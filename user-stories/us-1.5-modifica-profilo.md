# US-1.5 — Modifica del profilo

**Epic:** [EPIC 1 — Creazione e accesso al profilo](../epics/epic-1-accesso-profilo.md)

**Attore:** Utente autenticato

**Necessità:** Voglio modificare i dati del mio profilo e la mia password

**Obiettivo:** Per mantenere le informazioni aggiornate e per essere trovato correttamente dagli altri utenti.

## Criteri di accettazione

- L'utente può modificare nome, cognome, professione ed eventuali campi aggiuntivi del profilo.
- La modifica dell'email richiede la conferma della nuova email e non può coincidere con un'email già registrata.
- Per cambiare la password l'utente inserisce quella attuale e la nuova, che rispetta i requisiti di sicurezza.
- Le modifiche si salvano solo se i dati sono validi, e l'utente riceve la conferma del salvataggio.
- Le modifiche sono visibili agli altri utenti nella ricerca utenti e nelle cartelle condivise.
- Con un'opzione esplicita nelle impostazioni del profilo l'utente può rendersi non visibile agli altri utenti: non compare nella ricerca utenti (US-3.1) e non può ricevere nuovi inviti (US-3.2).
- L'opzione non ha effetto sulle cartelle condivise di cui l'utente è già membro: resta nell'elenco dei membri e continua a partecipare. L'Admin vede sempre tutti i profili.
- L'utente può tornare visibile dalle impostazioni, dando di nuovo in modo esplicito il consenso alla visibilità.
