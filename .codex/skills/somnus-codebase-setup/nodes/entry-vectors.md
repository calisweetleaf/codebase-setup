# Node: entry-vectors

**Parent skill:** somnus-codebase-setup
**Kind:** entry sequences
**Status:** locked

## What this node is

Two ways to enter the Somnus codebase setup system: **cold entry** (repo has no Somnus surfaces yet) and **warm entry** (repo already has them). These are not rigid checklists — they are navigation entry points. The skill is the topology; the sequence is the path you walk from the state that actually exists.

---

## Cold entry — repo has no Somnus surfaces yet

Use when starting a brand-new Somnus codebase or converting a raw repo into an agent-operable Somnus workspace.

1. **Read the operator's explicit current instruction** — highest authority. It may override or specialize any template.
2. **Instantiate `AGENTS.md`** from `AGENTS.template.md`. Fill: Project identity, Behavioral constitution, Operating rules, Authority + Conflict Resolution, Start of Session sequence, Validation, Hard Bans, Environment, Project-Specific Invariants.
3. **Instantiate `filetree.md`** — run the tree generator. Spatial awareness must exist before any wandering.
4. **Instantiate `CONTEXT.md`** from `CONTEXT.template.md`. Set: Workspace state, Active delivery surface, Current branch/revision, Active packet, Last meaningful validation, Main unresolved variable.
5. **Instantiate `MEMORY.md`** from `MEMORY.template.md`. Record Initial Lock-In entry + Canon/authority lock.
6. **Instantiate `NOTEPAD.md`** from `NOTEPAD.template.md`. Leave an OPEN entry describing the setup task.
7. **Instantiate `PROVENANCE.md`** from `PROVENANCE.template.md`. Record v0.1 snapshot + Initial Lock-In decision + Session Log header.
8. **Instantiate `STATE.md`** (required by AGENTS.md but not in the template list). Current runtime truth: what exists, what passes, what fails, active frontier, blocked items, next justified action.
9. **Instantiate `ARCHITECTURE.md` / `SPEC.md`** from `ARCHITECTURE.template.md`. Normative authority.
10. **Instantiate `ARCHITECTURE_MAP.md`** from `ARCHITECTURE_MAP_TEMPLATE.md`. ROOT question + BRANCH questions with file:line anchors + Quick Reference table.
11. **Instantiate `DEVELOPMENT_SETUP.md`** from `DEVELOPMENT_SETUP.template.md`. Define `<GATE_COMMAND>`.
12. **Run the gate / narrowest validation.** Update `STATE.md`.
13. **Refresh `filetree.md`** after all structural instantiations.

Do not begin by reading the entire repository. Recover state in the order above unless project-specific rules say otherwise.

---

## Warm entry — repo already has Somnus surfaces

Use when resuming work in an existing Somnus codebase.

1. Read `AGENTS.md`.
2. Read `STATE.md`.
3. Read the newest relevant portion of `NOTEPAD.md`.
4. Read `SPEC.md` sections relevant to the active frontier.
5. Read `ANTITHESIS.md` for known invalid directions.
6. Read `filetree.md`.
7. Consult `MEMORY.md` and `CONTEXT.md` for the specific subsystem/problem.
8. Read the active `TASK.md` / `PLAN.md` packet, if one exists.
9. Inspect the actual implementation and tests.
10. Run the project gate or narrowest meaningful validation command.

Do not repeatedly reread solved history when persistent project state already contains the needed result.

---

## How to choose

| Situation | Entry vector |
|-----------|--------------|
| Repo has only templates / no AGENTS.md | Cold entry |
| Repo has AGENTS.md + STATE.md + NOTEPAD.md | Warm entry |
| Repo has AGENTS.md but it's stale/contradicts tree | Cold entry for AGENTS.md, then warm for the rest; repair AGENTS.md from live evidence |
| Unsure which | Start with cold entry step 1 (read operator instruction); it will tell you |

Entry vector: enter this node first when setting up or resuming a Somnus codebase.

Next nodes: `template-field.md` (what each template projects), `failure-grammar.md` (check before declaring done), `provenance.md` (record the setup in Session Log).
