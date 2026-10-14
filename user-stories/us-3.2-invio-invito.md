# US-3.2 — Invio di un invito a una cartella

**Epic:** [EPIC 3 — Ricerca utenti e inviti](../epics/epic-3-ricerca-utenti-inviti.md)

**Attore:** Utente autenticato (membro della cartella)

**Necessità:** Voglio invitare un altro utente in una mia cartella

**Obiettivo:** Per lavorare insieme sugli stessi documenti senza che ognuno rifaccia la stessa ricerca.

## Criteri di accettazione

- Dalla cartella o dai risultati della ricerca utenti l'utente sceglie chi invitare e in quale cartella.
- Può invitare qualsiasi membro della cartella, compresi gli utenti che a loro volta sono stati invitati.
- Non si può invitare chi è già membro della cartella o ha già un invito in attesa per la stessa cartella; in quel caso viene mostrato un messaggio chiaro.
- L'invitato riceve una notifica solo all'interno del portale (US-6.1), con il nome di chi invita e il nome della cartella; non viene inviata alcuna email.
- Chi invita riceve la conferma dell'invio e vede l'invito come "in attesa" finché l'invitato non risponde.
- Quando il primo invito a una cartella personale viene accettato, la cartella diventa condivisa (Epic 4).
- Un invito senza risposta scade dopo 20 giorni e viene eliminato (US-6.5); per entrare nella cartella serve un nuovo invito.
- Non si possono invitare gli utenti che hanno scelto di non essere visibili (US-1.5).

## Note

- Si possono invitare solo utenti già registrati: non esistono inviti via email.
- Da chiarire se chi invita può annullare un invito ancora in attesa.
