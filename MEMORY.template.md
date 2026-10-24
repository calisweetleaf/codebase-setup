# %%PROJECT_NAME%% — MEMORY.md

**Purpose:** Durable repository memory: decisions, proven recoveries, lineage,
and non-obvious invariants.  
**Last synchronized:** %%CREATED_DATE%%  
**Current-state index:** CONTEXT.md  
**Entry router:** AGENTS.md

## Operating contract

This is append-oriented durable memory, not a transcript, scratchpad, secret
store, or substitute for current source. Store a finding only when it is likely
to prevent future rediscovery or changes a later decision. State evidence,
confidence, and authority. When later evidence contradicts an entry, append a
correction; do not rewrite history into a false smooth narrative.

Do not store credentials, private keys, raw personal data, unverified claims, or
routine command output.

## Retrieval index

| Topic | Canonical entry/date | Why it matters | Confidence |
|---|---|---|---|
| Initial Lock-In | %%CREATED_DATE%% | document roles and routing boundary established | high |

## %%CREATED_DATE%% — initial Lock-In

### Durable finding

AGENTS.md is the workspace router. filetree.md supplies spatial and dependency
awareness but is not a task dispatcher. CONTEXT.md carries current indexed state;
NOTEPAD.md carries append-only working deltas.

### Evidence and authority

Installed from Operator Lock-In templates. Target-specific architecture and
validation remain unknown until observed.

### Boundary

This establishes a preparation layer for Somnus Accelerate; it does not certify
that a project implementation, gate, provider capability, or host integration
already exists.

### Retrieval anchors

operator lockin, AGENTS-first, filetree not router, continuity, provider
projection, Somnus Accelerate boundary

## Canon and authority lock

| Domain | Authority | Notes |
|---|---|---|
| Current behavior | live source/configuration and consumed evidence | verify when cheap and drift-prone |
| Entry routing | AGENTS.md | repair when it contradicts current tree |
| Current state | CONTEXT.md plus newest NOTEPAD entry | synchronize after material changes |
| Durable history | this file | append corrections; do not overwrite |
| Structure | filetree.md | refresh after add/move/delete |
| Security/authority | OPSEC.md and explicit operator direction | external action remains explicit |

## Known anti-rediscovery hazards

| Hazard | Durable lesson |
|---|---|
| generic template fact | a template is structure, not evidence |
| provider capability claim | historical probe output expires; runtime evidence owns availability |
| premature tool equivalence | equivalent-looking operators may not share filesystem, shell, memory, or gateway access |
| document-only completion | documentation cannot replace consumed-boundary validation |
