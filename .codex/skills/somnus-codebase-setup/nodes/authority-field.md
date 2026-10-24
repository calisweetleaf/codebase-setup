# Node: authority-field

**Parent skill:** somnus-codebase-setup
**Kind:** functional relations
**Status:** locked

## What this node is

Surfaces inside a Somnus codebase do not relate through single-source authority. They relate through a **field of functional relations**: some preserve, some project, some constrain, some condition, some expose, some narrow, some recall, some trigger.

A model operating in this field does not experience "I must obey AGENTS.md which governs everything." It experiences each surface as a local functional relation. Together they form an acceleration field around agent intelligence.

## Relation map

| Surface | Relation | What it does | Default authority order position* |
|---------|----------|--------------|-----------------------------------|
| AGENTS.md | CONSTRAINS + ROUTES | Bounded work definition; tells entering operator how to inhabit | router (top of navigation) |
| ARCHITECTURE.md / SPEC.md | CONSTRAINS | Normative technical authority; intended architecture | 3 |
| ARCHITECTURE_MAP.md | NAVIGATES | Question graph; reach any component within 3 hops | navigation aid |
| CONTEXT.md | RECALLS + INDEXES | Current indexed state; rapid future routing | 5 |
| DEVELOPMENT_SETUP.md | CONDITIONS | Environment + runtime contract; gates execution | runtime context |
| MEMORY.md | RECALLS + PRESERVES | Durable knowledge; prevents rediscovery | 7 |
| NOTEPAD.md | RECALLS (transient) + CARRIES | Cross-session state carry; external scratch | 10 |
| PROVENANCE.md | PRESERVES + LINEAGES | Decision log, session history, rejected paths | decision log |
| filetree.md | EXPOSES | Structural topology; spatial awareness before wandering | navigation aid |
| STATE.md | EXPOSES + TRIGGERS | Current runtime truth; tells what changed | 4 |

\* Default project authority order per AGENTS.md:
1. operator's explicit current instruction
2. current source / executable behavior / direct evidence
3. SPEC.md
4. STATE.md
5. project-local contracts and tests
6. ANTITHESIS.md
7. MEMORY.md
8. CONTEXT.md
9. current task/plan surfaces
10. NOTEPAD.md
11. generated prose and stale summaries

## How to read this

- **CONSTRAINS** surfaces (AGENTS.md, SPEC.md) set boundaries on what is permissible.
- **CONDITIONS** surfaces (DEVELOPMENT_SETUP.md) gate whether execution can proceed.
- **EXPOSES** surfaces (filetree.md, STATE.md) make structure or truth visible.
- **RECALLS** surfaces (CONTEXT.md, MEMORY.md, NOTEPAD.md) carry state across turns/sessions.
- **PRESERVES** surfaces (PROVENANCE.md) keep history from being lost.
- **NAVIGATES** surfaces (ARCHITECTURE_MAP.md) let an agent reach any component quickly.
- **PROJECTS** surfaces (templates) bring new structure into existence.

## Conflict resolution

When authoritative surfaces conflict:
1. Record the conflict.
2. Determine which surface is stale or incomplete.
3. Repair the disagreement deliberately.
4. Update persistent state.

Never allow generated prose to silently outrank implementation or normative source.

Entry vector: enter when two surfaces disagree, or when you need to know which surface to consult for a given question.

Next nodes: `template-field.md` (what each surface is), `entry-vectors.md` (recovery sequence starts at AGENTS.md), `failure-grammar.md` (authority inversion is a listed failure).
