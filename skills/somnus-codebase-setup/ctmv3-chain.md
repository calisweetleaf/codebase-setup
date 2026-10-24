# CTMv3 Chain — somnus-codebase-setup ↔ @skills/ctmv3

**This document explains how the two skills chain together.** They remain two
separate skill packages. `somnus-codebase-setup` is a *domain skill* that
instantiates Somnus template surfaces. `ctmv3` is the *meta-framework engine*
that provides boot protocol, workspace activation, topology construction, and
ecosystem artifacts. The chain is: **CTMv3 boot → somnus-codebase-setup domain
instantiation → CTMv3 Phase 5 ecosystem artifacts.**

---

## The two skills, separate but chained

| Skill | Role | Lives at |
|-------|------|----------|
| `@skills/ctmv3` | Meta-framework: boot protocol (cold/warm), topology construction, failure grammar, provenance, ecosystem artifacts (`.github/`, `.claude/`, `.codex/`, `.sovereign/`) | `skills/ctmv3/` |
| `somnus-codebase-setup` | Domain skill: Somnus template instantiation (8 templates from `filetree.md` → live surfaces), authority field, entry vectors | `skills/somnus-codebase-setup/` |

---

## Runtime chain (what happens when you run `npx somnus-codebase-setup`)

```
1. npx somnus-codebase-setup
   │
   ├── Detect CTMv3 (skills/ctmv3/ or ~/.codex/skills/ctmv3/)
   │
   ├── CTMv3 BOOT_PROTOCOL.md discovery (< 60s, read-only)
   │   ├── COLD_START  → CTMv3 Phase 0-5 workspace activation
   │   │     (TOPOLOGY.md, ARCHITECTURE_MAP.md, .sovereign/, AGENTS.md, etc.)
   │   └── WARM_START  → PROVENANCE.md diff, continue from last session
   │
   ├── somnus-codebase-setup installs itself into .codex/skills/somnus-codebase-setup/
   │
   ├── somnus-codebase-setup instantiates Somnus templates:
   │   AGENTS.template.md → AGENTS.md
   │   MEMORY.template.md → MEMORY.md
   │   CONTEXT.template.md → CONTEXT.md
   │   NOTEPAD.template.md → NOTEPAD.md
   │   PROVENANCE.template.md → PROVENANCE.md
   │   ARCHITECTURE.template.md → ARCHITECTURE.md / SPEC.md
   │   ARCHITECTURE_MAP_TEMPLATE.md → ARCHITECTURE_MAP.md
   │   DEVELOPMENT_SETUP.template.md → DEVELOPMENT_SETUP.md
   │   (+ STATE.md, filetree.md refresh)
   │
   ├── somnus-codebase-setup records session log in PROVENANCE.md
   │
   └── CTMv3 Phase 5 ecosystem artifacts (if CTMv3 present)
         .sovereign/session_state.json, topology_fingerprint.txt,
         .github/copilot-instructions.md, .claude/settings.json + CLAUDE.md,
         pre-commit hooks, golden_paths.json
```

---

## How CTMv3's semantic router references this skill

CTMv3's `SKILL.md` semantic router maps task types to entry documents. Add this
entry to CTMv3's router (in `skills/ctmv3/SKILL.md`, under the TASK TYPE table):

```
[SETUP_SOMNUS_CODEBASE] — instantiating Somnus template surfaces
  → skills/somnus-codebase-setup/SKILL.md (entry vector: cold or warm)
```

Or, from CTMv3's perspective, the task type is `[COLD_START_REPO]` when a
Somnus repo has no surfaces yet, and `somnus-codebase-setup` is the domain
skill that knows *which* templates to instantiate for a Somnus codebase
specifically.

---

## How somnus-codebase-setup references CTMv3

In `skills/somnus-codebase-setup/SKILL.md`, under Entry Vectors:

- **Cold entry** delegates the boot-state check to CTMv3 `BOOT_PROTOCOL.md`
  before running the template instantiation sequence.
- **Warm entry** uses CTMv3 `BOOT_PROTOCOL.md` §3 warm validity check before
  proceeding.
- **Provenance** uses CTMv3 `PROVENANCE.md` template for session log entries.
- **Ecosystem** (Phase 5) is handled by CTMv3 `DOT_TOPOLOGY.md` build sequence.

---

## Installation as an npx package

```bash
# From anywhere, run in a target repo:
cd /path/to/somnus/repo
npx somnus-codebase-setup

# Force cold entry (full template instantiation):
npx somnus-codebase-setup --cold

# Force warm entry (resume, don't overwrite existing surfaces):
npx somnus-codebase-setup --warm

# Dry-run (report what would be done, no writes):
npx somnus-codebase-setup --check
```

The package installs the skill into `.codex/skills/somnus-codebase-setup/`
inside the target repo, making it available to Codex, Claude Code, Droid, and
OpenCode agents operating in that repo.

---

## Compatibility matrix

| Agent | How it uses the skill |
|-------|----------------------|
| Codex | Reads `skills/somnus-codebase-setup/SKILL.md` as a skill; `bin/` auto-applies via npx |
| Claude Code | Reads `SKILL.md` nodes for topology; `bin/` installs into `.codex/skills/` |
| Droid | Reads `SKILL.md` for cognitive topology; `bin/` for workspace setup |
| OpenCode | Reads `SKILL.md` for navigation; `bin/` for repo activation |

---

## Anti-patterns in the chain

- ❌ Merging the two skills into one package — they serve different layers
  (meta-framework vs. domain skill)
- ❌ Running somnus-codebase-setup without CTMv3 boot protocol — you lose
  cold/warm detection and may overwrite existing surfaces
- ❌ Running CTMv3 Phase 5 ecosystem artifacts before somnus-codebase-setup
  instantiates AGENTS.md — hooks enforce topology that doesn't exist yet
- ❌ Treating CTMv3's `ARCHITECTURE_MAP_TEMPLATE.md` and somnus-codebase-setup's
  `ARCHITECTURE_MAP_TEMD.md` as the same thing — they are parallel templates
  for different layers (CTMv3 = workspace topology, somnus = Somnus-specific)
