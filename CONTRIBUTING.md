# Contributing

Thank you for helping keep this public parent useful and safe.

This repository is the **router and public front door** for Sovereign AI
OS. It is not a monorepo, not a second implementation authority, and not
a planning database. Implementation belongs in the owning public child
repository named by [`ROUTES.md`](ROUTES.md).

By contributing, you agree that your contribution is licensed under the
license that applies to the file you are changing: [`LICENSE`](LICENSE),
Creative Commons Attribution 4.0 International, for documents, and
[`LICENSE-CODE`](LICENSE-CODE), Apache License 2.0, for the executable
tooling listed in [`README.md`](README.md#license). Contributions are
accepted under the Developer Certificate of Origin; see [`DCO.md`](DCO.md).
Child repositories may use different licenses.

## Read first

1. [`README.md`](README.md) — what this parent is and is not.
2. [`ROUTES.md`](ROUTES.md) — which public component owns the concern.
3. [`CONTEXT.md`](CONTEXT.md) — cold-start order for agents.
4. [`SECURITY.md`](SECURITY.md) — what must never appear in public
   issues or pull requests.
5. [`THESIS.md`](THESIS.md) — only when mission or invariant principles
   are needed.
6. [`HORIZON.md`](HORIZON.md) — only when future direction matters.

Agents should follow `CONTEXT.md` before ingesting thesis or horizon
payload.

## Downstream dogfood to generic upstream

Wirespeed is operated by the same principal. It is not independent
third-party review. It remains a separate deployment with its own
identity, data, policy, and authority.

Wirespeed and other deployments may observe real defects while dogfooding
the architecture. Those observations do not become upstream truth by
being true downstream.

```text
downstream dogfood observation
        ↓
genericize / remove private payload
        ↓
issue or PR to the owning upstream public repo
        ↓
normal review / evidence / acceptance
        ↓
optional downstream adoption
```

Clarifications:

- Downstream evidence does **not** self-promote upstream.
- Upstream acceptance does **not** force downstream parity.
- Business-specific policy, private data, topology, credentials, and
  deployment-only behavior stay in the authorized business deployment.
- A generic lesson may enter the owning **public** repository only after
  private payload is removed.

If the owning public route is unclear, open an issue on this parent that
asks for a route, not for an implementation change.

## What belongs here

Good parent contributions are small and routing-shaped:

- broken public links or missing required files;
- ambiguous routes that send a cold reader to the wrong public repo;
- CONTRIBUTING / SECURITY / LICENSE corrections for this parent;
- public decision-pointer wording that no longer matches an accepted
  ruling.

Do not add:

- a hand-maintained current-state, effort, or provenance chronicle;
- private names, locators, or denylist patterns;
- a machine-readable program manifest without a demonstrated second
  consumer;
- implementation, schema, or deployment changes that belong in a child
  repository.

## Pull requests

Keep pull requests small enough to review as one coherent change.

A pull request should:

- explain the routing or documentation defect;
- name the owning surface (`ROUTES.md`, this parent, or a child repo);
- avoid unrelated doctrine rewrites;
- pass Tier-1 CI;
- omit private payload.

Use a topic branch.

### Docs-only merges (locked D3)

Locked **D3** on the GitHub-first operating model allows **docs-only** bot
merges only after all of the following are true:

- required CI is green;
- a distinct GitHub reviewer identity exists (Primary Users F2);
- that identity has approved the pull request on GitHub;
- the author and the reviewer are different GitHub identities
  (author ≠ reviewer).

No D3 bot merge until that distinct GitHub reviewer identity exists.
Model Channel PASS is not GitHub approval. A shared `jryski` login means
author ≠ reviewer cannot currently be satisfied on GitHub. Core pull
request
[sovereign-memory-core#97](https://github.com/jryski/sovereign-memory-core/pull/97)
received HTTP 422 “Can not approve your own pull request” when approval
was attempted through that same login. A comment on the pull request is
not a GitHub approval.

D3 is not a rule that Primary Users click merge on every docs-only pull
request. It does not authorize a bot merge of anything outside the narrow
definition below, and it cannot rewrite this section or the steward map.

Non-docs merges, release, deploy, and access expansion still need Primary
Users (or explicit delegation). Opening an issue, branch, or pull request
grants none of those actions.

This section does not install rulesets, does not allow the author to
approve their own landing, and does not claim that Gate A or Gate B is
enforced.

### Docs-only, narrowly

A pull request is docs-only only when every changed file is human-readable
documentation that does not grant authority, does not describe executable
agent instructions, and does not change bot, workflow, review, security,
governance, routing, license, or DCO behavior.

The following are **never** docs-only, even when they are Markdown. A
docs-only bot merge must not be able to rewrite D3 or the steward map.

Agent-instruction and security surfaces:

- `AGENTS.md`
- `CONTEXT.md`
- `CLAUDE.md` and equivalents (other agent-instruction entry points)
- `.cursor/**`
- `.github/**` in full, with no behavior test: `CODEOWNERS`, issue and
  pull-request templates, workflows, and every other path under that
  directory
- `SECURITY.md`
- any file that grants or describes executable agent instructions

Governance, routing, license, and DCO surfaces:

- `CONTRIBUTING.md` (including this D3 section)
- `STEWARDS.md`
- `ROUTES.md`
- `START-HERE.md`
- any license or Developer Certificate of Origin document, including
  `LICENSE`, `LICENSE-CODE`, `DCO.md`, and `COPYRIGHT`
- any other file that changes governance, routing, license, or DCO terms

If a pull request mixes a docs-only file with any exclusion, the whole
pull request is non-docs and needs Primary Users (or explicit
delegation).

Proposed assigning stewards for public routes are in
[`STEWARDS.md`](STEWARDS.md). That map is proposed only. It is not merge
authority and it is not Gate A/B enforcement. Changing `STEWARDS.md` is
outside docs-only.

## Validation

From the repository root:

```text
python3 scripts/validate_parent.py
```

GitHub Actions also run Markdown structural checks and internal/external
link validation. The public-boundary check is an **allowlist** of known
public routes; it is not a denylist of private names.

## Acceptance

This parent uses two meanings of “accepted.” See the Acceptance section
in [`README.md`](README.md):

- the per-change merit test for ordinary later work;
- the one-time parent acceptance milestone, declared by Jesse at an
  exact head.

This file does not record whether that milestone has been declared.
