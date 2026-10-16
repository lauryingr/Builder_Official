# US-9.3 — Rilevamento automatico delle modifiche

**Epic:** [EPIC 9 — Monitoraggio automatico delle fonti (solo Admin)](../epics/epic-9-monitoraggio-automatico.md)

**Attore:** Sistema (a beneficio dell'Admin)

**Necessità:** Voglio che il sistema controlli periodicamente le fonti e rilevi le modifiche

**Obiettivo:** Per sapere quando un comune pubblica una nuova versione senza doverlo controllare a mano.

## Criteri di accettazione

- Ogni fonte viene controllata con la frequenza impostata.
- Il sistema confronta il file o la pagina con l'ultima versione nota e registra se è cambiato.
- Una modifica rilevata crea un aggiornamento in attesa di revisione e avvisa l'Admin; non viene mai pubblicata in automatico.
- Se la fonte non è raggiungibile o il file è sparito, la fonte viene segnata in errore e l'Admin viene avvisato.

## Note

- Il metodo di confronto deve ridurre i falsi positivi, per esempio PDF rigenerati senza modifiche reali (VT-02).
