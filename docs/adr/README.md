# ADR Index

Long-lived strategic operations decisions for the homelab Kubernetes cluster. If you find a matching ADR, **insert it here** and **link from the document where the information comes from** – declared ADRs do not replace code comments or README details.

ADRs document **decisions**, not ongoing analyses or incident reconstructions – for those, see the analysis documents (`*_ANALYSIS.md`, `*TROUBLESHOOTING.md`) and the [Known Issues](../issues/README.md).

## Project Key

Document IDs carry the **project key** defined in the project's `AGENTS.md` (three uppercase letters, e.g. `XYZ`): ADRs are referenced as `KEY-ADR-NNNN`, issues as `KEY-ISS-NNNN` (see `../issues/README.md`). The key appears in titles, index tables, and references – not in file names.

## Number Range

- `0000–0999` Architecture and operations decisions (active)
- Numbers are **not reused** – when an ADR expires, it is not deleted but marked with status `Superseded by KEY-ADR-NNNN` and its file is moved to `superseded/NNNN-short-title.md`. ADRs with status `Deprecated` (no direct successor) remain in the main folder. Update the index link and any references from other documents when moving (relative links break otherwise).
- Analyses / incident reconstructions do not belong in ADRs. They belong in `analysis/` (tempus, Confluence-like) – ADRs link there once the context has been derived.

## Status Values

`Proposed` → `Accepted` / `Rejected` → (`Superseded by KEY-ADR-NNNN`, file moves to `superseded/`) / (`Deprecated`, remains in place)

## Overview

| ID | Title | Status | Area |
| --- | --- | --- | --- |
| [DVT-ADR-0001](0001-example-adr.md) | First recorded decision | Accepted | affected module/subsystem etc. |

## All ADRs in Detail

### [DVT-ADR-0001: Example ADR](0001-example-adr.md)

- **Status:** Accepted
- **Area:** affected module/subsystem etc.
- **Core:** Briefly state the decision and context
