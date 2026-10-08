# Security, privacy and sanitization

**Language / Idioma:** English | [Espanol](../05-seguridad-y-sanitizacion.md)

Can I Play with Madness? Yes, when access can be defined and revoked. Sharing
the score does not require handing over the keys to the building.

## Minimum context

An agent receives only the needed source or pointer, for the needed duration,
with the appropriate classification and audience. Access alone does not establish
that the information is necessary for the task.

| Classification | Handling |
|---|---|
| Public | Sanitized reusable patterns may be published |
| Internal | Only authorized organizational recipients |
| Local-only | Body remains at its source |
| Indexed without content | Existence and routing metadata only |

Classification is a handling signal. Actual permissions must enforce it.

## Excluded from public material

Credentials, tokens, cookies, certificates, internal addresses, domains, hostnames,
usernames, logs, dumps, complete configurations, machine identifiers, account
details, private repository names, workstation paths and private personal data
are excluded. Public documentation communicates judgment without providing an
operational map.

## Transformation example

An unsuitable description identifies an internal jump host, a service account
and a precise change time. A suitable public description explains the decision:

> A jump host with its own identity concentrates agent access and allows that
> path to be revoked without giving agents privileges across the network.

The design survives; identifying details do not.

## Router checks

```text
source_exists
classification_allows(audience)
freshness_is_known
requested_scope_is_minimal
response_contains_no_secret
response_is_not_an_unauthorized_private_body
```

Failure means denial, explicit authorization request or a permitted pointer
without content.

## Audit and retention

Separate audit metadata, necessary decisions and handoffs, temporary material
and restricted private bodies. Recording that a task occurred does not require
retaining every prompt. Retention follows need, risk and organizational obligations.

## Rollback

Identify the transaction, check for incompatible subsequent work, restore the
previous state under the authorized procedure, preserve incident evidence and
invalidate derived responses that depended on the incorrect entry. Do not erase
history to conceal a mistake; document the correction and review affected outputs.

## Threat model

| Threat | Main defense |
|---|---|
| Prompt injection in a source | Treat source content as data, not governing instructions |
| Memory confused with authority | Required source and version metadata |
| Handoff exfiltration | Audience check and sanitization before writing |
| Stale answer | Scoped freshness verification |
| Accidental inherited privilege | Deny by default and bounded tools |
| Unrecorded change | Divergence detection and closure receipts |

Review the entire public diff and history as someone attempting to identify the
real environment. Diagrams and metadata deserve the same scrutiny as prose.

**Next:** [Implementation playbook](06-implementation-playbook.md) | [Reading path](README.md#reading-path)
