# BuildEr — PRD

> Product Requirements Document
> **Autore:** Laura Ingrid Ragoni
> **Data:** 23/09/2026
> **Versione:** 1.0 (bozza)
> **Stato:** bozza

---

## 1. Idea

L’idea nasce da molte conversazioni nate con il mio compagno Elia, Architetto neo laureato che ha iniziato a lavorare come come tale in uno studio di Ingegneria Edile integrata ad Oderzo. Il suo compito è quello di progettare opere urbane molto diverse in base alla committenza.

---

## 2. Contesto e problema

Durante questi ragionamenti mi presenta il suo problema: la reperibilità delle normative di ogni comune. Ogni comune italiano non pubblica le proprie norme urbanistiche ed edilizie in un formato standard, né in un luogo prevedibile del proprio sito istituzionale. Non esiste un portale unico nazionale che raccolga in modo organico Regolamenti Edilizi, Piani Regolatori (PRG/PGT/PAT/PI) e relative Norme Tecniche di Attuazione: ogni professionista è costretto a cercare manualmente, comune per comune, spesso tra decine di PDF sparsi tra sezioni "Urbanistica", "Edilizia Privata" e "Amministrazione Trasparente", senza alcuna garanzia che il documento trovato sia effettivamente l'ultima versione in vigore.

Questo chiaramente porta via molto tempo solo nella ricerca dei documenti e ulteriore tempo per la consultazione.

### 2.1 Problema da risolvere

La soluzione per risolvere parzialmente questo problema sarebbe una sorta di applicativo web basato su un archivio digitale, organizzato per localizzazione geografica (regione, provincia, comune), che raccoglie in un unico punto tutta la documentazione normativa edilizia e urbanistica ufficiale, ovviamente reperita esclusivamente da fonti istituzionali (siti comunali, BUR regionali, Normativa) e la mantiene aggiornata tramite un sistema di monitoraggio automatico, così che un architetto non debba più chiedersi se la norma che sta consultando sia ancora quella in vigore.

### 2.2 Perché ora

Cioò che ha dato origine a BuildEr non nasce da un'analisi di mercato a tavolino, ma da una richiesta concreta e diretta del mio compagno, nel confrontarsi ogni giorno con le normative urbanistiche ed edilizie dei comuni in cui lavora. Non è un'ipotesi di prodotto in cerca di un problema — è un problema reale, vissuto da un professionista sul campo, che cerca una soluzione.

### 2.3 Cosa è incluso e cosa non è incluso

E' inclusa:

- La possibilità di crare un utente e di salvare i pdf dei comuni più utilizzati.
- La possibilità di richiedere attraverso una form, i pdf dei documenti di un comune non ancora nel DB
- Scaricare qualsiasi pdf presente dei comuni inseriti
- Banner di notifica all'utente quando viene aggiornata una normativa di un comune che ha salvato tra i preferiti, e quando viene invitato in una cartella condivisa (accetta o rifiuta)
- Data/versione di ultimo aggiornamento visibile su ogni documento con chiara indicazione della fonte da cui proviene per sicurezza.
- Ricerca filtro per tipologia di documento oltre che per provincia e comune.
- Dashboard nella home con le 20 regioni, le relative province e i comuni, in verde se la normativa del comune è presente e in rosso altrimenti
- Gestione multi-utente: cartelle condivisibili con altri utenti (team = membri di una cartella, tutti pari), con inviti per email

Non è incluso:

- Interrogazione in linguaggi naturale/AI sulle normative. Le normative potranno solo essere consultate oppure scaricate.
- integrazioni con altri software di progettazione/CAD.
- Verifica di conformità automatica di un progetto rispetto alla normativa
- Copertura di tutti i 7900 comuni italiani al lancio, (le integrazioni, se possibili, saranno graduali)

---

## 3. Obiettivi e metriche di successo

_Da compilare: obiettivi di prodotto, KPI e target misurabili._

---

## 4. Mercato e competitor

