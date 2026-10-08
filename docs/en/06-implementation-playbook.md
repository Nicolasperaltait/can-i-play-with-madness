# Implementation playbook

**Language / Idioma:** English | [Espanol](../06-playbook-de-implementacion.md)

Can I Play with Madness? Begin with verifiable local memory. Define authority
and continuity before adding connectors, each with a purpose and acceptance rule.

## Minimal structure

```text
project/
  source/
  memory/
    current-state.md
    decisions.md
    receipts/
  handoffs/
  policies/
  README.md
```

This is illustrative. The hub points to the source rather than copying it, and
runtime receipts may instead live in private Git metadata or temporary storage.

## Source contract

```yaml
id: logical-project-id
authority: source-of-truth
classification: internal
audiences:
  - project-team
memory_relative_path: memory/
freshness:
  method: git-subpath-or-file-evidence
  last_verified: YYYY-MM-DD
```

Use unknown or pending when evidence is missing. Do not invent metadata.

## Task contract

```yaml
request_id: RQ-example-topic
requested_by: engine-or-person
source: logical-project-id
scope: one-question-or-one-change
audience: named-team
forbidden:
  - private-bodies
  - secrets
  - unrelated-domains
acceptance: observable-result
```

A bounded task reduces unnecessary context and coordination cost.

## Recommended sequence

1. Inventory sources and owners.
2. Define classifications and audiences.
3. Create local memory and a handoff template.
4. Implement session start and close.
5. Add pre-commit verification.
6. Add post-commit notices without copying.
7. Measure scoped freshness.
8. Implement a deny-by-default router.
9. Add a second engine for low-risk tasks.
10. Selectively promote durable decisions.

A vector database is not a substitute for authority, audience and freshness.
Without those, retrieval can merely deliver incorrect answers faster.

## Meaningful verification

Positive checks establish that a session finds memory, a request reaches the
right source, a handoff is usable, a decision links to authority and a source
change produces a notice without copying its body.

Negative checks establish that private sources are denied to public audiences,
stale answers are rejected, unsupported closure cannot be marked complete,
out-of-scope delegation fails, unnecessary tools remain unavailable and output
loops do not repeat writes.

## Daily operation and growth

Start with project rules and state. During work, use authoritative sources and
mark inference. Close with facts, mistakes, lessons and the next step. When the
hub is unavailable, leave local coordination pending rather than claiming sync.

As projects grow, separate domain registries, centralize only the appropriate
index and policies, preserve owners, require evidence for handoffs and responses,
apply classification-specific retention and audit failures as well as successes.
Review engine integrations periodically.

Healthy scale adds routing and controls rather than an omniscient central memory.

**Next:** [Project memory](07-project-memory.md) | [Reading path](README.md#reading-path)
