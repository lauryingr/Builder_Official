# US-8.7 — Gestione degli utenti

**Epic:** [EPIC 8 — Amministrazione (solo Admin)](../epics/epic-8-amministrazione.md)

**Attore:** Admin

**Necessità:** Voglio vedere e gestire gli utenti della piattaforma

**Obiettivo:** Per intervenire in caso di problemi di accesso o di uso scorretto.

## Criteri di accettazione

- L'Admin vede quanti utenti sono registrati e l'elenco degli utenti con nome, cognome, email, professione, data di registrazione e ultimo accesso, e può cercarli.
- L'Admin può aprire il dettaglio di ogni profilo.
- L'Admin può creare un nuovo profilo utente solo per conto di una persona che lo richiede esplicitamente, per esempio perché la registrazione dal portale non le funziona; l'Admin si assume la responsabilità di collegare il profilo all'indirizzo email indicato.
- La richiesta della persona viene registrata insieme al profilo creato (chi l'ha chiesta, quando e come).
- Il profilo creato dall'Admin resta inattivo finché la persona non lo attiva: riceve all'indirizzo indicato l'email di servizio con il link di attivazione (come la verifica in US-1.1).
- Al primo accesso è la persona stessa a scegliere la password e ad accettare i termini di servizio, l'informativa privacy e il consenso alla visibilità: l'Admin non conosce la password e non può accettare questi consensi al suo posto.
- L'Admin può sospendere e riattivare un utente; l'utente sospeso non può accedere.
- L'Admin può eliminare un utente, con le stesse regole dell'eliminazione del profilo (US-1.6) e dopo una conferma esplicita.
- L'Admin vede il contenuto delle cartelle personali e condivise degli utenti.
- L'Admin non può sospendere né eliminare sé stesso.

## Note

- L'accesso dell'Admin ai dati dei profili e al contenuto delle cartelle è dichiarato nell'informativa privacy (VL-04).
- La creazione di un profilo da parte dell'Admin è un'eccezione per assistere chi non riesce a registrarsi. Le regole possono cambiare dopo l'analisi legale (VL-04), per esempio sul modo di registrare la richiesta.
- Da chiarire cosa succede a un profilo creato dall'Admin e mai attivato (proposta: viene eliminato dopo un periodo definito).
- La creazione di un profilo da parte dell'Admin è registrata nei log di sistema (US-8.8).