Che il bisogno sia reale e non isolato è confermato: esiste già un'Ai arcai.it (Normo S.r.l., Milano), che si propone di risolvere lo stesso problema per l'Italia, offrendo interrogazione in linguaggio naturale delle normative di migliaia di comuni. La sua esistenza è una validazione indiretta: il problema della reperibilità e dell'aggiornamento delle normative comunali è reale.

Il bisogno è confermato dai tre Consigli nazionali (architetti, ingegneri, geometri), che chiedono una riforma perché la stratificazione normativa crea incertezza.

- **Arcai si occupa di:**
  - Chat normativa universale
  - redazioni di relazioni tecniche
  - Verifica conformità progetto (Fonti tracciate e verificate)
  - alert sugli aggiornamenti
  - stendere bozze precompilate delle principali pratiche edilizie
  - Copertura progressiva di 7.904 comuni
  - Form di richiesta normative di comuni mancanti
  - Piano pro oppure piano personalizzato

  Il piano Pro costa €39/mese, con il primo mese a €1, e c'è un piano Studio su misura. Ti correggo una cosa: i 7.896 comuni che ti avevo citato sono un obiettivo di copertura progressiva, e dove il comune manca l'utente carica i propri PDF. La copertura reale in Veneto è quindi da verificare. Stanno anche preparando un portale per i Comuni.

---

## 5. Stakeholder

| 👤 Persona                                                  | 🎯 Bisogno principale                                                                                                                                                                          | 📍 Contesto d'uso                                                                                                                                                                                                 |
| ----------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Architetto, ingegnere edile/civile, urbanista, geometra** | Reperire rapidamente la normativa edilizia/urbanistica ufficiale e aggiornata (Regolamento Edilizio, PRG/PGT/PAT/PI, NTA) di uno specifico comune, con certezza di avere la versione in vigore | Fase di progettazione preliminare o di verifica di conformità, spesso sotto scadenza verso il committente; lavoro su più comuni/province diversi, con esigenza di consultare e scaricare in PDF la documentazione |
| **Studio tecnico / Società di progettazione**               | Standardizzare e velocizzare la ricerca normativa per tutti i collaboratori, riducendo il tempo (e costo) speso in attività non progettuali                                                    | Gestione di più commesse contemporanee in comuni diversi; necessità che junior e collaboratori trovino la normativa corretta senza dover ricorrere sistematicamente al senior                                     |

---

## 6. Archetipi utente

### 6.1 Elia

- **Ruolo:** Architetto neolaureato, dipendente di uno studio di ingegneria edile
- **Età:** 25 anni
- **Obiettivi:**
  - Trovare in pochi minuti la normativa in vigore per il comune su cui sta lavorando
  - Avere la certezza che il documento scaricato sia la versione aggiornata, senza doverla verificare a mano sul sito del comune
  - Archiviare i PDF consultati nel fascicolo di pratica in modo ordinato
- **Frustrazioni attuali:**
  - Perde ore a cercare PDF sparsi tra sezioni "Urbanistica", "Edilizia Privata" e "Amministrazione Trasparente"
  - Non ha mai la certezza di essere di fronte all'ultima versione in vigore di un regolamento
  - Deve ripetere la stessa ricerca ogni volta che lo studio prende una commessa in un nuovo comune
- **Comportamento d'uso:** Consulta la normativa soprattutto nella fase preliminare di progettazione e nella verifica di conformità, spesso sotto scadenza; lavora su più comuni/province in parallelo
- **Citazione rappresentativa:** _"voglio essere sicuro di avere in mano il PDF giusto e aggiornato e di consultarlo in pochi click."_

### 6.2 Studio Progettazione integrata & General Contractor

- **Ruolo:** Medio/grande studio di progettazione con titolari, senior e collaboratori junior
- **Obiettivi:**
  - Ridurre il tempo (e quindi il costo) che i collaboratori junior spendono in attività di ricerca non progettuale
  - Rendere autonomi i junior nella ricerca normativa, senza che debbano interrompere continuamente i senior
  - Avere uno storico condiviso della documentazione normativa già raccolta per i comuni in cui lo studio opera abitualmente
