# Knowledge Map (Canonical)

This file is the canonical map for discovery, ingestion, and retrieval across the `docs/` tree.

## 1) Canonical hierarchy

- `docs/index.md` (global portal)
- `docs/governance/documentation-standard.md` (documentation policy)
- `docs/templates/document-template.md` (authoring template)
- `docs/technology/index.md` (domain-level index)
- `docs/technology/<domain>/README.md` (domain overview)
- `docs/technology/<domain>/<subdomain>/README.md` (subdomain overview)
- `docs/technology/<domain>/<subdomain>/<n>-<topic>.md` (deep-dive guides)

## 2) Domain inventory

- Programming
- Network
- Data
- AI
- DevOps
- Operations
- Systems
- Security
- Tester

## 3) Required metadata schema (for indexing)

Every indexed chunk should include:

- `domain`: top-level domain (e.g., `data`, `ai`)
- `subdomain`: second-level topic (e.g., `retrieval-augmented-generation`)
- `doc_type`: `tutorial | how-to | reference | explanation | overview`
- `audience`: `beginner | intermediate | advanced | mixed`
- `path`: canonical file path in repo
- `language`: document language code (e.g., `en`, `vi`)
- `last_reviewed`: ISO date (`YYYY-MM-DD`)
- `version`: semantic or date-based doc version

## 4) Ingestion order for RAG

1. `docs/index.md`
2. `docs/governance/documentation-standard.md`
3. `docs/technology/index.md`
4. all domain/subdomain `README.md`
5. specialized guides in numerical order

## 5) Retrieval strategy guidance

- Stage 1: metadata filter by `domain`, `subdomain`, `doc_type`.
- Stage 2: hybrid search (vector + keyword/BM25).
- Stage 3: reranking by query intent and authority level.
- Stage 4: answer generation with source citation (`path`).

## 6) Governance rule

When adding new documents, update this knowledge map in the same change set to keep AI ingestion deterministic.
