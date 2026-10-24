# SKILL: somnus-codebase-setup

**Id:** somnus-codebase-setup
**Category:** somnus-infrastructure / codebase-bootstrap
**Trigger:** Setting up a new Somnus codebase; bringing a template field online; recovering a codebase that lacks its continuity surfaces; converting a raw repo into an agent-operable Somnus workspace.
**Authority:** Somnus Sovereign Systems — Morpheus Advanced Intelligence Labs
**Status:** IN_PROGRESS (first lock-in)
**Template source:** `filetree.md` (8 templates) in repo root
**Meta-framework:** @skills/ctmv3 (CTMv3 boot protocol + workspace activation)
**Chain:** CTMv3 boot → somnus-codebase-setup instantiation → CTMv3 Phase 5
**Install:** `npm install -g /path/to/skills/somnus-codebase-setup`
**Run:** `somnus-codebase-setup --repo /path/to/target/repo` (from any terminal)

---

## What this skill is

This is a Cognitive Topology Map (CTM) skill. It does **not** produce a procedure, a checklist, or a step-by-step script. It encodes the **navigable domain structure** of how Somnus codebases are set up from the 8 template surfaces listed in `filetree.md`:

| Template | Live surface | Primary role |
|----------|--------------|--------------|
| `AGENTS.template.md` | `AGENTS.md` | Runtime router + transition grammar |
| `ARCHITECTURE.template.md` | `ARCHITECTURE.md` / `SPEC.md` | Normative technical authority + codebase whitepaper |
| `ARCHITECTURE_MAP_TEMPLATE.md` | `ARCHITECTURE_MAP.md` | Question-graph traversal map |
| `CONTEXT.template.md` | `CONTEXT.md` | Current indexed state router |
| `DEVELOPMENT_SETUP.template.md` | `DEVELOPMENT_SETUP.md` | Environment + runtime contract |
| `MEMORY.template.md` | `MEMORY.md` | Durable learned knowledge |
| `NOTEPAD.template.md` | `NOTEPAD.md` | External working memory |
| `PROVENANCE.template.md` | `PROVENANCE.md` | Decision log + session lineage |

Each surface is a **node** in a field of functional relations: some preserve, some project, some constrain, some condition, some expose, some narrow, some recall, some trigger. The skill is the map of that field.

A model operating in this field does **not** experience "I must obey AGENTS.md which governs everything." It experiences:

- "This template tells me what surface to instantiate" (PROJECTS + CONSTRAINS)
- "This gate tells me if my setup is complete" (BINARY COMPLETION SIGNAL)
- "This filetree tells me where files live" (EXPOSES + SPATIAL AWARENESS)
- "This NOTEPAD entry tells me what the last session did" (RECALLS + CROSS-SESSION STATE CARRY)
- "This hard ban tells me what NOT to build" (NARROWS + CONSTRAINS)
- "This provenance entry tells me why a decision was made" (PRESERVES + LINEAGES)

None require a global authority hierarchy. Each is a local functional relation. Together they form an acceleration field around agent intelligence.

---

## Load-bearing concepts

### 1. AGENTS.md is the router, not the spec

AGENTS.md tells an entering operator how to inhabit the repository. Its rough responsibility split is:

- ~25% project-specific rules — invariants, local doctrine, hard bans, project semantics, authority ordering
- ~25% concrete runtime/environment knowledge — virtual environments, build/test commands, platform quirks, generated files, local tooling, paths that must or must not be touched
- ~50% navigation/orchestration — what to read first, how persistent files relate, how to recover state, how to choose the next action, how to validate, persist, and hand off

AGENTS.md is closer to a project-local state machine than a generic instruction sheet. It should rarely contain deep implementation detail that belongs in SPEC.md, STATE.md, MEMORY.md, or CONTEXT.md.

### 2. filetree.md is spatial awareness, not a dispatcher

filetree.md gives an agent the structural map before they wander. Use it before wandering. It makes implementation centers, tests, generated artifacts, documentation, proof/validation surfaces, historical material, and project-local tooling easy to locate.

Refresh it when structural changes make the existing tree materially stale. **A stale file tree is a navigation bug.** filetree.md does **not** tell you what to do next — AGENTS.md does.

### 3. State surfaces form a hierarchy, not a monolith

```
AGENTS.md → NOTEPAD.md → CONTEXT.md → MEMORY.md
```

- AGENTS.md tells the agent how to operate.
- NOTEPAD.md externalizes active working state while operating (append-only scratch).
- CONTEXT.md indexes durable state that survives the turn (current indexed state).
- MEMORY.md stores deep durable findings, provenance, architecture truth, failures, verification, historical strata.

