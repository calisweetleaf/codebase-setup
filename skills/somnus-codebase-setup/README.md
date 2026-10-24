# somnus-codebase-setup

**Somnus codebase setup skill** — instantiates the 8 Somnus template surfaces from `filetree.md` into a live, agent-operable workspace, then builds Phase 5 CTMv3 ecosystem artifacts (`.sovereign/`, `.github/`, `.codex/`, `.pre-commit-config.yaml`).

Installs once globally, then runs from **any terminal** with `--repo <path>`. No `cd` into the target repo required.

Designed for **Codex** (primary), with Opencode and Droid compatible. No Claude. No ctm plugin hooks. No bb7 dependency.

---

## What it does

Given a repo that has the 8 Somnus template files (`*.template.md`) at its root, this skill:

1. **Detects boot state** — cold entry (no surfaces yet) vs. warm entry (surfaces exist, resume).
2. **Installs itself** into `.codex/skills/somnus-codebase-setup/` inside the target repo.
3. **Instantiates all 8 templates** into live surfaces — `AGENTS.md`, `MEMORY.md`, `CONTEXT.md`, `NOTEPAD.md`, `PROVENANCE.md`, `ARCHITECTURE.md`/`SPEC.md`, `ARCHITECTURE_MAP.md`, `DEVELOPMENT_SETUP.md` — plus `STATE.md`.
4. **Builds Phase 5 ecosystem artifacts** — `.sovereign/session_state.json`, `.sovereign/topology_fingerprint.txt`, `.sovereign/golden_paths.json`, `.github/copilot-instructions.md`, `.github/instructions/`, `.github/workflows/topology-enforce.yml`, `.codex/settings.json`, `.codex/CODEX.md`, `.pre-commit-config.yaml`.
5. **Records a session log row** in `PROVENANCE.md`.

Existing live surfaces are never overwritten (warm entry is safe and idempotent).

---

## Install

Install once, globally:

```bash
npm install -g /home/daeron/Desktop/test/codex/skills/somnus-codebase-setup
```

Verify:

```bash
somnus-codebase-setup --help
# or just run it:
somnus-codebase-setup --repo /path/to/somnus/repo --check
```

Requires Node.js >= 18.

---

## Usage

Run from **any terminal** — no `cd` into the target repo needed:

```bash
# Auto-detect cold vs warm entry (recommended)
somnus-codebase-setup --repo /path/to/somnus/repo

# Force cold entry — full template instantiation (fresh repo)
somnus-codebase-setup --repo /path/to/somnus/repo --cold

# Force warm entry — resume, never overwrite existing surfaces
somnus-codebase-setup --repo /path/to/somnus/repo --warm

# Dry-run — report what would be done, no writes
somnus-codebase-setup --repo /path/to/somnus/repo --check
```

You can also pass the repo as a positional argument:

```bash
somnus-codebase-setup /path/to/somnus/repo
```

---

## What gets created

### Live surfaces (from templates)

| Template | Live surface | Role |
|----------|-------------|------|
| `AGENTS.template.md` | `AGENTS.md` | Runtime router + transition grammar |
| `MEMORY.template.md` | `MEMORY.md` | Durable learned knowledge |
| `CONTEXT.template.md` | `CONTEXT.md` | Current indexed state router |
| `NOTEPAD.template.md` | `NOTEPAD.md` | External working memory |
| `PROVENANCE.template.md` | `PROVENANCE.md` | Decision log + session lineage |
| `ARCHITECTURE.template.md` | `ARCHITECTURE.md` / `SPEC.md` | Normative technical authority |
| `ARCHITECTURE_MAP_TEMPLATE.md` | `ARCHITECTURE_MAP.md` | Question-graph traversal map |
| `DEVELOPMENT_SETUP.template.md` | `DEVELOPMENT_SETUP.md` | Environment + `<GATE_COMMAND>` |
| — | `STATE.md` | Current runtime truth |

### Phase 5 ecosystem artifacts

| Artifact | Path | Role |
|----------|------|------|
| Session state | `.sovereign/session_state.json` | Codex session continuity |
| Topology fingerprint | `.sovereign/topology_fingerprint.txt` | Drift detection hash |
| Golden paths | `.sovereign/golden_paths.json` | Repo-specific bootstrap chains |
| PROVENANCE mirror | `.sovereign/PROVENANCE.md` | Stub → root `PROVENANCE.md` |
| Agent context | `.github/copilot-instructions.md` | Repo-wide instruction |
| Per-path instructions | `.github/instructions/{backend,tests}.instructions.md` | Path-scoped context |
| CI enforcement | `.github/workflows/topology-enforce.yml` | Placeholder + gate checks |
| Codex settings | `.codex/settings.json` | Permissions + env |
| Codex context | `.codex/CODEX.md` | Extends `AGENTS.md` |
| Pre-commit gate | `.pre-commit-config.yaml` | Local placeholder + provenance checks |

---

## How it chains with CTMv3

This skill is a **domain skill** under the **@skills/ctmv3** meta-framework. They remain two separate skills:

| Skill | Role |
|-------|------|
| `@skills/ctmv3` | Boot protocol (cold/warm detection), topology construction, failure grammar, provenance |
| `somnus-codebase-setup` | Somnus template instantiation domain skill |

**Runtime chain:**

```
CTMv3 BOOT_PROTOCOL.md (cold/warm detection)
    → somnus-codebase-setup (template instantiation)
    → CTMv3 Phase 5 ecosystem artifacts
```

CTMv3 is detected automatically if present at `skills/ctmv3/` or `~/.codex/skills/ctmv3/`. If absent, the skill runs in standalone mode.

---

## Codex-first workflow

This skill is optimized for Codex:

```bash
# Install once
npm install -g /home/daeron/Desktop/test/codex/skills/somnus-codebase-setup

# Set up a new Somnus repo from any terminal
somnus-codebase-setup --repo /home/daeron/Projects/my-somnus-repo --cold

# Then, inside the repo, Codex reads:
#   AGENTS.md          → Start of Session sequence
#   STATE.md           → current runtime truth
#   NOTEPAD.md         → working deltas
#   CONTEXT.md         → current indexed state
#   MEMORY.md          → durable knowledge
#   PROVENANCE.md      → decision log + session history
#   ARCHITECTURE_MAP.md → traversal map (where is X?)
#   DEVELOPMENT_SETUP.md → <GATE_COMMAND>
```

No Claude. No `.claude/`. `.codex/` is the Codex operational directory.

---

## Validation

A codebase is considered "Somnus-setup" when:

- [ ] All 9 live surfaces exist with non-placeholder content
- [ ] `filetree.md` reflects current structure
- [ ] `<GATE_COMMAND>` is defined in `DEVELOPMENT_SETUP.md`
- [ ] Gate command runs and exits 0
- [ ] `.sovereign/`, `.github/`, `.codex/`, `.pre-commit-config.yaml` are present

---

## License

UNLICENSED — internal Somnus Sovereign Systems tooling. Not for public distribution.

---

## Files

```
skills/somnus-codebase-setup/
├── README.md            # this file
├── LICENSE
├── package.json
├── .gitignore
├── SKILL.md             # canonical cognitive topology map
├── ctmv3-chain.md       # cross-skill chain documentation
├── bin/
│   └── somnus-codebase-setup   # executable entry point
└── nodes/
    ├── template-field.md
    ├── authority-field.md
    ├── failure-grammar.md
    ├── entry-vectors.md
    ├── provenance.md
    └── ctmv3-chain.md
```
