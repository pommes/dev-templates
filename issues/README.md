# Known Issues

Known, (not yet) resolved or fixed issues of the cluster/repo. Issues document **problems**, not decisions – for those, see the [ADRs](../adr/README.md).

## Process

1. New issue: `NNNN-short-title.md` (sequential, 4-digit), based on `template.md`.
2. Status `Open`; on resolution → `Resolved (YYYY-MM-DD)` with a resolution note.
3. Issues are **not deleted** – they remain as recurrence knowledge. On recurrence: set status back to `Open`, add note "Re-opening #N" with date.
4. If a problem is mitigated by an architecture change (instead of being directly fixed), status `Resolved` with reference "done by ADR-XXXX".
5. When a problem is reported in chat that cannot be fixed immediately: create an issue (or re-open an existing one). Agents do this proactively.

## Index – Open

| No. | Title | Status | Priority | ADR |
|-----|-------|--------|-----------|-----|
| [0002](0002-example-issue-open.md) | Open example issue | Open | Low | – |


## Index – Resolved

| No. | Title | Status | ADR |
|-----|-------|--------|-----|
| [0001](0001-example-issue-resolved.md) | Closed example issue | Resolved (2026-10-21) | 0001 |


## Once Resolved

An issue file remains in place as a knowledge store. Resolved issues document symptom, cause, fix, and recurrence criterion – they are the first point of contact when a known symptom reappears.