Do not duplicate across them. Each has a distinct semantic role and a promotion path: NOTEPAD → CONTEXT → MEMORY.

### 4. SPEC.md is normative; STATE.md is current truth

SPEC.md defines intended architecture, semantics, contracts, invariants, required behavior, system boundaries, canonical terminology.

STATE.md answers: what exists now, what is implemented, what is incomplete, what currently passes, what currently fails, what the active frontier is, what is blocked, what changed most recently, what the next justified action appears to be.

STATE.md is **not** a roadmap and **not** historical memory. Update it whenever runtime truth materially changes.

When implementation and SPEC disagree, investigate the disagreement rather than automatically assuming either side is correct. A stale spec must be updated deliberately, not silently bypassed.

### 5. ANTITHESIS.md is accumulated immunity

Records rejected architectural directions, known failure grammars, false equivalences, anti-goals, dangerous simplifications, tempting but invalid abstractions, patterns that previously caused drift. Check before introducing a familiar pattern, abstraction, framework, or refactor. It reduces search space. It is not pessimism — it is accumulated immunity.

---

## The authority field (functional relations)

Surfaces relate through functional relations, not single-source authority:

| Surface | Relation | What it does in setup |
|---------|----------|----------------------|
| AGENTS.md | CONSTRAINS + ROUTES | Bounded work definition; tells entering operator how to inhabit |
| ARCHITECTURE.md / SPEC.md | CONSTRAINS | Normative authority; intended architecture |
| ARCHITECTURE_MAP.md | NAVIGATES | Question graph; reach any component within 3 hops |
| CONTEXT.md | RECALLS + INDEXES | Current indexed state; rapid future routing |
| DEVELOPMENT_SETUP.md | CONDITIONS | Environment + runtime contract; gates execution |
| MEMORY.md | RECALLS + PRESERVES | Durable knowledge; prevents rediscovery |
| NOTEPAD.md | RECALLS (transient) + CARRIES | Cross-session state carry; external scratch |
| PROVENANCE.md | PRESERVES + LINEAGES | Decision log, session history, rejected paths |
| filetree.md | EXPOSES | Structural topology; spatial awareness before wandering |
| STATE.md | EXPOSES + TRIGGERS | Current runtime truth; tells what changed |

---

## Entry vectors

### Cold entry — repo has no Somnus surfaces yet

1. **Read the operator's explicit current instruction** — highest authority.
2. **Instantiate AGENTS.md** from `AGENTS.template.md` — fill Project identity, Behavioral constitution, Operating rules, Authority + Conflict Resolution, Start of Session sequence, Validation, Hard Bans.
3. **Instantiate filetree.md** — run the tree generator so spatial awareness exists before any wandering.
4. **Instantiate CONTEXT.md** from `CONTEXT.template.md` — set Workspace state, Active delivery surface, Current branch/revision, Active packet, Last meaningful validation, Main unresolved variable.
5. **Instantiate MEMORY.md** from `MEMORY.template.md` — record Initial Lock-In entry + Canon/authority lock.
6. **Instantiate NOTEPAD.md** from `NOTEPAD.template.md` — leave an OPEN entry describing the setup task.
7. **Instantiate PROVENANCE.md** from `PROVENANCE.template.md` — record v0.1 snapshot + Initial Lock-In decision + Session Log header.
8. **Instantiate STATE.md** (required by AGENTS.md but not in the template list) — current runtime truth.
9. **Instantiate ARCHITECTURE.md / SPEC.md** from `ARCHITECTURE.template.md` — normative authority.
10. **Instantiate ARCHITECTURE_MAP.md** from `ARCHITECTURE_MAP_TEMPLATE.md` — traversal map with ROOT + branches + file:line anchors.
11. **Instantiate DEVELOPMENT_SETUP.md** from `DEVELOPMENT_SETUP.template.md` — environment + `<GATE_COMMAND>`.
12. **Run the gate / narrowest validation.** Update STATE.md.
13. **Refresh filetree.md** after all structural instantiations.

### Warm entry — repo already has Somnus surfaces

1. Read AGENTS.md.
2. Read STATE.md.
3. Read newest NOTEPAD.md entry.
4. Read relevant SPEC.md sections for the active frontier.
5. Read ANTITHESIS.md for known invalid directions.
6. Read filetree.md.
7. Consult MEMORY.md and CONTEXT.md for the specific subsystem/problem.
8. Read active TASK.md / PLAN.md packet if one exists.
9. Inspect actual implementation and tests.
10. Run the project gate or narrowest meaningful validation command.

