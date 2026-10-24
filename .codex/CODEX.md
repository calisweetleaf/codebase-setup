# CODEX.md — Extends AGENTS.md. When in conflict, rebuild from AGENTS.md.

## What This Project Is
codex — Somnus codebase setup domain. Agent-operable workspace instantiated from 8 template surfaces.

## Topology Map
→ ARCHITECTURE_MAP.md (question-graph traversal, file:line anchors)

## Boot Protocol
1. Read AGENTS.md
2. Read STATE.md
3. Read newest NOTEPAD.md entry
4. Read relevant SPEC.md / ARCHITECTURE.md sections
5. Read filetree.md
6. Consult MEMORY.md / CONTEXT.md
7. Run <GATE_COMMAND>

## Tools Available
- somnus-codebase-setup: install once globally, run `somnus-codebase-setup --repo <path>` from anywhere
- CTMv3: skills/ctmv3/ for boot protocol + topology

## Operations Requiring Confirmation
- Deleting data or modifying manifest.json
- Production deploys
