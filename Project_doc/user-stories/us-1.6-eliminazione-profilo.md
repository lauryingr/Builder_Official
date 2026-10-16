# US-1.6 — Eliminazione del profilo

**Epic:** [EPIC 1 — Creazione e accesso al profilo](../epics/epic-1-accesso-profilo.md)

**Attore:** Utente autenticato

**Necessità:** Voglio eliminare il mio profilo

**Obiettivo:** Per uscire dalla piattaforma e far cancellare i miei dati personali.

## Criteri di accettazione

- La funzione è nelle impostazioni del profilo e richiede una conferma esplicita (con inserimento della password).
- L'utente viene avvisato di cosa succede prima di confermare: cartelle personali eliminate, uscita da tutte le cartelle condivise.
- Dopo la conferma l'utente è disconnesso e non può più accedere con le vecchie credenziali.
- I dati personali sono cancellati secondo quanto richiesto dal GDPR (VL-04).
- Le cartelle condivise di cui era membro restano ai membri rimasti; se era l'ultimo membro, la cartella viene eliminata.

## Note

-I documenti che l'utente aveva aggiunto in una cartella condivisa restano se ci sono altri utenti dentro.

- L'eliminazione dell'Admin non deve essere possibile.