Do not repeatedly reread solved history when persistent project state already contains the needed result.

---

## Node catalog

Each node below is a navigable concept. Enter at the node matching what you need to understand.

### Node: AGENTS (runtime router)
- **Role:** Entry point for every session; state machine for inhabiting the repo
- **Load-bearing:** authority order, recovery sequence, working loop (`observe → orient → act → validate → persist → derive next`), hard bans, validation gate
- **Connects to:** all surfaces (routes to them)
- **Update trigger:** operating doctrine, navigation, or environment truth changes

### Node: SPEC / ARCHITECTURE (normative authority)
- **Role:** intended architecture, semantics, contracts, invariants
- **Load-bearing:** in-scope/out-of-scope, component breakdown, data structures, integration challenges, operational hazards
- **Connects to:** AGENTS (router references it), STATE (truth comparison), ANTITHESIS (rejected directions)
- **Update trigger:** intentional normative truth change only

### Node: ARCHITECTURE_MAP (traversal graph)
- **Role:** question graph; any component within 3 hops; file + line anchors required
- **Load-bearing:** ROOT question ("what is this system"), 5–8 BRANCH questions, Quick Reference table (question → file:line), lateral navigation pointers between branches
- **Connects to:** SPEC (it maps the architecture), filetree (structural index)
- **Update trigger:** new modules/classes added, functions moved/renamed, layers added/removed, new data artifacts

### Node: CONTEXT (current indexed state)
- **Role:** structured index linking to primary evidence; not raw history; current executable evidence outranks this document
- **Load-bearing:** Current snapshot table, Architecture index, Authority/provenance index, Active hazards, Resume route
- **Connects to:** AGENTS (entry router), NOTEPAD (newest entry), STATE (current truth)
- **Update trigger:** current state or validation evidence changed

### Node: DEVELOPMENT_SETUP (environment contract)
- **Role:** prerequisites, setup steps, virtual environment, testing framework, project structure, development workflow, CI/CD
- **Load-bearing:** `<GATE_COMMAND>`, environment paths, package manager, supported platforms, required external services, local quirks
- **Connects to:** AGENTS (Environment section), STATE (what passes/fails)
- **Update trigger:** runtime/environment truth changes

### Node: MEMORY (durable knowledge)
- **Role:** append-oriented durable memory; prevents rediscovery; not a transcript, scratchpad, secret store, or substitute for current source
- **Load-bearing:** Retrieval index, Canon/authority lock, Known anti-rediscovery hazards
- **Connects to:** NOTEPAD (promotion target), CONTEXT (current-state index), AGENTS (entry router)
- **Update trigger:** durable knowledge learned; corrections appended, never overwritten

### Node: NOTEPAD (external working memory)
- **Role:** active operator's external scratch surface; append-only workbook; not canon, not authoritative
- **Load-bearing:** Workbook contract, Write triggers, Entry identity, Checkpoint forms (full / micro / discovery / failure / deferred / hypothesis / before-edit / post-slice / multi-agent handoff / validate / close / correction), Promotion rules (NOTEPAD → CONTEXT → MEMORY), Anti-patterns
- **Connects to:** CONTEXT (promote compressed keys), MEMORY (promote durable findings), AGENTS (hierarchy position)
- **Update trigger:** continuously during work; before/after substantial edits; at every write trigger

### Node: PROVENANCE (decision log + lineage)
- **Role:** decisions, session lineage, rejected paths, integration history, next-state handoff so agents do not re-discover the repository from zero
- **Load-bearing:** Snapshot Lineage, Architectural Decisions (chronological), Rejected Alternatives (graveyard), Open Questions, Integration History, Session Log, Addenda, Handoff State, Provenance Maintenance Rules
- **Connects to:** MEMORY (durable history), AGENTS (session continuity), STATE (current authoritative snapshot)
- **Update trigger:** after meaningful work; session log row; addenda for detailed evidence

### Node: filetree (structural topology)
- **Role:** navigable structural map; implementation centers, tests, generated artifacts, docs, proof/validation surfaces, historical material, project-local tooling
- **Load-bearing:** current tree; refresh on structural change
- **Connects to:** AGENTS (recovery step 6), ARCHITECTURE_MAP (Quick Reference uses file paths)
- **Update trigger:** after add/move/delete

### Node: STATE (current runtime truth)
- **Role:** what exists now, implemented/incomplete/passes/fails/active frontier/blocked/recent change/next justified action
- **Load-bearing:** runtime truth table
- **Connects to:** AGENTS (recovery step 2), SPEC (truth comparison), MEMORY (not historical memory)
- **Update trigger:** whenever runtime truth materially changes

