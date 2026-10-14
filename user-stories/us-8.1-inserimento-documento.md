# US-8.1 — Inserimento di un documento

**Epic:** [EPIC 8 — Amministrazione (solo Admin)](../epics/epic-8-amministrazione.md)

**Attore:** Admin

**Necessità:** Voglio inserire un nuovo documento normativo nell'archivio

**Obiettivo:** Per rendere disponibile agli utenti la normativa ufficiale di un comune.

## Criteri di accettazione

- Un nuovo documento può entrare nell'archivio in due modi:
  - in automatico: BuildEr acquisisce il PDF dalle fonti monitorate (Epic 9) e precompila i dati; l'Admin li controlla e li completa;
  - a mano: l'Admin carica il PDF e compila i dati.
- I dati richiesti sono titolo, tipologia, comune, data/versione, fonte ufficiale (link) e data di verifica. Tutti i campi obbligatori devono essere compilati; la fonte deve essere un sito istituzionale.
- In entrambi i casi l'Admin vede un'anteprima e il documento è visibile agli utenti solo dopo che l'Admin lo ha pubblicato.
- Dopo la pubblicazione la dashboard di copertura si aggiorna secondo la regola di US-5.2 (nella prima versione un comune è coperto quando è presente il Regolamento Edilizio).
- La pubblicazione genera le notifiche per provincia (US-6.4).

## Note

- Ogni documento è verificato da una persona prima della pubblicazione (AS-03), anche quando è stato acquisito in automatico.
- L'obiettivo di BuildEr è automatizzare il più possibile l'acquisizione; l'inserimento manuale resta per i casi che il sistema automatico non copre.
