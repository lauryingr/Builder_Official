# BuildEr — Brainstorming tecnico: monitoraggio automatico delle fonti

> Documento di lavoro, non definitivo. Raccoglie idee e domande aperte sul sistema che scarica la documentazione edilizia dai siti istituzionali, controlla periodicamente gli aggiornamenti e aggiorna il database.
> Riferimenti: [Epic 9](epics/epic-9-monitoraggio-automatico.md), [US-8.1](user-stories/us-8.1-inserimento-documento.md), [US-8.2](user-stories/us-8.2-modifica-documento.md), PRD sez. 10 (VL-02, VL-03, VT-01…VT-04) e sez. 11.

---

## 1. Principio di base: versionare, non sovrascrivere

Ogni nuova versione di un documento viene **salvata accanto** alla precedente; cambia solo il puntatore alla "versione in vigore" che vedono gli utenti.

Perché:

- **Valore legale (VL-03):** una pratica edilizia si valuta sulla norma in vigore alla data di presentazione; può servire la versione di sei mesi fa. Lo storico è un punto di forza.
- **Errori dello scraper:** se il sito restituisce una pagina di errore al posto del PDF, sovrascrivendo si perde il documento buono.
- **Costo:** l'archiviazione dei PDF costa pochissimo.
- È già coerente con US-8.2 (la versione precedente viene segnata come non più in vigore) e US-9.3 (niente pubblicazione automatica).

---

## 2. Architettura

Processo separato dal sito (Worker Service .NET), che condivide il database con l'applicazione web.

```
Fonti → Pianificatore → Download → Confronto → Aggiornamento in attesa → Revisione Admin → Pubblicazione
 (DB)    (ogni tot)     (HTTP)     (hash)       (DB + file)               (US-9.4)          (notifiche)
```

| Componente | Strumenti .NET | Note |
|---|---|---|
| Pianificatore | Hangfire o Quartz.NET | Hangfire ha una dashboard pronta, utile per US-9.1 e US-9.6 |
| Download | `HttpClient` + `Microsoft.Extensions.Http.Resilience` (Polly) | Nuovi tentativi, attese crescenti, timeout |
| Lettura pagine HTML | AngleSharp | Trova i link ai PDF nelle pagine "Urbanistica" / "Amministrazione trasparente" |
| Siti costruiti in JavaScript | Playwright per .NET | Più pesante, solo dove serve |
| Testo dei PDF | PdfPig | Per il confronto tra versioni |
| Confronto del testo | DiffPlex | Mostra all'Admin cosa è cambiato |
| Archiviazione file | Azure Blob / S3 / disco | PDF fuori dal DB, nominati con il loro hash |

**Domande aperte**

- [ ] Hangfire o Quartz.NET?
- [ ] Il worker gira sullo stesso server del sito o separato (es. job su Azure Container Apps)?
- [ ] Dove si archiviano i PDF (VT-04)?

---

## 3. Rilevamento delle modifiche (VT-02)

Livelli dal più economico al più costoso; ci si ferma al primo che risponde.

1. **Richiesta condizionale HTTP** (`If-None-Match` con ETag, `If-Modified-Since`): se il server risponde `304`, non è cambiato nulla e non si scarica niente. Molti siti PA non lo gestiscono bene.
2. **Hash SHA-256 del file:** uguale all'ultimo → nessuna modifica.
3. **Hash del testo estratto e normalizzato** (senza spazi superflui, date di generazione, metadati): file diverso ma testo uguale → PDF solo rigenerato, falso positivo, non si disturba l'Admin.
4. **Percentuale di testo cambiato:** se il testo è diverso si crea l'aggiornamento in attesa con questo dato, per far capire subito all'Admin l'entità della modifica.
5. **PDF scansionati senza testo (VT-03):** il livello 3 non funziona → sempre revisione manuale.

Per le **pagine elenco HTML** non si fa l'hash della pagina intera (banner, date, token cambiano a ogni visita): solo dell'elenco estratto (titoli + link dei PDF).

**Domande aperte**

