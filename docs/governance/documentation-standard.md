# Documentation Standard

## 1) Scope

This standard applies to the entire `docs/` tree.

## 2) Structure standard (international best practice)

- Use **Diátaxis** to classify document intent.
- Keep one main concern per document.
- Enforce hierarchical navigation: portal → domain → subdomain → deep dive.

## 3) Naming conventions

- Folder names: English, lowercase-kebab-case.
- Files: descriptive and concise.
- Ordered content: `01-`, `02-`, ... prefixes.
- Main index files: `README.md` and `index.md`.

## 4) Mandatory front matter block

Use this YAML header for new documents:

```yaml
---
title: "<document-title>"
doc_type: "tutorial|how-to|reference|explanation|overview"
domain: "<domain>"
subdomain: "<subdomain>"
audience: "beginner|intermediate|advanced|mixed"
language: "en|vi"
last_reviewed: "YYYY-MM-DD"
version: "v1.0.0"
---
```

## 5) Quality checklist

Before merge, verify:

- Navigation links are valid.
- Scope and prerequisites are explicit.
- Commands/examples are reproducible.
- Terminology is consistent with parent domain docs.
- `docs/knowledge-map.md` is updated when structure changes.

## 6) AI readiness checklist

- Document contains clear sections and headings (`H1`/`H2`/`H3`).
- Definitions are explicit and non-ambiguous.
- Tables and lists are used for structured facts.
- Source path and revision date are visible.
