# Node: failure-grammar

**Parent skill:** somnus-codebase-setup
**Kind:** pre-failure signatures
**Status:** locked

## What this node is

This node records what goes wrong when setting up a Somnus codebase from templates. Each entry names a failure, its symptom, and the first response. These are pre-failure signatures — signs that setup is going off the rails before the repo is broken.

## Failure table

| # | Failure | Symptom | First response |
|---|---------|---------|----------------|
| 1 | Template treated as evidence | Placeholder text (`%%PROJECT_NAME%%`, `<replace>`, `[Project name goes here]`, `replace`) copied into a live file as if it were real state | Treat template as structure only; replace every placeholder with live evidence before counting the surface as instantiated |
| 2 | AGENTS.md becomes a spec dump | Deep implementation detail lives in AGENTS.md; navigation buried under code detail | Move implementation detail to SPEC.md / STATE.md / MEMORY.md / CONTEXT.md; keep AGENTS.md as router (~25% rules, ~25% runtime, ~50% navigation) |
| 3 | NOTEPAD → MEMORY skip | Durable findings left only in NOTEPAD.md, never promoted upward | Promote durable findings to CONTEXT.md then MEMORY.md; NOTEPAD is transient scratch, not canon |
| 4 | Stale filetree | Navigation points to missing, renamed, or moved files | Regenerate filetree.md after every structural change; a stale file tree is a navigation bug |
| 5 | SPEC/STATE drift | Implementation contradicts SPEC; STATE.md not updated when runtime truth changes | Investigate the disagreement; repair deliberately; update STATE.md whenever truth materially changes |
| 6 | No gate defined | No `<GATE_COMMAND>`; changes "landed" by edit alone with no validation | Define `<GATE_COMMAND>` in DEVELOPMENT_SETUP.md; gate must PASS before any handoff or release |
| 7 | Authority inversion | Generated prose or NOTEPAD.md treated as outranking live source or SPEC.md | Enforce authority order: operator instruction → live source → SPEC → STATE → contracts/tests → ANTITHESIS → MEMORY → CONTEXT → task surfaces → NOTEPAD → generated prose |

## How to use

Enter this node when:
- A setup step feels like it's cutting corners (placeholder left in, gate skipped, filetree not refreshed).
- Two surfaces disagree and you're tempted to just "pick one."
- You're about to mark a template-derived surface as "done."

Check each failure against the current repo state before declaring setup complete.

Entry vector: enter from `entry-vectors.md` before the validation gate, or from `template-field.md` when instantiating any surface.

Next nodes: `entry-vectors.md` (the setup sequence), `provenance.md` (record decisions about which failure path you took).
