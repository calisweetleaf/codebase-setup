# Node: provenance

**Parent skill:** somnus-codebase-setup
**Kind:** provenance chains
**Status:** locked

## What this node is

Provenance records where each template came from, when it was integrated, and what live surface it produces. It prevents agents from re-discovering the repository from zero and preserves the reason behind architecture changes, not only the diff.

## Template → live surface provenance chains

| Template | Projects into | What it produces | When updated |
|----------|---------------|------------------|--------------|
| `AGENTS.template.md` | `AGENTS.md` | Router doctrine: authority order, recovery sequence, working loop, hard bans, validation gate | When operating doctrine, navigation, or environment truth changes |
| `ARCHITECTURE.template.md` | `ARCHITECTURE.md` / `SPEC.md` | Normative authority: intended architecture, semantics, contracts, invariants, hazards | Only when normative truth intentionally changes |
| `ARCHITECTURE_MAP_TEMPLATE.md` | `ARCHITECTURE_MAP.md` | Traversal map: ROOT question, BRANCH questions, file:line anchors, Quick Reference | When new modules/classes added, functions moved/renamed, layers changed, new data artifacts |
| `CONTEXT.template.md` | `CONTEXT.md` | Current state index: snapshot, architecture index, authority/provenance index, hazards, resume route | When current state or validation evidence changes |
| `DEVELOPMENT_SETUP.template.md` | `DEVELOPMENT_SETUP.md` | Environment contract: prerequisites, setup steps, testing, `<GATE_COMMAND>` | When runtime/environment truth changes |
| `MEMORY.template.md` | `MEMORY.md` | Durable knowledge: retrieval index, canon/authority lock, anti-rediscovery hazards | Append corrections; never overwrite |
| `NOTEPAD.template.md` | `NOTEPAD.md` | Working scratch: workbook contract, checkpoint forms, promotion rules | Continuously during work; append-only |
| `PROVENANCE.template.md` | `PROVENANCE.md` | Decision log: snapshot lineage, decisions, rejected paths, integration history, session log, handoff | After meaningful work; session log row per session |

## What to record during setup

In `PROVENANCE.md` Session Log, after setup lands:

```
### <DATE> — <agent> — setup
- Base: <commit / tree identity>
- Did: instantiated all 8 template surfaces + STATE.md
- Validation: <gate command> → <result>
- Proof facts: surface count = 9; placeholder count = 0; gate exit code = 0
- Next agent: read AGENTS.md → resume per Start of Session sequence
- Hazards: any template placeholders missed; gate not yet defined
```

Add an Architectural Decision for each template choice (e.g., why AGENTS.md is the router, why NOTEPAD → CONTEXT → MEMORY promotion path).

Add a Rejected Alternative for any setup pattern you considered but rejected (e.g., "single monolithic rules file" rejected because surfaces must have distinct semantic roles).

## Maintenance rules

1. Append history. Do not silently rewrite it.
2. Correct old statements by recording the correction and superseding state.
3. Record decisions separately from implementation status.
4. A file existing does not establish that it is runtime-active.
5. A test passing does not establish architectural completeness unless the test exercises that architecture.
6. Preserve rejected paths so future agents do not repeatedly rediscover them.
7. Record the reason behind architecture changes, not only the diff.
8. Update Current authoritative snapshot whenever a material repository state becomes the new baseline.
9. Add a Session Log row after meaningful work.
10. Use addenda for detailed evidence that would make the chronological tables unreadable.
11. Keep current runtime truth distinguishable from historical claims.
12. Never use provenance documentation to redefine an external architectural authority such as a specification, whitepaper, protocol, or operator instruction.

Entry vector: enter when recording setup decisions, after a session, or when you need to know why a surface exists the way it does.

Next nodes: `authority-field.md` (which surface holds what authority), `template-field.md` (what each template projects).
