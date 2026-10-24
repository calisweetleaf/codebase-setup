# codex — Agent Context

## What This Codebase Is
Somnus codebase setup skill domain. Instantiates the 8 template surfaces from filetree.md
into a live agent-operable workspace. See ARCHITECTURE_MAP.md for navigation.

## Architecture
- AGENTS.md — runtime router + transition grammar
- MEMORY.md / CONTEXT.md / NOTEPAD.md / STATE.md / PROVENANCE.md — continuity surfaces
- ARCHITECTURE.md / SPEC.md — normative technical authority
- ARCHITECTURE_MAP.md — question-graph traversal map
- DEVELOPMENT_SETUP.md — environment + <GATE_COMMAND>
- filetree.md — navigable structural topology

## What You Cannot Get Wrong (Load-Bearing Concepts)
- AGENTS.md is the router, not the spec — keep implementation detail out of it
- filetree.md is spatial awareness, not a dispatcher — it tells you where, not what to do
- NOTEPAD.md is transient scratch; promote durable findings to CONTEXT.md → MEMORY.md
- STATE.md is current runtime truth; update it when truth materially changes
- No template placeholders (%%, <>, []) may remain in live surfaces

## What Already Exists (Do Not Reimplement)
- All 8 Somnus template surfaces (instantiated by somnus-codebase-setup)
- CTMv3 skill at skills/ctmv3/ (boot protocol, topology, failure grammar)

## Baked-In Decisions (Do Not Question These)
- CTM over SOP — skills encode topology, not checklists
- Multi-doc skill package — SKILL.md is the only entry point, others load conditionally
- AGENTS.md is canonical; CLAUDE.md extends it

## If Something Smells Wrong
- Template placeholders in live files → replace with live evidence
- AGENTS.md becoming a spec dump → move detail to SPEC.md/STATE.md
- Stale filetree → regenerate after structural change
- No <GATE_COMMAND> → define in DEVELOPMENT_SETUP.md before handoff

## Tools
- somnus-codebase-setup (this skill) — npx-installable, repo-agnostic via --repo
- CTMv3 boot protocol — cold/warm entry detection
