# US-1.1 — Registrazione e creazione del profilo

**Epic:** [EPIC 1 — Creazione e accesso al profilo](../epics/epic-1-accesso-profilo.md)

**Attore:** Visitatore non registrato (professionista)

**Necessità:** Voglio registrarmi sulla piattaforma e creare il mio profilo

**Obiettivo:** Per avere uno spazio personale in cui creare cartelle, salvare i documenti e collaborare con altri utenti.

## Criteri di accettazione

- Il modulo richiede nome, cognome, email, password e professione (Architetto, Geometra, Urbanista, Ingegnere civile).
- L'email deve avere un formato valido e non deve essere già registrata; in caso contrario viene mostrato un messaggio chiaro.
- verifica dell'email con link di conferma prima del primo accesso.
- La password rispetta i requisiti minimi di sicurezza indicati nel modulo.
- Per completare la registrazione l'utente accetta i termini di servizio e l'informativa privacy.
- A registrazione completata l'utente ha un profilo con ruolo User e accede alla piattaforma.
- Tutti gli utenti registrati hanno gli stessi privilegi; l'Admin non si crea da questo modulo.

## Note

- Eventuali campi aggiuntivi utili alla ricerca utenti (Epic 3), come studio o provincia (per ora no).
- L'utente NON può caricare propri documenti né file in nessun modo.
- Nessun utente eccetto Admin può in modo alcuno accedere al DB dell'archivio normativo. 
- Un utente può scegliere di non comparire nella ricerca e dunque non essere aggiunto e partecipare a cartelle condivise, questa opzione deve essere presentata nelle impostazioni di modifica del profilo, di default vengono settate con il flag di visibilità attivo (consenso accettato nei termini e condizioni esplicitati alla creazione dell'account).