- **Frustrazioni attuali:**
  - Ogni collaboratore rifà da zero la stessa ricerca già fatta da un collega per lo stesso comune
  - Difficoltà a garantire che tutti nello studio lavorino sulla stessa versione aggiornata della normativa
- **Comportamento d'uso:** Gestisce più commesse contemporanee in comuni diversi; ha bisogno di condividere cartelle di documenti tra i membri del team, dove ognuno aggiunge ciò che serve alla propria competenza
- **Citazione rappresentativa:** _"Se un collega ha già trovato la normativa di un comune, voglio che tutto lo studio ci acceda senza rifare la ricerca da capo."_

---

## 7. Ruoli utente

| Ruolo | Descrizione                                        |
| ----- | -------------------------------------------------- |
| Admin | Gestione completa della piattaforma e degli utenti |
| User  | Architetto, Geometra, Urbanista, Ingegnere civile  |

2 tipologie di utente previste: Admin e User.

---

---

## 8. Epic

Il backlog è organizzato in 9 Epic. Ogni Epic ha un proprio file di dettaglio in [epics/](epics/). Le User Story verranno ridefinite in base alla struttura degli Epic.

| Epic   | Titolo                                      | File                                                                             |
| ------ | ------------------------------------------- | -------------------------------------------------------------------------------- |
| EPIC 1 | Creazione e accesso al profilo                           | [epic-1-accesso-profilo.md](epics/epic-1-accesso-profilo.md)                     |
| EPIC 2 | Cartelle personali                          | [epic-2-cartelle-personali.md](epics/epic-2-cartelle-personali.md)               |
| EPIC 3 | Ricerca utenti e inviti                    | [epic-3-ricerca-utenti-inviti.md](epics/epic-3-ricerca-utenti-inviti.md)         |
| EPIC 4 | Cartelle condivise                          | [epic-4-cartelle-condivise.md](epics/epic-4-cartelle-condivise.md)               |
| EPIC 5 | Archivio normativo                          | [epic-5-archivio-normativo.md](epics/epic-5-archivio-normativo.md)               |
| EPIC 6 | Notifiche                                   | [epic-6-notifiche.md](epics/epic-6-notifiche.md)                                 |
| EPIC 7 | Assistenza                                  | [epic-7-assistenza.md](epics/epic-7-assistenza.md)                               |
| EPIC 8 | Amministrazione (solo Admin)                | [epic-8-amministrazione.md](epics/epic-8-amministrazione.md)                     |
| EPIC 9 | Monitoraggio automatico delle fonti (Admin) | [epic-9-monitoraggio-automatico.md](epics/epic-9-monitoraggio-automatico.md)     |

---

## 9. User Story

Le User Story sono in [user-stories/](user-stories/), una per file, raggruppate per Epic. Sono definite per ora solo quelle dell'Epic 1; le altre verranno aggiunte epic per epic.

### EPIC 1 — Creazione e accesso al profilo

| ID     | Titolo                                | File                                                                          |
| ------ | ------------------------------------- | ----------------------------------------------------------------------------- |
| US-1.1 | Registrazione e creazione del profilo | [us-1.1-registrazione.md](user-stories/us-1.1-registrazione.md)               |
| US-1.2 | Accesso alla piattaforma (login)      | [us-1.2-login.md](user-stories/us-1.2-login.md)                               |
| US-1.3 | Uscita dalla piattaforma (logout)     | [us-1.3-logout.md](user-stories/us-1.3-logout.md)                             |
| US-1.4 | Recupero della password              | [us-1.4-recupero-password.md](user-stories/us-1.4-recupero-password.md)       |
| US-1.5 | Modifica del profilo                  | [us-1.5-modifica-profilo.md](user-stories/us-1.5-modifica-profilo.md)         |
| US-1.6 | Eliminazione del profilo              | [us-1.6-eliminazione-profilo.md](user-stories/us-1.6-eliminazione-profilo.md) |

