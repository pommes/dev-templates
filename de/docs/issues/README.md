# Known Issues

Bekannte, (noch) ungelöste bzw. behobene Probleme des Clusters/Repos. Issues dokumentieren **Probleme**, keine Entscheidungen – dafür sind die [ADRs](../adr/README.md) da.

## Ablauf

1. Neues Issue: `NNNN-kurztitel.md` (fortlaufend, 4-stellig), Basis `template.md`.
2. Status `Open`, bei Lösung → `Resolved (JJJJ-MM-TT)` mit Lösungsnotiz.
3. Issues werden **nicht gelöscht** – sie bleiben als Wiederauftreten-Wissen. Bei Wiederkehr: Status zurück auf `Open`, Vermerk „Re-Öffnung #N" mit Datum.
4. Wird ein Problem durch eine Architekturänderung entschärft (statt direkt gelöst), Status `Resolved` mit Verweis „erledigt durch ADR-XXXX".
5. Bei Meldung eines Problems im Chat, das nicht sofort gelöst werden kann: Issue anlegen (oder bestehendes re-öffnen). Agenten machen das proaktiv.

## Index – Open

| Nr. | Titel | Status | Priorität | ADR |
|-----|-------|--------|-----------|-----|
| [0002](0002-beispiel-issue-open.md) | Offenes Beispielissue | Open | Niedrig | – |


## Index – Resolved

| Nr. | Titel | Status | ADR |
|-----|-------|--------|-----|
| [0001](0001-beispiel-issue-resolved.md) | Geschlossenes Beispielissue | Resolved (2026-10-21) | 0001 |


## Sobald gelöst

Ein Issue-File bleibt als Wissensspeicher bestehen. Gelöste Issues dokumentieren Symptom, Ursache, Fix und Wiederauftreten-Kriterium – sie sind die erste Anlaufstelle, wenn ein bekanntes Symptom wieder auftaucht.