- [ ] Quale soglia di testo cambiato rende un aggiornamento "rilevante"?
- [ ] Come trattare i PDF scansionati: solo revisione manuale o in futuro OCR?

---

## 4. Modello dei dati (bozza)

- **Fonte:** comune, URL, tipo (file diretto / pagina elenco), configurazione dell'estrattore (JSON), frequenza, ETag, Last-Modified, stato, errori consecutivi.
- **Documento:** il documento "logico" (es. "Regolamento Edilizio del comune X").
- **VersioneDocumento:** hash del file, hash del testo, posizione del file archiviato, URL di origine, data del download, data di pubblicazione, stato (`in_attesa`, `pubblicata`, `superata`, `scartata`).
  - Vincolo di unicità su (documento, hash del file): la stessa versione non si salva due volte.
- **EsecuzioneControllo:** storico dei controlli (US-9.5).

**Domande aperte**

- [ ] Una versione può avere più file (NTA divise in più PDF, tavole del PRG)? Serve una tabella `FileVersione`?
- [ ] Azure SQL o PostgreSQL?

---

## 5. Problemi tipici dei siti dei comuni

- **File `.pdf.p7m`:** delibere firmate digitalmente (CAdES). Bisogna estrarre il PDF dalla busta firmata (es. BouncyCastle). Molto comune; la firma è anche una prova di autenticità.
- **Pagina HTML con risposta 200 al posto del PDF:** controllare sempre `Content-Type` e che il file inizi con `%PDF`.
- **Certificati TLS scaduti:** frequenti sui siti PA. Decidere una regola, senza disattivare la verifica in silenzio.
- **Documenti spezzati in più file:** NTA in più PDF, tavole del PRG.
- **File molto grandi** (tavole cartografiche da 100 MB e oltre): download a flusso, con un limite di dimensione.
- **URL che cambiano:** con un `404` non segnare subito la fonte in errore; prima cercare di nuovo il documento nella pagina elenco.

---

## 6. Rispetto dei siti (VL-02)

- Una richiesta alla volta per dominio, qualche secondo di pausa e un ritardo casuale.
- Controlli di notte.
- Rispetto di `robots.txt`.
- User-Agent che dichiara chi siamo, con un contatto.
- Frequenza: le norme edilizie cambiano raramente, **un controllo a settimana** basta.
- Volume stimato: ~7.900 comuni × ~3 documenti ≈ 24.000 fonti a settimana ≈ 3.400 al giorno. Molto basso.

**Domande aperte**

- [ ] Frequenza: settimanale per tutti o diversa per tipo di documento?
- [ ] Cosa fare se un sito blocca il monitoraggio (captcha, firewall)?

---

## 7. Scalare a migliaia di comuni (VT-01)

- Un estrattore per ogni comune non regge.
- Molti comuni usano gli stessi fornitori di software e molti siti nuovi seguono il modello AgID per i comuni.
- Idea: **un estrattore per tipo di sito**, più una configurazione per comune (quale estrattore, quali selettori).
- In futuro un LLM potrebbe classificare i PDF trovati (es. "è il Regolamento Edilizio?"); non serve per partire.

**Domande aperte**

- [ ] Esistono portali regionali che raccolgono già PRG/PAT/PI dei comuni? Potrebbero essere una fonte unica per molti comuni.
- [ ] Quanti tipi di sito diversi ci sono nella provincia di partenza?

---

## 8. Piano di partenza

1. **Una sola provincia**, con un elenco di URL diretti ai PDF compilato a mano (validazione con Elia).
2. **Solo i livelli 1–3** del confronto, con revisione dell'Admin. Niente ricerca automatica nelle pagine.
3. **Misurare:** quanti siti gestiscono l'ETag, quanti falsi positivi, quanti errori.
4. **Poi** estrattori per le pagine elenco e per tipo di sito.

**Domande aperte**

- [ ] Quale provincia di partenza?
- [ ] I PDF dei siti già visti hanno link diretti stabili o stanno dietro pagine JavaScript?

---

## 9. Note dal brainstorming

_Spazio per idee e decisioni prese durante la discussione._

-
