# Known Issues

Known, (not yet) resolved or fixed issues of the cluster/repo. Issues document **problems**, not decisions – for those, see the [ADRs](../adr/README.md).

## Project Key

Every project defines a unique **project key** (three uppercase letters, e.g. `XYZ`) in its `AGENTS.md`. Document IDs are prefixed with it so references stay unambiguous across projects:

- Issues: `KEY-ISS-NNNN`
- ADRs: `KEY-ADR-NNNN` (see `../adr/README.md`)

The key appears in document titles, index tables, and all references – **not** in file names (they remain `NNNN-short-title.md`).

## Process

1. New issue: `NNNN-short-title.md` (sequential, 4-digit), based on `template.md`. It is referenced as `KEY-ISS-NNNN` using the project key from `AGENTS.md`.
2. Status `Open`; on resolution → `Resolved (YYYY-MM-DD)` with a resolution note. Resolved issue files are moved to `resolved/NNNN-short-title.md` – the folder structure then shows at a glance what is still open. Update the index link and any references from other documents when moving (relative links break otherwise).
3. Issues are **not deleted** – they remain as recurrence knowledge. On recurrence: move the file back to the main folder, set status back to `Open`, add note "Re-opening KEY-ISS-NNNN" with date.
4. If a problem is mitigated by an architecture change (instead of being directly fixed), status `Resolved` with reference "done by KEY-ADR-NNNN".
5. When a problem is reported in chat that cannot be fixed immediately: create an issue (or re-open an existing one). Agents do this proactively.

## Index – Open

| ID | Title | Status | Priority | ADR |
|-----|-------|--------|-----------|-----|
| [DVT-ISS-0002](0002-example-issue-open.md) | Open example issue | Open | Low | – |


## Index – Resolved

| ID | Title | Status | ADR |
|-----|-------|--------|-----|
| [DVT-ISS-0001](resolved/0001-example-issue-resolved.md) | Closed example issue | Resolved (2026-10-21) | DVT-ADR-0001 |


## Once Resolved

An issue file remains in place as a knowledge store, in the `resolved/` subfolder. Resolved issues document symptom, cause, fix, and recurrence criterion – they are the first point of contact when a known symptom reappears.
