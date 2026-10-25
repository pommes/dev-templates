# dev-templates

Shared documentation templates for development projects: ADRs (Architecture Decision Records) and Known Issues. Templates are written in **English as lingua franca**; the structure is language-independent, while content language is up to the consuming project.

## Purpose

Instead of duplicating templates across repositories, projects fetch them from this repo on demand. This repo is the single source of truth for structure and conventions.

## Repository Layout

```
docs/
  adr/
    README.md     ADR conventions (number range, status values, index format, superseded/ convention)
    template.md   Skeleton for a new ADR
  issues/
    README.md     Known-Issue conventions (lifecycle, index format)
    template.md   Skeleton for a new issue
    resolved/     Resolved issues (knowledge store)
  puml/
    README.md     How to embed PlantUML diagrams (include convention + example)
    style.puml    Global skinparams for a consistent diagram look
    example_components.puml  Demo of reusable diagram artifacts (components, ports, actors)
  mermaid/
    README.md     How to embed Mermaid diagrams (init convention + example)
    style.snippet Standard %%{init}%% header for a consistent diagram look
    example-components.mmd  Demo diagram with the shared artifact vocabulary
```

## How Consuming Projects Use This

1. Fetch the templates and conventions from this repo (raw URLs):
   - ADRs: `https://raw.githubusercontent.com/<owner>/dev-templates/main/docs/adr/template.md` and `docs/adr/README.md`
   - Issues: `https://raw.githubusercontent.com/<owner>/dev-templates/main/docs/issues/template.md` and `docs/issues/README.md`
   - PlantUML: `https://raw.githubusercontent.com/<owner>/dev-templates/main/docs/puml/style.puml` and the conventions from `docs/puml/README.md`
   - Mermaid: `https://raw.githubusercontent.com/<owner>/dev-templates/main/docs/mermaid/style.snippet` and the conventions from `docs/mermaid/README.md`
2. Copy the templates into the project as `docs/adr/template.md` and `docs/issues/template.md`; adopt the conventions from the READMEs. Put `style.puml` into the project's `docs/puml/` and define reusable diagram artifacts in `docs/puml/components.puml` (see the PlantUML README for the include convention). Put `style.snippet` into the project's `docs/mermaid/` and start every Mermaid diagram with its `%%{init}%%` directive.
3. Create documents from the templates and maintain the index tables as described in the respective READMEs.

### Suggested AGENTS.md Snippet

Add this to the consuming project's `AGENTS.md` so agents handle this correctly:

```markdown
## Documentation

- ADRs, Known Issues, and PlantUML diagrams follow the templates from https://github.com/<owner>/dev-templates:
  - ADRs: fetch `docs/adr/template.md` and the conventions from `docs/adr/README.md`
  - Issues: fetch `docs/issues/template.md` and the conventions from `docs/issues/README.md`
  - PlantUML: fetch `docs/puml/style.puml` and the include conventions from `docs/puml/README.md`; define shared artifacts in `docs/puml/components.puml`
  - Mermaid: fetch `docs/mermaid/style.snippet` and the conventions from `docs/mermaid/README.md`; start every diagram with its `%%{init}%%` directive
- Copy the templates to `docs/adr/`, `docs/issues/`, `docs/puml/`, and `docs/mermaid/` and fill them in.
- Write all content in the project language; the structure follows the template.
- PlantUML diagrams only define relationships between the artifacts included from `docs/puml/`. Mermaid diagrams start with the `%%{init}%%` directive and reuse the artifact vocabulary from `docs/mermaid/`.
```

## Language Handling

The templates are in English on purpose: they define **structure**, not content. Agents in consuming projects fill them in the project's language, guided by the project's `AGENTS.md`. Language-neutral assets (e.g. diagram snippets, formatting conventions) live here once, without language suffixes or duplicate folders.