## 10. Assunzioni e vincoli

Assunzioni di partenza e vincoli (legali, tecnici, di budget, di tempo). Questa sezione è un documento vivo: le voci vengono analizzate nel tempo e lo stato aggiornato (Da analizzare, In analisi, Deciso).

### 10.1 Legali

| ID    | Voce                          | Descrizione                                                                                                                     | Stato         | Domande aperte                                                                                                                                    |
| ----- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| VL-01 | Riproduzione dei PDF          | I documenti dei comuni verrebbero ripubblicati sulla piattaforma; la licenza d'uso non è nota e può variare da comune a comune. | Da analizzare | Quali regole sul riuso dei dati pubblici e quali licenze si applicano? Basta citare la fonte o serve un permesso?                                 |
| VL-02 | Raccolta automatica dai siti  | Il monitoraggio delle fonti (Epic 8) scarica periodicamente file dai siti istituzionali.                                        | Da analizzare | I termini d'uso dei siti e robots.txt lo consentono? Con quale frequenza è accettabile?                                                           |
| VL-03 | Responsabilità sulla versione | Un utente potrebbe lavorare su un documento non più in vigore perché l'aggiornamento non è stato ancora rilevato.               | Da analizzare | Quale disclaimer è necessario? Come si dichiara che la fonte ufficiale resta quella del comune?                                                   |
| VL-04 | GDPR e dati personali         | La piattaforma tratta dati personali di utenti professionisti (profilo, cartelle condivise, preferiti, notifiche).              | Da analizzare | Chi è il titolare del trattamento? Servono informativa, registro dei trattamenti e contratto con chi ospita i dati? Dove devono risiedere i dati? |
| VL-05 | Termini di servizio e cookie  | Servono termini di servizio, informativa privacy e gestione dei cookie prima del lancio.                                        | Da analizzare | Chi li redige? È necessaria una consulenza legale?                                                                                                |

### 10.2 Tecnici

| ID    | Voce                          | Descrizione                                                                                                                                | Stato         | Domande aperte                                                                                 |
| ----- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------- | ---------------------------------------------------------------------------------------------- |
| VT-01 | Eterogeneità delle fonti      | Ogni comune pubblica i documenti in formato e posizione diversi, senza standard.                                                           | Da analizzare | Come si configura una fonte in modo robusto? Quanto lavoro manuale richiede ogni nuovo comune? |
| VT-02 | Rilevamento delle modifiche   | Il confronto tra versioni (es. impronta del file) può dare falsi positivi se il PDF viene rigenerato senza modifiche reali.                | Da analizzare | Quale metodo di confronto è affidabile? Come si riducono i falsi aggiornamenti?                |
| VT-03 | PDF scansionati               | Molti PDF possono essere immagini non ricercabili; la ricerca nel testo richiederebbe il riconoscimento del testo (OCR), oggi fuori scope. | Da analizzare | La ricerca per comune, provincia e tipologia è sufficiente al lancio?                          |
| VT-04 | Piattaforma e infrastruttura  | Non sono ancora stati scelti stack, hosting, archiviazione dei file, invio email, backup.                                                  | Da analizzare | Quali scelte tecnologiche? Quali requisiti di sicurezza e disponibilità?                       |
| VT-05 | Copertura iniziale dei comuni | Il lancio non copre tutti i circa 7.900 comuni; la copertura cresce gradualmente.                                                          | Da analizzare | Quali comuni e province all'inizio? Con quale criterio si scelgono?                            |

### 10.3 Budget