---

## Failure grammar (what goes wrong during setup)

| Failure | Symptom | First response |
|---------|---------|----------------|
| Template treated as evidence | Copying placeholder text (`<replace>`, `%%PROJECT_NAME%%`, `[Project name goes here]`) into a live repo as if it were real state | Treat template as structure only; replace every placeholder with live evidence |
| AGENTS.md becomes a spec dump | Deep implementation detail in AGENTS.md; navigation buried under code detail | Move implementation detail to SPEC.md/STATE.md; keep AGENTS.md as router |
| NOTEPAD → MEMORY skip | Durable findings left only in NOTEPAD.md, never promoted | Promote to CONTEXT.md then MEMORY.md on durable findings |
| Stale filetree | Navigation points to missing/renamed files | Regenerate filetree.md after every structural change |
| SPEC/STATE drift | Implementation contradicts SPEC; STATE not updated when truth changes | Investigate disagreement; repair deliberately; update STATE.md on material change |
| No gate defined | No validation command; changes "landed" by edit alone | Define `<GATE_COMMAND>` in DEVELOPMENT_SETUP.md; gate must PASS before handoff |
| Authority inversion | Generated prose / NOTEPAD outranks live source | Enforce authority order: operator instruction → live source → SPEC → STATE → contracts/tests → ANTITHESIS → MEMORY → CONTEXT → task surfaces → NOTEPAD → generated prose |

---

## Provenance chains (template → live surface)

Each template has a provenance chain: where it came from, when integrated, what it produces:

- `AGENTS.template.md` → `AGENTS.md` — router doctrine; updated when operating doctrine/navigation/environment truth changes
- `ARCHITECTURE.template.md` → `ARCHITECTURE.md` / `SPEC.md` — normative authority; updated only when normative truth intentionally changes
- `ARCHITECTURE_MAP_TEMPLATE.md` → `ARCHITECTURE_MAP.md` — traversal map; updated on structural/module changes
- `CONTEXT.template.md` → `CONTEXT.md` — current state index; updated when current state or validation evidence changes
- `DEVELOPMENT_SETUP.template.md` → `DEVELOPMENT_SETUP.md` — environment contract; updated when runtime/environment truth changes
- `MEMORY.template.md` → `MEMORY.md` — durable knowledge; append corrections, never overwrite
- `NOTEPAD.template.md` → `NOTEPAD.md` — working scratch; append-only; promote durable findings upward
- `PROVENANCE.template.md` → `PROVENANCE.md` — decision log; append history; session log row after meaningful work

---

## Validation (gate)

A codebase is **Somnus-setup** when all of the following hold:

- [ ] `AGENTS.md` exists and loads at session start (Project identity + Behavioral constitution + Operating rules + Authority order + Start of Session sequence + Validation section)
- [ ] `filetree.md` exists and reflects current structure (not stale)
- [ ] `CONTEXT.md` exists with Current snapshot + Architecture index + Resume route
- [ ] `MEMORY.md` exists with Initial Lock-In entry + Canon/authority lock
- [ ] `NOTEPAD.md` exists with Workbook contract + at least one OPEN entry
- [ ] `PROVENANCE.md` exists with v0.1 snapshot + Initial Lock-In decision + Session Log header
- [ ] `STATE.md` exists with current runtime truth
- [ ] `SPEC.md` / `ARCHITECTURE.md` exists with normative authority
- [ ] `ARCHITECTURE_MAP.md` exists with ROOT + branches + file:line anchors
- [ ] `DEVELOPMENT_SETUP.md` exists with `<GATE_COMMAND>` defined
- [ ] Gate command runs and PASSES (exit 0)
- [ ] No template placeholders (`%%`, `<replace>`, `[Project name goes here]`, `replace`) remain in live files
- [ ] `filetree.md` refreshed after all instantiations

Expected output: running `<GATE_COMMAND>` exits 0; all template-derived surfaces are present with live (non-placeholder) content; a cold-entering agent can recover state using the Start of Session sequence without reconstructing the project.

---

## Exit report

After setup lands, record in `PROVENANCE.md` Session Log:

```
Base: <commit / tree identity>
Did: instantiated all 8 template surfaces + STATE.md
Validation: <gate command> → <result>
Proof facts: surface count = 9; placeholder count = 0; gate exit code = 0
Next agent: read AGENTS.md → resume per Start of Session sequence
Hazards: any template placeholders missed; gate not yet defined
```

Then refresh `filetree.md` and update `STATE.md` to mark setup complete.
