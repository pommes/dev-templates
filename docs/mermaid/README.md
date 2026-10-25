# Mermaid Templates

Shared Mermaid conventions for consistent, reusable diagrams across projects. This directory is language-neutral: the diagram vocabulary is defined once and referenced by every diagram – no duplication, no per-language variants.

## Files

- `style.snippet` – the standard `%%{init}%%` directive (neutral theme, 12 px font) so all diagrams share a consistent look.
- `example-components.mmd` – demo diagram with the shared artifact vocabulary (components, databases, actors) to copy from.

## Convention

Mermaid has no include mechanism, so the reuse principle from PlantUML (`docs/puml/`) is adapted:

- Every embedded Mermaid diagram is a Markdown code fence (` ```mermaid `) and **starts with the `%%{init}%%` directive from `style.snippet`** (copy-paste).
- Use consistent node IDs and labels, following the vocabulary of `example-components.mmd` (e.g. `roundcube`, `postfixadmin`, `mariadb`, `act_mail_user`). A diagram then only defines relationships (edges, labels) – not new spellings of existing artifacts.

## Example

`example-components.mmd` shows the same mail system as `docs/puml/example_components.puml`, rendered from a plain ` ```mermaid ` fence:

````markdown
```mermaid
%%{init: {"theme":"neutral","themeVariables":{"fontSize":"12px"}}}%%
flowchart LR
    subgraph system
        direction TB
        server["mail/server"]
        postfixadmin["mail/postfixadmin"]
        roundcube["mail/roundcube"]
        mariadb[("mariadb")]
        db_postfixadmin[("Postfixadmin DB")]
        db_roundcube[("Roundcube DB")]
    end

    act_relay["External Mail Relay"]
    act_mail_user(["Mail User"])
    act_mail_admin(["Mail Admin"])
    act_webmail_user(["Webmail User"])

    act_webmail_user --> roundcube
    act_mail_admin --> postfixadmin
    act_mail_user --> server
    act_relay <--> server

    roundcube -->|"use mailbox (R/W)"| server
    roundcube -->|"own data (R/W)"| db_roundcube
    postfixadmin -->|"domains and addresses (R/W)"| db_postfixadmin
    server -->|"domains and addresses (R)"| db_postfixadmin
    mariadb -->|manages| db_postfixadmin
    mariadb -->|manages| db_roundcube
```
````
