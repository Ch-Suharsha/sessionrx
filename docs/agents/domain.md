# Domain docs

This repository uses a single context, with `GLOSSARY.md` and `docs/adr/` at the repository root.

## Before exploring

Read `GLOSSARY.md` when it exists and read ADRs in `docs/adr/` that touch the area under discussion.

If these files do not exist, proceed silently. Domain modeling creates them as terminology and decisions are settled during explicitly requested work; setup reserves their locations without inventing domain content.

## Shared vocabulary

Use terms defined in `GLOSSARY.md` when naming domain concepts in code, tests, issues, and explanations. If a concept is missing, reconsider the term or raise the gap during domain modeling.

## Architectural decisions

Record settled architectural trade-offs as numbered Markdown ADRs under `docs/adr/`. If a proposal conflicts with an existing ADR, identify the conflict and discuss reopening the decision before replacing it.
