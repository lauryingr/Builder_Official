# US-9.5 — Log e storico dei controlli

**Epic:** [EPIC 9 — Monitoraggio automatico delle fonti (solo Admin)](../epics/epic-9-monitoraggio-automatico.md)

**Attore:** Admin

**Necessità:** Voglio consultare lo storico dei controlli effettuati

**Obiettivo:** Per verificare che il monitoraggio funzioni e ricostruire cosa è successo su una fonte.

## Criteri di accettazione

- Per ogni controllo sono registrati fonte, data e ora, esito (nessuna modifica, modifica rilevata, errore) e dettaglio dell'errore.
- Lo storico si può filtrare per fonte, comune, esito e periodo.
- Sono registrate anche le decisioni dell'Admin sugli aggiornamenti (approvato, scartato).
- Lo storico viene conservato per un periodo definito.

## Note

- Da chiarire per quanto tempo si conserva lo storico.
