# US-4.4 — Uscita da una cartella condivisa (autoesclusione)

**Epic:** [EPIC 4 — Cartelle condivise](../epics/epic-4-cartelle-condivise.md)

**Attore:** Utente autenticato (membro della cartella)

**Necessità:** Voglio uscire da una cartella condivisa

**Obiettivo:** Per non vedere più le cartelle dei progetti a cui non partecipo.

## Criteri di accettazione

- Il membro può uscire dalla cartella dopo una conferma esplicita.
- Nessun membro può escludere un altro: si può solo uscire di propria volontà.
- Dopo l'uscita la cartella sparisce dal suo elenco e il suo nome non compare più tra i membri.
- I documenti che aveva aggiunto restano nella cartella per gli altri membri.
- Se esce l'ultimo membro, la cartella viene eliminata e l'ultimo utente visualizza un messaggio che esplicita che in quanto ultimo membro la cartella verrà irreversibilmente eliminata. 
- Per rientrare serve un nuovo invito da parte di un membro.

## Note

- Una cartella condivisa non si può eliminare per tutti: si elimina solo quando esce l'ultimo membro (coerente con US-1.6).