| ID    | Voce                               | Descrizione                                                                                   | Stato         | Domande aperte                                        |
| ----- | ---------------------------------- | --------------------------------------------------------------------------------------------- | ------------- | ----------------------------------------------------- |
| VB-01 | Costi ricorrenti di infrastruttura | Hosting, archiviazione dei PDF, email transazionali, dominio, monitoraggio.                   | Da analizzare | Qual è la stima mensile al lancio e a regime?         |
| VB-02 | Consulenza legale                  | Probabile costo una tantum per licenze, GDPR e termini di servizio.                           | Da analizzare | Quale preventivo? Quali aspetti sono prioritari?      |
| VB-03 | Lavoro di inserimento e controllo  | Inserimento e verifica dei documenti da parte dell'Admin: potenzialmente la voce più pesante. | Da analizzare | Quante ore per comune? Chi lo svolge?                 |
| VB-04 | Modello di ricavi                  | Non è ancora definito; il concorrente Arcai ha un piano Pro a 39 €/mese (vedi sezione 4).     | Da analizzare | Gratuito, abbonamento, piano per studi? Quale prezzo? |
| VB-05 | Budget complessivo e fondi         | Il budget disponibile e la sua origine non sono stati stabiliti.                              | Da analizzare | Quanto si può investire e per quanto tempo?           |

### 10.4 Assunzioni di partenza

| ID    | Voce                                     | Descrizione                                                                                                              | Stato         | Domande aperte                                                       |
| ----- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | ------------- | -------------------------------------------------------------------- |
| AS-01 | Fonti pubbliche e raggiungibili          | I documenti sono sempre disponibili pubblicamente sui canali istituzionali.                                              | Da analizzare | Che cosa accade se un comune rimuove o sposta un documento?          |
| AS-02 | Disponibilità degli utenti a registrarsi | I professionisti accettano di creare un profilo per accedere ai documenti.                                               | Da analizzare | L'ipotesi è stata verificata con utenti reali oltre al caso di Elia? |
| AS-03 | Curatela manuale dei contenuti           | I contenuti sono curati da un Admin; i rilevamenti automatici richiedono sempre una revisione prima della pubblicazione. | Da analizzare | Quante persone servono per mantenere la qualità dei dati?            |
| AS-04 | Valori dei requisiti non funzionali      | I valori numerici della sezione 9 (tempi, volumi, conservazione) sono ipotesi.                                           | Da analizzare | Chi li valida e con quali dati?                                      |

---

## 11. Stack tecnologico

## 12. Dipendenze

_Da compilare: fonti dati istituzionali, servizi di terze parti, team o attività da cui dipende il progetto._

---

## 13. Rischi e mitigazioni

_Da compilare: rischi principali (es. qualità/copertura dei dati, aspetti legali sulla riproduzione dei documenti) e azioni di mitigazione._

---

## 14. Roadmap e rilascio

- **Prima i contenuti, poi l'automazione.** Il valore del prodotto è avere documenti ufficiali, corretti e con fonte visibile; il monitoraggio automatico (Epic 8) si aggiunge quando c'è già un archivio da monitorare (AS-03: la curatela è comunque manuale).
- **Area pilota ristretta.** Si parte dai comuni di Elia (Veneto, zona Oderzo/Treviso) e si allarga per cerchi, scegliendo i comuni con i dati dei log di richiesta (US-5.2) e non a tavolino (VT-05).
- **Nessun lancio pubblico senza il minimo legale** (VL-01…VL-05).
- **Validazione con utenti reali** a ogni fase, oltre al caso di Elia (AS-02).

### 14.2 Fasi

