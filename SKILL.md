# Somnus Skill Index — codex

This repo exposes one skill: **somnus-codebase-setup**.

Canonical skill file: `skills/somnus-codebase-setup/SKILL.md`

Entry vector: load `skills/somnus-codebase-setup/SKILL.md` when setting up a new Somnus codebase, bringing a template field online, or recovering a repo that lacks its continuity surfaces.

Skill node files live under `skills/somnus-codebase-setup/nodes/`:
- `template-field.md` — each template's load-bearing role
- `authority-field.md` — functional relations between surfaces
- `failure-grammar.md` — what goes wrong during setup
- `entry-vectors.md` — cold and warm entry sequences
- `provenance.md` — template → live surface provenance chains
- `ctmv3-chain.md` — how this skill chains with @skills/ctmv3

## Cross-skill chain

This skill chains with **@skills/ctmv3** (the CTMv3 meta-framework engine). They
remain two separate skills:

- **@skills/ctmv3** — boot protocol (cold/warm entry), workspace activation,
  topology construction, failure grammar, provenance, ecosystem artifacts
  (`.github/`, `.claude/`, `.codex/`, `.sovereign/`)
- **somnus-codebase-setup** — Somnus template instantiation domain skill

Runtime chain: `CTMv3 BOOT_PROTOCOL.md` (cold/warm detection) →
`somnus-codebase-setup` template instantiation → `CTMv3 Phase 5` ecosystem
artifacts. See `skills/somnus-codebase-setup/ctmv3-chain.md` for full chain
documentation.

## npx-installable / global install

Install once, then run from any terminal without `cd`-ing:

```bash
# Install once (global)
npm install -g /home/daeron/Desktop/test/codex/skills/somnus-codebase-setup

# Run from ANY terminal — no cd required
somnus-codebase-setup --repo /path/to/somnus/repo          # cold or warm, auto-detected
somnus-codebase-setup --repo /path/to/somnus/repo --cold   # force cold entry
somnus-codebase-setup --repo /path/to/somnus/repo --warm   # force warm entry
somnus-codebase-setup --repo /path/to/somnus/repo --check  # dry-run, no writes
```

It installs itself into `.codex/skills/somnus-codebase-setup/` inside the target
repo and builds Phase 5 ecosystem artifacts (`.sovereign/`, `.github/`,
`.claude/`, `.pre-commit-config.yaml`) — no ctm plugin hooks, no bb7
dependency. Available to Codex, Claude Code, Droid, and OpenCode.
