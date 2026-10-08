# The score inside each project: local memory

**Language / Idioma:** English | [Espanol](../07-memoria-de-proyecto.md)

Can I Play with Madness? Switching engines becomes manageable when the project
can explain where work stopped.

## What memory means

External documents preserve decisions and continuity after a chat ends. An agent
reads them at start and updates them after a changed work session. The operational
source still takes precedence over an old note.

## Illustrative anatomy

```text
project/
  README.md
  src/
  docs/
  memory/
    current-state.md
    index.md
    decisions.md
    journal/
    handoffs/
  local-controls/
```

Hooks are technical controls, not necessarily files inside narrative memory.
Receipts may remain in private Git metadata or temporary storage.

| Artifact | Why it exists | Use |
|---|---|---|
| State | Reading the entire journal is expensive | Last verified closure, blockers and next step |
| Index | An answer may live elsewhere | Find authoritative context |
| Decisions | Code may not explain intent | Preserve deliberate constraints |
| Journal | Current state is overwritten | Preserve history and lessons |
| Handoff | Another contributor may continue | Carry an actionable task |
| Receipt | A note alone cannot prove closure | Check identity, files and evidence |

## A complete session

Fictional example: adjust a validation without sending real requests.

1. Read README, rules, index, state and the relevant handoff.
2. Start records a baseline for this project and session. Repeating Start keeps
   the existing baseline.
3. Change the source and verify within scope.
4. Record a memory ID, reason, evidence, mistakes and next step.
5. Update brief state and append the session without rewriting someone else's.
6. Send sanitized coordination and a pointer to the hub.
7. Close checks that the entry and evidence belong to the right root and session.
8. Verify checks receipt freshness. Later changes or a commit can require renewal.
9. The next engine checks the current source and state before continuing.

## Runtime verification

The inspected runtime requires project and session identity. Changed work needs
a local memory entry and evidence. The entry must belong to authoritative memory,
contain a MEM identifier and match the session ID. File fingerprints detect
subsequent changes; domain truth still requires an appropriate domain check.

Stop can block incomplete closure; its wrapper prevents a loop. Pre-commit checks
hygiene and private surfaces. With a session ID it requires that session's receipt;
without one it does not claim identified session closure. Sensitive surfaces may
retain declarative controls rather than executable hooks.

Claude Code has session hooks. Codex and Antigravity follow the explicit protocol;
no unverified native hook is assumed.

## Relationship to global memory

"How engines hand off work" belongs to global memory. "Why this application
keeps this validation" belongs to its project. The hub contains the catalog,
coordination and cross-project memory rather than replicated project journals.

If the hub is missing, minimal local rules and memory allow work to continue
with coordination pending. Reconnection reconciles identities, evidence and
conflicting variants explicitly. Unchanged read-only work creates no narrative,
handoff or commit.

## Public repositories and recovery

Private ignored memory is neither published nor backed up by Git. Recovery needs
a separate backup. Ignoring an already tracked file does not remove its history.

Success is concrete: the next engine understands what was decided, why, what was
verified and what remains. The project keeps the score when the performer changes.

**Next:** [Engines and budget](08-engines-fallback-and-tokens.md) | [Reading path](README.md#reading-path)
