PROVENANCE — [PROJECT / REPOSITORY NAME]

Loaded by: [Agents / tools / workflows that should read this file]
Purpose: record decisions, session lineage, rejected paths, integration history, and next-state handoff so agents do not re-discover the repository from zero.

---

Snapshot Lineage

Version| Date| Source| Changes from Previous
v0.1| YYYY-MM-DD| [Agent / Operator / Tool]| Initial repository state / activation / baseline.
v0.2| YYYY-MM-DD| [Source]| [Concise description of material changes.]

Current authoritative snapshot: "[VERSION]" — "YYYY-MM-DD"

Current state:
[Concise statement of current executable/runtime/project state. Describe what is implemented, what is active, and any important known gaps.]

Current topology / fingerprint / revision:
[Git commit, topology hash, schema version, model version, run ID, or other identity marker.]

---

Architectural Decisions (Chronological)

Decision 1: [Short Decision Title]

Date: YYYY-MM-DD

Context:
[What condition, discovery, requirement, or problem caused this decision to be necessary?]

Decision:
[What was decided? State the actual architectural or operational rule.]

Implication:
[What must future agents/code/workflows now preserve or do differently?]

---

Decision 2: [Short Decision Title]

Date: YYYY-MM-DD

Context:
[Context.]

Decision:
[Decision.]

Implication:
[Implication.]

---

Decision N: [Short Decision Title]

Date: YYYY-MM-DD

Context:
[Context.]

Decision:
[Decision.]

Implication:
[Implication.]

---

Rejected Alternatives (Graveyard)

Rejected: [Alternative / Architecture / Approach]

Why it looked appealing:
[Why an agent or developer might reasonably choose this.]

Why rejected:
[Technical, architectural, operational, scientific, or security reason.]

Status: Rejected.

Reconsider only if:
[Optional. Explicit condition that would justify reopening this path.]

---

Rejected: [Alternative]

Why it looked appealing:
[Reason.]

Why rejected:
[Reason.]

Status: Rejected.

---

Open Questions

Question| Current Assumption| Impact if Wrong
[Open architectural/runtime question]| [Working assumption]| [What breaks or changes if assumption is false?]
[Question]| [Assumption]| [Impact]

Open questions are not permission for silent architectural invention.

When an open question becomes resolved, move the resolution into Architectural Decisions and update/remove the corresponding row here.

---

Integration History

Module / Artifact| Source| Integrated| Status| Notes
"[path/or/component]"| [Current repo / imported system / operator]| YYYY-MM-DD| Active| [Role and current runtime status.]
"[component]"| [Source]| YYYY-MM-DD| Partial| [What exists and what remains.]
"[artifact]"| [Source]| YYYY-MM-DD| Design only| [Not currently executable / not runtime input.]

Suggested status vocabulary:

- Active — executable and part of the current authoritative path.
- Partial — materially implemented but incomplete.
- Diagnostic — used for validation/inspection only.
- Design only — specified but not runtime-active.
- Deprecated — superseded but retained for history.
- Rejected — intentionally excluded.
- Blocked — intended but currently prevented by a known dependency.

Do not mark something Active merely because the file exists.

---

Session Log

Date| Agent| Action| Topology Drift?| Next Recommended Action
YYYY-MM-DD| [Agent]| [What actually changed or was verified.]| no / yes / yes-docs / resolved| [Concrete next action.]
YYYY-MM-DD| [Agent]| [Action.]| [Status]| [Next action.]

Each meaningful agent session should append one row.

The row should describe what actually happened, not what the agent intended to do.

If a session modifies architectural boundaries, runtime topology, authority hierarchy, artifact formats, execution paths, or agent-operating rules, mark topology drift accordingly.

---

[YYYY-MM-DD] Addendum — [Subject]

[Use addenda for substantial session findings or operational details that are too large for the Session Log but do not warrant a new architectural decision.]

Discovery / change:
[What was found or changed.]

Current behavior:
[What the executable system now does.]

Validation:
[Tests, commands, runs, artifacts, hashes, commits, or other evidence.]

Boundary:
[What this does not mean. Prevent overclaiming.]

Next state:
[What the next agent should do.]

---

[YYYY-MM-DD] Addendum — Validation State

Environment:

- Runtime: "[Python / Node / CUDA / etc.]"
- Environment path: "[.venv / container / host]"
- Hardware: "[relevant hardware]"
- Commit: "[git SHA]"

Validation performed:

- "[command]" → "[result]"
- "[command]" → "[result]"
- "[command]" → "[result]"

Known failures:

- [Failure]
- [Failure]

Preserved evidence:

- "[path/to/log]"
- "[path/to/run]"
- "[path/to/artifact]"

---

[YYYY-MM-DD] Addendum — Runtime / Architecture Boundary

Canonical path:

[input]
   ↓
[layer / loader]
   ↓
[router / coordinator]
   ↓
[core runtime]
   ↓
[integration / compiler]
   ↓
[artifact / output]

Authoritative components:

- "[component]"
- "[component]"
- "[component]"

Non-authoritative / historical components:

- "[component]"
- "[component]"

Invariant:
[Single sentence describing what future agents must not violate.]

---

Provenance Maintenance Rules

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

---

Handoff State

Current objective:
[Exact active objective.]

Current blocker:
[None / specific blocker.]

Last completed state:
[What is definitely complete.]

Next required action:
[One concrete next action.]

Do not redo:

- [Already completed work.]
- [Validated work.]
- [Rejected approach.]

Must reread before continuing:

- "[AGENTS.md]"
- "[OPSEC.md]"
- "[MEMORY.md]"
- "[authoritative specification]"
- "[current plan]"
- "[STATE/HANDOFF file]"

Resume from:
[Commit / run ID / checkpoint / file / phase.]

---

End of current provenance record.

## Session Log (appended by somnus-codebase-setup)

| Date | Agent | Action | Topology Drift? | Next Recommended Action |
|------|-------|--------|----------------|------------------------|
2026-10-24|somnus-codebase-setup|instantiated Somnus template surfaces + STATE.md|no|run gate command and validate


## Session Log (appended by somnus-codebase-setup)

| Date | Agent | Action | Topology Drift? | Next Recommended Action |
|------|-------|--------|----------------|------------------------|
2026-10-24|somnus-codebase-setup|instantiated Somnus template surfaces + STATE.md|no|run gate command and validate


## Session Log (appended by somnus-codebase-setup)

| Date | Agent | Action | Topology Drift? | Next Recommended Action |
|------|-------|--------|----------------|------------------------|
2026-10-24|somnus-codebase-setup|instantiated Somnus template surfaces + STATE.md + Phase 5 ecosystem artifacts|no|run gate command and validate


## Session Log (appended by somnus-codebase-setup)

| Date | Agent | Action | Topology Drift? | Next Recommended Action |
|------|-------|--------|----------------|------------------------|
2026-10-24|somnus-codebase-setup|instantiated Somnus template surfaces + STATE.md + Phase 5 ecosystem artifacts|no|run gate command and validate
