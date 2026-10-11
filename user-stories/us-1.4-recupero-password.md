# US-1.4 — Recupero della password

**Epic:** [EPIC 1 — Creazione e accesso al profilo](../epics/epic-1-accesso-profilo.md)

**Attore:** Utente registrato che non ricorda la password

**Necessità:** Voglio reimpostare la mia password

**Obiettivo:** Per riottenere l'accesso al mio account senza chiedere aiuto all'Admin.

## Criteri di accettazione

- Dalla pagina di accesso l'utente può richiedere il recupero inserendo la propria email.
- Se l'email è registrata riceve un messaggio con un link per reimpostare la password; la risposta mostrata a schermo è la stessa anche se l'email non esiste.
- Il link ha una scadenza e si può usare una sola volta.
- La nuova password rispetta gli stessi requisiti della registrazione.
- Dopo il cambio l'utente può accedere con la nuova password.

## Note

- Dipende dalla scelta del servizio di invio email (VT-04).