| Fase                          | Obiettivo                                                 | Contenuto                                                                                                                                                                                                                                                                                                                                      | Epic / US coinvolte                                                           | Criteri di uscita                                                                                                                                |
| ----------------------------- | --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **0. Fondamenta**             | Chiudere ciò che blocca il progetto                       | Validazione lista fonti con Elia; link alle fonti primarie e flag di accessibilità; scelta stack e hosting (sez. 11); prima analisi legale (VL-01, VL-02); definizione KPI (sez. 3)                                                                                                                                                            | Flusso ricerca fonti, sez. 3, 10, 11                                          | Lista fonti validata; stack scelto; esito preliminare su licenze e termini d'uso dei siti; KPI definiti                                          |
| **1. MVP / alpha chiusa**     | Verificare che l'idea risolva il problema di Elia         | Registrazione e profilo; archivio per regione/provincia/comune; scheda documento con data, versione e fonte; download PDF; ricerca per comune, provincia e tipologia; backoffice Admin per inserire documenti e anagrafica territoriale; modulo assistenza e richiesta nuovo comune. Notifiche, cartelle condivise e monitoraggio **esclusi**. | Epic 1 (US-1.1…1.3), Epic 6 (US-6.1…6.4), US-3.1, Epic 5, Epic 7 (US-7.1…7.7) | Elia + 3–5 utenti invitati trovano un documento in pochi minuti; dati dell'area pilota inseriti e verificati; nessun bug bloccante               |
| **2. Beta chiusa**            | Funzioni di uso quotidiano e collaborazione               | Preferiti e cartelle personali; cartelle condivise con inviti (team); consultazione online; dashboard di copertura verde/rosso; centro notifiche e banner (documento richiesto, aggiornamento preferito, invito)                                                                                                                               | Epic 2, restante Epic 3 (US-3.2…3.7), Epic 4, US-6.5                          | Almeno uno studio usa le cartelle condivise; le richieste di nuovo comune vengono evase entro il tempo target; feedback raccolto e prioritizzato |
| **3. Lancio pubblico (v1.0)** | Aprire a tutti i professionisti con la copertura iniziale | Copertura estesa (provincia/e pilota completa/e); monitoraggio automatico con revisione Admin; notifiche per provincia; pagine legali e cookie; modello di ricavi attivo (VB-04)                                                                                                                                                               | Epic 8, US-4.3, US-4.4                                                        | Criteri di lancio (14.3) tutti soddisfatti                                                                                                       |
| **4. Crescita**               | Estendere copertura e valore                              | Nuove province/regioni in base alla domanda; miglioramento rilevamento modifiche (VT-02); valutazione OCR e ricerca nel testo (VT-03); piani per studi                                                                                                                                                                                         | Backlog successivo                                                            | Obiettivi di copertura e retention (sez. 3)                                                                                                      |

### 14.3 Criteri di lancio pubblico (go / no-go)

**Legali**

- Licenza di riuso/ripubblicazione dei PDF chiarita; fonte sempre citata (VL-01)
- Verifica di termini d'uso e robots.txt delle fonti monitorate (VL-02)
- Disclaimer sulla versione in vigore: la fonte ufficiale resta quella del comune (VL-03)
- Informativa privacy, registro dei trattamenti e accordo con il fornitore di hosting (VL-04)
- Termini di servizio e cookie pubblicati (VL-05)

**Contenuto**

- Copertura dell'area di lancio completa per Regolamento Edilizio, strumento urbanistico e NTA, ciascun documento con data/versione e fonte
- Ogni documento verificato da una persona prima della pubblicazione

**Prodotto e qualità**

- Tutte le User Story del perimetro di fase completate e criteri di accettazione verificati
- Requisiti non funzionali critici rispettati (prestazioni, sicurezza, accessibilità, sez. 9)
- Backup e ripristino provati; invio email affidabile (inviti, notifiche)

**Operativi**

- Processo e persona responsabili dell'evasione di richieste e segnalazioni
- Stima dei costi ricorrenti validata (VB-01)

### 14.4 Dipendenze critiche

- Validazione della lista fonti da parte di Elia (blocca la Fase 0)
- Esito dell'analisi legale (blocca il lancio pubblico, non l'alpha chiusa)
- Scelta dello stack (blocca l'inizio dello sviluppo)
- Disponibilità di chi inserisce e controlla i documenti (VB-03): è il collo di bottiglia della copertura

### 14.5 Da decidere

- Date e durata di ciascuna fase (dipendono da team e budget)
- Area pilota definitiva e numero di comuni al lancio
- Modello di ricavi e momento di attivazione (gratuito in beta, a pagamento dal lancio?)
- Se spostare il monitoraggio automatico (Epic 8) prima del lancio o dopo, in base al carico di curatela manuale

---

## 15. Domande aperte

_compila se ne hai_

---
