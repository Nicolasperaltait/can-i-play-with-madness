# Context - Persistent AI Memory Workflow

**Language / Idioma:** English | [Espanol](../../contexto.md)

## What it is

A documented pattern for continuity across AI engines: local memory, handoffs,
classification-based routing, lifecycle triggers and durable knowledge.

## Why it exists

Conversation is a temporary interface. Decisions must survive a chat, a model,
a provider and the person who started the work. The hub provides coordination
without becoming an indiscriminate copy of every source.

## What it demonstrates

- Separating sources, memory, indexes and durable knowledge.
- Using Git and session events for detection and validation.
- Producing evidence without claiming unperformed work.
- Coordinating bounded tasks between engines.
- Continuing a task through a sanitized handoff.
- Extending the pattern from one project to an organization.

| Item | Value |
|---|---|
| Format | Markdown and Mermaid diagrams |
| Type | Sanitized public documentation |
| Operational code | Contracts and pseudocode only |
| Audience | Engineering, architecture, platform, security and operations |
| Status | Documented pattern; integrations require their own validation |

Persistent memory preserves what is needed, in the right place, for the right
audience, with evidence of freshness. [Start reading](README.md).
