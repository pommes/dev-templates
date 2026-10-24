# PlantUML Templates

Shared PlantUML building blocks for consistent, reusable diagrams across projects. This directory is language-neutral: artifacts are defined once and included by every diagram that needs them – no duplication, no per-language variants.

## Files

- `style.puml` – global `skinparam` settings (monochrome, 150 dpi, arrow thickness, …) so all diagrams share a consistent look.
- `example_components.puml` – demo of the reuse principle: reusable artifacts (components, ports, actors, databases) that any number of diagrams can include and link together. In a real project, the corresponding file is named `components.puml`.

## Convention

Every embedded PlantUML diagram is a Markdown code fence (` ```plantuml `) and includes `style.puml` and `components.puml` via `!include`, with a path relative to the diagram's own location, pointing into `docs/puml`. The diagram itself only defines relationships (arrows, labels) between the included artifacts – not their declarations. This keeps component definitions consistent repo-wide.

## Example

`example_components.puml` shows how artifacts are reused across diagrams, in the sense of a repo-wide vocabulary:

````markdown
```plantuml
!include ./style.puml
!include ./example_components.puml

roundcube --> p_imaps : use mailbox (R/W)
roundcube --> p_sieve : admin filter (R/W)

roundcube ---> db_roundcube : "own data (RW)"
postfixadmin ---> db_postfixadmin : "domains and\n adresses (RW)"
server ---> db_postfixadmin : "domains and\n addresses (R)"

mariadb -> db_postfixadmin : "manages"
db_roundcube <- mariadb : "manages"

act_relay <----> p_smtp
act_mail_user ----> p_imaps
act_mail_user ----> p_smtp
act_mail_admin ----> p_postfixadmin_http

act_webmail_user --> p_roundcube_http

remove @unlinked
```
````

The `!include` paths in the example resolve from the diagram's own directory; when a diagram lives outside `docs/puml`, adjust the relative path accordingly (e.g. `!include ../puml/style.puml`).
