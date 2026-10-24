# Somnus Codex — Skill Package

This repo is the **somnus-codebase-setup** skill package: a Cognitive Topology Map (CTM) domain skill that turns the 8 Somnus template surfaces in `filetree.md` into a live, agent-operable workspace, then builds Phase 5 CTMv3 ecosystem artifacts.

**Optimized for Codex.** Opencode and Droid compatible. No Claude. No ctm plugin hooks. No bb7 dependency.

## What's in this repo

| Path | Purpose |
|------|---------|
| `filetree.md` | Generated structural map of the repo |
| `AGENTS.template.md` | → `AGENTS.md` (runtime router) |
| `MEMORY.template.md` | → `MEMORY.md` (durable knowledge) |
| `CONTEXT.template.md` | → `CONTEXT.md` (current indexed state) |
| `NOTEPAD.template.md` | → `NOTEPAD.md` (external working memory) |
| `PROVENANCE.template.md` | → `PROVENANCE.md` (decision log + session lineage) |
| `ARCHITECTURE.template.md` | → `ARCHITECTURE.md` / `SPEC.md` (normative authority) |
| `ARCHITECTURE_MAP_TEMPLATE.md` | → `ARCHITECTURE_MAP.md` (traversal map) |
| `DEVELOPMENT_SETUP.template.md` | → `DEVELOPMENT_SETUP.md` (environment + gate) |
| `skills/somnus-codebase-setup/` | The installable skill package |
| `skills/ctmv3/` | CTMv3 meta-framework (boot protocol, topology, failure grammar) |

## Install the skill

```bash
# From any terminal, install once globally
npm install -g /home/daeron/Desktop/test/codex/skills/somnus-codebase-setup

# Then set up any Somnus repo — no cd required
somnus-codebase-setup --repo /path/to/somnus/repo --cold

# Warm resume (idempotent, never overwrites existing surfaces)
somnus-codebase-setup --repo /path/to/somnus/repo --warm

# Dry-run to preview
somnus-codebase-setup --repo /path/to/somnus/repo --check
```

See `skills/somnus-codebase-setup/README.md` for the full install + usage guide.

## Requirements

- Node.js >= 18

## License

UNLICENSED (public domain) — internal Somnus Sovereign Systems tooling.
