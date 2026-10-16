# US-5.2 — Dashboard di copertura nella home

**Epic:** [EPIC 5 — Archivio normativo](../epics/epic-5-archivio-normativo.md)

**Attore:** Utente autenticato

**Necessità:** Voglio vedere nella home quali regioni, province e comuni sono coperti dalla piattaforma

**Obiettivo:** Per capire subito se la normativa del comune che mi interessa è disponibile.

## Criteri di accettazione

- La home mostra un elenco navigabile delle 20 regioni; da ogni regione si scende alle province e da ogni provincia ai comuni.
- Ogni comune è verde se è coperto e rosso altrimenti. Nella prima versione di BuildEr un comune è coperto quando è presente il suo Regolamento Edilizio.
- Per regioni e province viene mostrato quanti comuni sono coperti sul totale.
- Cliccando un comune verde l'utente vede i suoi documenti; cliccando un comune rosso può richiederne l'inserimento (US-7.2).
- Il colore non è l'unica indicazione: lo stato è riportato anche in testo, per l'accessibilità.

## Note

- Nelle versioni successive la regola di copertura potrà includere anche strumento urbanistico e NTA.

