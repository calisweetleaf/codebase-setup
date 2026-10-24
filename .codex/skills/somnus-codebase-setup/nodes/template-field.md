# Node: template-field

**Parent skill:** somnus-codebase-setup
**Kind:** load-bearing concept
**Status:** locked

## What this node is

The 8 templates in `filetree.md` are not documentation. They are **structure projectors**: each one projects a specific persistent surface into a repo and defines that surface's semantic role in the Somnus continuity field. Instantiating a template means replacing its placeholders with live evidence, not copying the placeholder text.

## Template → surface → role

| Template (source) | Projects into | Semantic role in the field |
|-------------------|---------------|----------------------------|
| `AGENTS.template.md` | `AGENTS.md` | Runtime router + transition grammar. Tells an entering operator how to inhabit the repo. ~25% rules, ~25% runtime/env knowledge, ~50% navigation/orchestration. |
| `ARCHITECTURE.template.md` | `ARCHITECTURE.md` / `SPEC.md` | Normative technical authority + codebase whitepaper. Defines intended architecture, semantics, contracts, invariants. |
| `ARCHITECTURE_MAP_TEMPLATE.md` | `ARCHITECTURE_MAP.md` | Question-graph traversal map. ROOT question + BRANCH questions with file:line anchors; any component reachable within 3 hops. |
| `CONTEXT.template.md` | `CONTEXT.md` | Current indexed state router. Structured index linking to primary evidence; not raw history. |
| `DEVELOPMENT_SETUP.template.md` | `DEVELOPMENT_SETUP.md` | Environment + runtime contract. Prerequisites, setup steps, testing, `<GATE_COMMAND>`. |
| `MEMORY.template.md` | `MEMORY.md` | Durable learned knowledge. Append-oriented; prevents rediscovery; not a transcript or scratchpad. |
| `NOTEPAD.template.md` | `NOTEPAD.md` | External working memory. Append-only workbook for active working state; not canon, not authoritative. |
| `PROVENANCE.template.md` | `PROVENANCE.md` | Decision log + session lineage. Decisions, rejected paths, integration history, session log, handoff state. |

## The placeholder contract

Every template carries placeholders (`%%PROJECT_NAME%%`, `%%CREATED_DATE%%`, `<replace>`, `[Project name goes here]`, etc.). The rule:

- A placeholder is **structure**, not evidence.
- Copying a placeholder into a live file is a setup failure (see failure-grammar node).
- Every placeholder must be replaced with live, project-specific evidence before the surface counts as instantiated.

## Entry vector

Enter this node when: you are about to instantiate any template surface, or you need to know what surface a template projects.

Next nodes: `authority-field.md` (how surfaces relate), `entry-vectors.md` (cold/warm setup sequence), `provenance.md` (template → live surface chains).
