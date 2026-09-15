# Start here

Keep your records useful when you change AI tools.

This project is building a foundation where people and organizations control
their records, the evidence behind them, and who can act on them. Models and
apps can change without becoming the only place your history makes sense.

Household OS is the practical household application of that idea. SMP defines
the information and evidence rules. User MCP provides a bounded path for AI
clients to reach application data. You do not need to install every project
to explore or contribute to one.

## Choose your starting point

| I want to... | Start with | What to expect |
| --- | --- | --- |
| Try an AI connector against sample data | [User MCP getting started][mcp-start] | An experimental local, read-only synthetic demo. Follow its prerequisites, not a production setup. |
| Understand the household use case | [Household OS][house] | Reference architecture, household workflows and synthetic integration patterns, not a finished consumer app. |
| Understand what survives a change of provider | [Sovereign Memory Protocol][smp] | Protocol drafts for provenance, custody, authority and portability. Publication is not proof of conformance. |
| Build or test the database implementation | [Sovereign Memory Core][core] | An alpha PostgreSQL reference implementation and test harnesses. |
| Adapt the ideas to a business | [Sovereign Vault][vault] | A business data layer with its own identity and policy boundaries. Read its status and open risks first. |
| Explore agent deployment and coordination | [Agent Coordination][coordination] | An early public placeholder. Its README currently contains only the project title. |
| Reuse AI working methods | [Public AI Skills][skills] | Versioned skills with personal-use terms; organizational use requires separate permission. |

For the broader rationale, read [the thesis](THESIS.md). For ownership of
technical concerns, use [the route map](ROUTES.md).

## How the pieces fit

SMP was the starting point: retaining records is not enough if you lose their
sources, meaning or change history when moving them.

- **SMP is the protocol.** It describes the evidence and authority semantics,
  independently of a particular database, memory engine or AI provider.
- **Core is a reference implementation.** It implements and tests those ideas
  in PostgreSQL. It is not a complete household app or retrieval product.
- **User MCP is the access layer.** It explores application-data access tied
  to a user or agent, rather than granting a model administrative access.
- **Household OS and Sovereign Vault are application/domain projects.** They
  address household and business needs respectively. They are not required
  to share identical schemas, permissions or deployment steps.
- **Agent Coordination and skills address how agents work.** They do not
  replace database authorization or make a claimed capability trustworthy.

These are related projects, not a tested install-everything bundle. This
parent repository explains their relationship; each component owns its
implementation, tests and limitations.

## What Household OS is aiming for

Suppose you upload a school notice. The intended workflow is to extract the
date, preserve the source, detect a duplicate or conflict, and propose the
right calendar action for the people allowed to see it. Another assistant
should be able to pick up that work without you retelling the story.

The same approach extends to household projects, maintenance and shared
knowledge, while keeping private information private. This example describes
the intended connected experience, not a claim that the entire workflow is
available as a public product today.

## What can I test today?

Start with the [User MCP synthetic demo][mcp-start]. Its public instructions
describe a POSIX local-stdio path. Native Windows, a public hosted endpoint
and a one-click installer are not supported by that public profile.

Use fabricated data in an isolated test environment. Do not connect real
household or business records because a demo passes. The public README
separately documents private-alpha work; that does not make it part of the
public installation path.

For database work, use Core's own setup and tests. For household or business
design, read the relevant component's examples and limitations before
adapting them. There is no single production-readiness claim for all repos.

## Help with one concrete thing

You do not need access to our private chats to begin.

1. Choose one component above and read its contribution and license terms.
2. Check its open issues and pull requests for existing work.
3. Propose a bounded task with a reproducible result. Useful starting points:
   reproduce the synthetic MCP demo and report an unclear step; add a
   fabricated household calendar edge case; or identify an ambiguous SMP
   rule with a concrete example.
4. Include the version or commit tested, expected behavior and actual result.
   Keep private records, credentials and deployment details out of reports.

These are contribution suggestions, not claims that an issue is unassigned.
For security problems, use the component's documented private reporting
route rather than posting sensitive details in a public issue.

## Why are the repositories under two accounts?

The public project spans **jryski** and **WireSpeedComputing** on GitHub.
This page links the verified current destinations so you do not need to
guess which account contains a component. Account placement is not a
readiness label, a license grant or proof of legal ownership.

[Wire Speed Computing's website][website] is the public introduction and
support surface. Each repository's own license governs reuse; public
visibility and financial support do not grant additional rights.

## About this guide

Links and descriptions checked against public repository READMEs on
2026-09-15. This is an orientation snapshot, not a live deployment audit.
Follow each component's current documentation for supported behavior.
The [horizon](HORIZON.md) describes longer-term possibilities, not a feature
list. Internal deployments and private records are intentionally absent.

[mcp-start]: https://github.com/jryski/Supabase_user_MCP/blob/main/docs/GETTING_STARTED.md
[house]: https://github.com/jryski/Household-OS
[smp]: https://github.com/jryski/sovereign-memory-protocol
[core]: https://github.com/jryski/sovereign-memory-core
[vault]: https://github.com/WireSpeedComputing/Sovereign-Vault
[coordination]: https://github.com/jryski/Agent-Coordination
[skills]: https://github.com/jryski/Public_AI_SKills
[website]: https://www.wirespeedcomputers.com/
