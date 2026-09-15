# Sovereign AI OS

User-controlled records and bounded tools that work across AI assistants.

**[Start here: choose a project, try a synthetic demo, or contribute](START-HERE.md).**

WIRE SPEED COMPUTING LLC maintains this program, led by Jesse Ryski.
The goal is to keep evidence, decisions, permissions and work history useful
when models, applications or providers change.

[Website](https://www.wirespeedcomputers.com/) |
[Component routes](ROUTES.md) | [Project principles](THESIS.md)

## What we are building

1. Keep source evidence, changes and decisions in a store the owner controls.
2. Give each authorized person or agent a limited path to that data.
3. Build household and business workflows on those foundations.
4. Reuse existing models, standards and services where they fit.

Household OS is the household operating layer, not merely a calendar connector.
Its intended experience includes preparation, coordination, reminders and
approved actions using durable household context. A school notice becoming a
reviewable calendar suggestion is one useful example, not a claim that the
complete public product exists.

Household and business deployments are peers. Their schemas, permissions and
integrations may differ. A provider-neutral frontend is a direction, not a
delivered application.

## SMP is the foundation

Sovereign Memory Protocol began this work: preserving bytes is not enough if
their sources, meaning, authority and change history disappear when you move.
SMP develops implementation-neutral rules for that evidence. Core is a
PostgreSQL reference implementation; it is not the protocol itself.

Memory engines can supply retrieval and ranking. They do not determine access
rights or turn model inference into accepted fact. We aim to integrate useful
existing tools, not replace every assistant or memory engine.

## Public components

| Component | Purpose and starting point |
| --- | --- |
| [Household OS](https://github.com/jryski/Household-OS) | Household reference architecture, workflows and synthetic integration examples. |
| [Supabase User MCP](https://github.com/jryski/Supabase_user_MCP) | Bounded application-data access. Follow its documented synthetic demo and supported-client limits. |
| [Sovereign Memory Protocol](https://github.com/jryski/sovereign-memory-protocol) | Public protocol drafts for provenance, custody, authority and portability. Draft publication is not conformance acceptance. |
| [Sovereign Memory Core](https://github.com/jryski/sovereign-memory-core) | PostgreSQL reference implementation, tests and scope-specific recovery evidence. |
| [Sovereign Vault](https://github.com/WireSpeedComputing/Sovereign-Vault) | Business-domain data layer with its own policy and identity boundaries. |
| [Agent Coordination](https://github.com/jryski/Agent-Coordination) | Early public project for coordination work; do not assume a published deployment method. |
| [Public AI Skills](https://github.com/jryski/Public_AI_SKills) | Reusable working methods. Check the separate personal and organizational-use terms. |

Component repositories own their supported behavior, tests, releases and known
limitations. Public source, passing tests, deployment and independent acceptance
are different states. This parent does not certify a production-ready bundle.

## Where to begin

- [START-HERE.md](START-HERE.md): practical starting paths and contribution ideas.
- [ROUTES.md](ROUTES.md): which repository owns each concern.
- [CONTEXT.md](CONTEXT.md): bounded routing for agents.
- [THESIS.md](THESIS.md): purpose and design principles.
- [HORIZON.md](HORIZON.md): future possibilities, not present features.
- [CONTRIBUTING.md](CONTRIBUTING.md): public-safe contributions and review.
- [SECURITY.md](SECURITY.md): report security concerns privately.

Read the owning component before choosing an implementation task. This parent
is an orientation guide, not another task database or source of permission.

## Company, support and privacy

Company maintenance and GitHub account placement do not transfer copyright or
change a component's license. Funding and future support arrangements must
preserve user control and interoperability. Check each repository's terms;
a donation does not grant additional rights.

Public material contains code, architecture, synthetic fixtures and sanitized
lessons. Credentials, real household or business records, private deployment
details and restricted evidence stay out. Private components may exist without
being listed here.

Keep one implementation owner per task and independent review where needed.
Merge, release, deployment and publication have separate approval gates.

## Acceptance

This parent uses two different meanings of “accepted.” Do not collapse
them. This section is durable criteria, not a task tracker, and it does
not record whether Jesse has declared the milestone.

### Per-change merit test

A change survives if it makes sense and improves overall quality,
function, or efficiency without introducing new issues or security
concerns. Security claims must be verified against the mechanism, not
the intent, by someone other than the author.

### Parent acceptance milestone

The parent becomes accepted only when, at one exact head, all of the
following are true and Jesse explicitly declares acceptance:

1. CC BY 4.0 documentation and Apache-2.0 executable-tooling licenses are
   present with an explicit scope map.
2. Required Tier-1 CI exists and is green, including the public-boundary
   allowlist check.
3. No artifact asserts its own currency unless something outside the
   artifact can falsify that assertion.
4. All routes resolve, internal and external.
5. `SECURITY.md` and `CONTRIBUTING.md` are present, with CONTRIBUTING
   describing the Wirespeed downstream-dogfood → generic upstream
   contribution path.
6. Jesse declares acceptance at that exact head.

Acceptance is a one-time milestone, not a freeze. Ordinary later changes
use the per-change merit test.

Cross-program umbrella material previously living in Sovereign Memory
Core should be reduced to compatibility pointers only after this parent
is accepted at an exact head. Child repositories remain authoritative
for their own implementation.

## License

Copyright 2026 Jesse Ryski.

The documents in this repository are licensed under Creative Commons
Attribution 4.0 International. See [`LICENSE`](LICENSE).

The executable tooling is licensed under the Apache License, Version 2.0.
See [`LICENSE-CODE`](LICENSE-CODE). That scope is:

- `scripts/validate_parent.py`
- `.github/workflows/ci.yml`

Each carries an SPDX identifier, and `validate_parent.py` checks that the
list above and the identifiers agree. This list is the authoritative scope
map: add executable tooling to it rather than assuming it is exhaustive by
construction.

Creative Commons does not recommend its licenses for software. Both licenses
disclaim warranties, so that is not the distinction; Apache-2.0 adds an
express patent grant and the software-specific terms reusers expect.

Contributions are accepted under the Developer Certificate of Origin. See
[`DCO.md`](DCO.md). Child-repo licensing is separate.
