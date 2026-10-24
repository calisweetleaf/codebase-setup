# Node: ctmv3-chain

**Parent skill:** somnus-codebase-setup
**Kind:** cross-skill chain
**Status:** locked

## What this node is

Documents how `somnus-codebase-setup` chains with `@skills/ctmv3`. They remain
two separate skills. CTMv3 is the meta-framework engine; somnus-codebase-setup
is a domain skill that runs under it.

## Chain topology

```
CTMv3 (meta-framework)
├── BOOT_PROTOCOL.md          ← cold/warm entry detection (runs first)
├── Phase 0-5                 ← workspace activation (archaeology → ecosystem)
│   ├── Phase 5 ecosystem     ← .github/, .claude/, .codex/, .sovereign/
│   └── ARCHITECTURE_MAP.md   ← traversal map (CTMv3 template)
└── semantic router           ← routes task types to docs

somnus-codebase-setup (domain skill)
├── template-field.md         ← 8 Somnus templates → live surfaces
├── entry-vectors.md          ← cold/warm entry for Somnus setup
├── failure-grammar.md        ← setup-specific pre-failure signatures
├── provenance.md             ← template → live surface chains
└── authority-field.md        ← functional relations between Somnus surfaces

Runtime flow:
  CTMv3 boot → somnus-codebase-setup template instantiation → CTMv3 Phase 5
```

## Entry point rule

Always load CTMv3 `SKILL.md` first for boot-state detection. Then load
`somnus-codebase-setup/SKILL.md` for domain-specific template knowledge.
Never load somnus-codebase-setup without first determining cold vs warm entry
via CTMv3 `BOOT_PROTOCOL.md`.

## Next node

From this node: `entry-vectors.md` (the actual setup sequence), `template-field.md` (what each template projects).
