# Several engines, one budget: sharing the madness

**Language / Idioma:** English | [Espanol](../08-motores-fallback-y-tokens.md)

More engines add alternatives and coordination overhead. Memory supports changing
tools without sending the entire previous conversation again.

## Tools and boundaries

| Tool | Use in this ecosystem | Rule |
|---|---|---|
| ChatGPT | Conversation and problem framing | Chat context does not replace authority |
| Codex | Artifacts, repositories and verification | Read access does not authorize export |
| Claude | Authorized technical analysis | Preserve audience and restrictions |
| Claude Code | Repository work with lifecycle hooks | Hooks verify closure, not domain judgment |
| Local Qwen3 Instruct | Installed text capability | Check suitability per task |
| Local Qwen3 VL Instruct | Installed multimodal capability | Installation does not prove active integration |
| Antigravity | Continuity and budget fallback | Minimal context; no sensitive bodies by default |

Local families were verified through installed model filenames. Paths,
quantization and equipment configuration are omitted. These roles describe this
ecosystem, not a universal product ranking.

## Tokens and context

A token is a unit of text processed by a model. Prompts, documents, history and
responses consume context and may affect service limits or costs. Tokens are
not always words and have no universal price.

Sending the same history to three engines repeats consumption and unnecessary
exposure. A brief memory and index retrieve the relevant part. Avoiding repeated
investigation can matter more than merely requesting shorter answers.

## Established workflow rules

- First look for a current derived response.
- Ask the source only for missing context.
- Scope context by audience and trust.
- Maintain one project memory instead of copies for each engine.
- Define a delegated task's objective, constraints and verification.
- Treat delegated capacity as shared: one authorization has bounded scope.
- Use a sanitized handoff for fallback continuity.

The workflow owner identifies Antigravity as a fallback. The exchange policy
restricts the Gemini-related fallback role to minimal state, next steps and
sanitized responses. A tool name does not establish its currently active model.

No measured saving percentage or automatic consumption-threshold switching is
claimed. This is a conscious allocation strategy.

## Fictional fallback handoff

```text
Goal: review a technical explanation.
State: architecture defined and links checked.
Context: sanitized document and public glossary.
Pending: contradictions between concepts.
Constraints: no private sources or operational changes.
Deliverable: contradiction locations and proposed corrections.
```

Fallback work returns evidence and uncertainty. Missing permission or capability
is a blocker, not a reason to invent a successful result.

## Local AI and concurrency

A suitable local task may avoid cloud consumption while using equipment resources,
maintenance and verification effort. Local does not guarantee isolation: tools,
network and permissions still matter. Installed files alone prove no workload.

Concurrent engines need bounded responsibilities. Sessions have independent IDs;
journals append; transactional plans use locks and hashes to detect later work.
One session receipt cannot close another session. Four guitarists do not all need
to play the solo: define who integrates results and what evidence is accepted.

## Proposed scaling practices

Measure task consumption and quality, choose the lightest engine meeting the
acceptance criterion and reserve costly review for high-impact decisions. These
are proposals, not established automatic behavior in this ecosystem.

We can play with madness when handoffs preserve judgment and capacity is managed
as a work resource.

**Next:** [Security](05-security-and-sanitization.md) | [Reading path](README.md#reading-path)
