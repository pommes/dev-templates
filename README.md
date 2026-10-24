# dev-templates

Shared documentation templates for development projects: ADRs (Architecture Decision Records) and Known Issues. Templates are written in **English as lingua franca**; the structure is language-independent, while content language is up to the consuming project.

## Purpose

Instead of duplicating templates across repositories, projects fetch them from this repo on demand. This repo is the single source of truth for structure and conventions.

## Repository Layout

```
docs/
  adr/
    README.md     ADR conventions (number range, status values, index format)
    template.md   Skeleton for a new ADR
  issues/
    README.md     Known-Issue conventions (lifecycle, index format)
    template.md   Skeleton for a new issue
  puml/           PlantUML snippets and includes (language-neutral)
```

## How Consuming Projects Use This

1. Fetch the templates and conventions from this repo (raw URLs):
   - ADRs: `https://raw.githubusercontent.com/<owner>/dev-templates/main/docs/adr/template.md` and `docs/adr/README.md`
   - Issues: `https://raw.githubusercontent.com/<owner>/dev-templates/main/docs/issues/template.md` and `docs/issues/README.md`
2. Copy the templates into the project as `docs/adr/template.md` and `docs/issues/template.md`; adopt the conventions from the READMEs.
3. Create documents from the templates and maintain the index tables as described in the respective READMEs.

### Suggested AGENTS.md Snippet

Add this to the consuming project's `AGENTS.md` so agents handle this correctly:

```markdown
## Documentation

- ADRs and Known Issues follow the templates from https://github.com/<owner>/dev-templates:
  - ADRs: fetch `docs/adr/template.md` and the conventions from `docs/adr/README.md`
  - Issues: fetch `docs/issues/template.md` and the conventions from `docs/issues/README.md`
- Copy the templates to `docs/adr/` and `docs/issues/` and fill them in.
- Write all content in the project language; the structure follows the template.
```

## Language Handling

The templates are in English on purpose: they define **structure**, not content. Agents in consuming projects fill them in the project's language, guided by the project's `AGENTS.md`. Language-neutral assets (e.g. diagram snippets, formatting conventions) live here once, without language suffixes or duplicate folders.
