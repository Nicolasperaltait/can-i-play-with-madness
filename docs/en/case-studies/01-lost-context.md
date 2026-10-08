# Case study: from lost context to usable memory

**Language / Idioma:** English | [Espanol](../../casos-de-estudio/01-contexto-perdido-y-memoria-operable.md)

Can I Play with Madness? The problem appears when the performer changes and
the decision remains trapped in a conversation. This is a sanitized design
narrative, not an execution log or disclosure of a real environment.

## Problem and significance

Several AI engines saw different parts of related projects. Decisions were
scattered across files and chats. The next session could repeat an investigation,
contradict a decision or request information already available.

Context loss wastes time and can create inconsistent changes, stale documentation
and excessive data sharing when copying more context seems like the only remedy.

## Decision

Each project keeps local memory; a hub holds pointers and handoffs; a router
checks source, audience and freshness; orchestration assigns bounded tasks; and
durable knowledge receives selected reusable decisions.

Start, close, pre-commit, post-commit and explicit-plan events provide controls.
They report changes and support proposals without blindly copying or publishing.

## What could go wrong

A tempting approach is to watch every folder and copy everything centrally.
That produces stale duplicates, mixed classifications and a larger exposure
surface. Another risk is labeling a recommendation as completed work.

The design separates detection from writing and Plan from Apply, Verify and
Receipt. It defines authoritative sources, objects for requests and handoffs,
visible audience restrictions and explicit blockers.

## Intended outcome and lessons

The next engine can locate context, establish whether it is current and continue
from a concrete step without reading everything. Success is less ambiguity,
duplication and unnecessary access rather than more generated text.

1. Memory is a policy supported by artifacts.
2. Sources and derived summaries remain distinct.
3. Detection does not imply publication permission.
4. Triangulation needs visible roles and contracts.
5. Missing evidence is a valid state.

At company scale, a product change may affect support, security, operations and
compliance. Each domain retains authority, while authorized summaries and handoffs
make documentation review visible.

**Continue:** [Architecture](../01-architecture.md) | [Reading path](../README.md#reading-path)
