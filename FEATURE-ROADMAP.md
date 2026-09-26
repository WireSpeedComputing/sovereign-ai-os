# Feature Roadmap: from everyday evidence to useful outcomes

> Capability targets derived from the principal-requested [north star](NORTHSTAR.md).
> The grouping, capability stages, and evaluation criteria below are proposed
> planning guidance, not implementation acceptance, a delivery schedule, or
> authorization to deploy, purchase, disclose, or act.
>
> Note (MC1304): roadmap dependency gates were renamed to capability stages
> 1–5 so they are not confused with launch gates A/B/C on #52.

## Scope and interpretation

This is a cross-domain feature roadmap, not a school-menu implementation plan.
It describes what the cooperating repositories should enable and how useful
slices can demonstrate the shared architecture.

Do not read a listed feature as implemented, tested, accepted, or released.
Component repositories own that evidence. Actual priorities, assignments,
issues, reviews, and deployment decisions belong in their authorized work
surfaces. The capability identifiers below are reference labels, not task IDs.

Use [ROUTES.md](ROUTES.md) for ownership, [THESIS.md](THESIS.md) for invariants,
and [HORIZON.md](HORIZON.md) for longer-range possibilities. Private examples
must be reduced to synthetic fixtures before entering public repositories.

## Capability families

| ID | Capability target | User-visible value | Required distinction or boundary |
| --- | --- | --- | --- |
| F01 | Consentful intake and progressive onboarding | Connect a useful source once; reuse its evidence without repeated manual explanation. | A detected source is not permission to ingest it; preserve source versions, freshness, and revocation. |
| F02 | Shared entity, resource, and relationship identity | Connect people, products, places, assets, commitments, and relevant history across tools. | Typed domain records remain distinct; ambiguous identities require resolution, not silent merging. |
| F03 | Preferences, intentions, constraints, and standing authority | Plans reflect the people affected, their goals, and what they actually authorized. | Separate explicit choices, contextual estimates, temporary restrictions, and accepted commitments. |
| F04 | Inventory and consumption estimation | Replenish near the useful time while reducing stockouts, excess purchases, waste, and extra trips. | Purchase cadence is evidence, not measured stock; account for units, quantities, returns, lead time, and uncertainty. |
| F05 | Commitment preparation and recurring obligations | Assemble tools, parts, documents, registration, and other prerequisites before they are needed. | A proposal is not an appointment; recurring obligations need a source or an accepted rule. |
| F06 | Dependency-aware planning and change propagation | A changed plan coherently updates meals, errands, calendars, resources, and affected suggestions. | Track why a plan depends on evidence; corrections must invalidate or reconsider dependent results. |
| F07 | Durable execution and reconciliation | Authorized work survives crashes, missed messages, duplicate inputs, and provider outages. | Attempted, provider-acknowledged, completed, and independently verified are separate states. |
| F08 | Attention, presence, and notifications | Surface useful changes at the right moment, with shared context and individual read state. | Machine broadcasts, queued work, persistent inboxes, and human interruptions are different mechanisms. |
| F09 | Personal and multi-household cooperation | Prepare shared trips, services, and activities without exposing complete private records. | Disclose only purpose-bound constraints; preserve identity, expiry, approval, and revocation. |
| F10 | Recipe, meal, and fulfillment planning | Offer varied menus from curated recipes, derive ingredients, and coordinate approved fulfillment. | Keep each person's constraints distinct; observed eating and waste differ from a planned or purchased meal. |
| F11 | Outcome learning and low-cost assistance | Corrections and observed results improve later suggestions without rereading the entire archive. | Use evidence-backed estimates and scoped feedback; model inference never self-promotes to accepted fact. |
| F12 | Portable provider and physical adapters | Replace assistants, retailers, calendars, trackers, or future actuators without losing context. | Advertise and verify actual capabilities; unavailable interfaces and physical safety constraints remain explicit. |

These capabilities should compose. Do not implement twelve unrelated assistants
or twelve parallel sources of truth.

## Related public issues

Some capability families already have public issues. The citations below are
references only. They are not assignments, acceptance evidence, or a complete
index, and they do not mean the capability is implemented. Families without a
confident citation are omitted.

| ID | Related public issues |
| --- | --- |
| F02 | [Household OS #8](https://github.com/jryski/Household-OS/issues/8) entity, observation, event, capability, and provenance model; [Household OS #10](https://github.com/jryski/Household-OS/issues/10) connector observations and entity-resolution proposals. |
| F03 | [sovereign-ai-os #36](https://github.com/WireSpeedComputing/sovereign-ai-os/issues/36) preference, constraint, and goal model. |
| F04 | [Household OS #16](https://github.com/jryski/Household-OS/issues/16) kitchen items, keep-list, and stock; [Household OS #18](https://github.com/jryski/Household-OS/issues/18) receipt ingest to stock. |
| F07 | [sovereign-ai-os #23](https://github.com/WireSpeedComputing/sovereign-ai-os/issues/23) action request and receipt contract; [Household OS #20](https://github.com/jryski/Household-OS/issues/20) external household actions behind action receipts. |
| F08 | [sovereign-ai-os #33](https://github.com/WireSpeedComputing/sovereign-ai-os/issues/33) presentation and presence contract. |
| F09 | [sovereign-ai-os #39](https://github.com/WireSpeedComputing/sovereign-ai-os/issues/39) external agent outcome exchange; [sovereign-ai-os #38](https://github.com/WireSpeedComputing/sovereign-ai-os/issues/38) sanitized steward-to-steward exchange. |
| F10 | [Household OS #14](https://github.com/jryski/Household-OS/issues/14) recipes in HOUSE; [Household OS #19](https://github.com/jryski/Household-OS/issues/19) meal and school-lunch planning. |
| F12 | [Household OS #13](https://github.com/jryski/Household-OS/issues/13) calendar and display synchronization boundaries. |

## The shared architecture to evaluate

```text
Permitted sources and devices
    -> versioned evidence and typed observations
    -> identity, relationships, estimates, preferences, and intentions
    -> dependency and expectation evaluation
    -> authorized proposal or durable work
    -> worker and provider adapter
    -> receipts, real outcomes, and reconciliation
    -> updated context and selective change notifications
```

### Put dependable operations beside the data

Evaluate existing PostgreSQL and Supabase capabilities before adding a service:

- Constraints and transactions for valid, coherent state changes.
- Bounded functions for established procedures and explicit authorization.
- Views or read functions for small, task-specific context packages.
- Triggers for limited obligations such as audit or transactional enqueueing,
  not unbounded model inference or remote side effects inside a transaction.
- Durable queues or an appropriately designed outbox for recoverable work.
- Scheduled jobs for expected-but-missing events, stale work, and reconciliation.
- Private change broadcasts for connected clients and running subscribers.
- Object storage for source evidence and separately governed derived artifacts.
- Full-text and vector retrieval for finding useful candidates, not deciding
  truth, identity, authority, stock levels, or whether an action completed.

These are mechanism candidates, not a statement that any extension is installed
or a selected design has passed review. Verify each deployment's actual version,
configuration, grants, quotas, and failure behavior in the owning component.
Do not enable capabilities or widen credentials merely because this roadmap
names them.

### Keep uncertainty and authority explicit

Distinguish observed facts, estimates, proposals, accepted decisions, actions,
and verified outcomes. Preserve effective time and observation time separately
where they matter. An old device location or purchase record must not silently
become a claim about the present.

Bind access and writes to verified principals. Human, household, agent, business,
and provider identities are not interchangeable. Standing policies need scope,
limits, expiry or revocation semantics, and a clear escalation path.

### Make work survive missed notifications

Preserve accepted state and its required work coherently. Use stable request
identity, bounded claims, safe retries, desired revisions, and receipts. Detect
and reject stale completion where newer work supersedes it. Reconcile uncertain
external outcomes instead of assuming a successful network request means the
real-world need was met.

Broadcast small change signals to authorized subscribers. Retain recoverable
state separately, including notification intent and per-recipient inbox state.
On reconnect, fetch an authorized snapshot or resumable change history.
A missed broadcast must not lose a purchase approval, maintenance obligation,
or calendar correction. Duplicate signals must not duplicate external actions.

Use local execution where the useful reaction window or disconnection behavior
requires it. A running worker is necessary for automatic response; a chat
conversation is not a persistent subscriber.

### Learn from consequences, not clicks alone

Connect proposals to approvals, execution, and observed outcomes. A purchase is
not proof of consumption; a suggestion dismissal is not necessarily dislike;
a task checkmark may be a self-report rather than independent verification.

Use deterministic rules and ordinary estimation where sufficient. Give small
models prepared, permitted context and structured results. Escalate unfamiliar
interpretation when needed instead of asking a large model to rediscover the
same schema and operational rules for each event.

## Proposed capability stages

These stages describe dependency order, not calendar dates or assigned work.
Reuse existing accepted capabilities where evidence supports them. A stage need
not require every feature family to be complete before useful work ships.

### Capability stage 1: shared evidence, identity, and authority

Establish or reuse source versioning, subject identity, typed state, freshness,
consent, principal-bound access, and acceptance boundaries. Support bounded
read functions and explainable proposals before consequential automation.

Proof should include duplicate input, source correction, ambiguous identity,
stale evidence, unauthorized access, and withdrawal of permission. Show that
private and shared records cannot be mixed merely by changing a caller label.

### Capability stage 2: demonstrate reuse across different needs

Deliver a narrow set of valuable slices from different domains: for example,
menu reconciliation, consumable replenishment suggestions, and preparation for
an accepted repair commitment.

They should share evidence, identity, proposal, dependency, authority, and receipt
contracts where appropriate. Each retains its domain semantics. A useful slice
must not depend on finishing an all-purpose planner or every integration.

The key proof is one cross-domain consequence: a changed commitment updates an
affected meal proposal and its resource requirements without creating unrelated
sources of truth or duplicate human interruptions.

### Capability stage 3: reliable ambient operation

Add durable execution, bounded retries, scheduling, reconciliation, observability,
and attention handling. Operate under outages and recover without asking the
human to reconstruct what happened. Add targeted local reactions where useful.

Prove worker crashes, overlapping workers, missing and duplicated broadcasts,
provider timeouts, stale revisions, cancellations, expired credentials, and
reconnect recovery. Measure the supervision burden, not only successful runs.

### Capability stage 4: multi-person and federated cooperation

Support individual preferences and inboxes, shared responsibilities, membership
changes, private-to-shared disclosure, and purpose-bound requests between
independent households or organizations.

Prove minimum disclosure, conflicting preferences, recipient authorization,
revocation, expired proposals, concurrent edits, and refusal to treat an empty
calendar as approval of another party's plan. Do not solve cooperation by
sharing administrator credentials or entire personal stores.

### Capability stage 5: bounded fulfillment and optional physical extension

Extend approved plans into carts, deliveries, bookings, or device operations
only where integrations are supported and authority is explicit. Distinguish
price estimates from executable offers and confirm material changes before
commitment where policy requires it.

Prove budget and scope limits, duplicate-order prevention, substitutions,
cancellation, delivery reconciliation, and outcome verification. Future robotic
or appliance execution requires its own capability checks, device-level safety,
interlocks, and explicit operational acceptance. It is not required to provide
software-first value.

## Reference acceptance scenarios

Use synthetic data. These are cross-domain tests of reusable contracts, not a
requirement to finish every scenario in the first release.

| Scenario | What the system should demonstrate |
| --- | --- |
| Corrected school menu | Preserve the previous source, reconcile the accepted version, reconsider affected meal plans, update authorized projections, and issue one useful change summary. |
| Likely condiment depletion | Produce an explainable, uncertain estimate from shopping evidence; incorporate a correction about spare stock; avoid unnecessary or duplicate ordering. |
| Appliance-installation commitment | Preserve accepted scope and timing, prepare tools and parts from relevant evidence, flag unknown requirements, and update preparation when the commitment changes. |
| Picture-hanging request | Keep location and mounting requirements attached to the task; distinguish requested, agreed, prepared, and completed states. |
| Vehicle consumable alert | Use sufficiently fresh device evidence, check available stock and authority, prepare replenishment, and distinguish delivery from actual refill. |
| Pet-care due date | Use a recorded due date or accepted recurrence, add a suitable task, and stop repeated reminders when completion evidence arrives. |
| Cooperative vacation planning | Exchange permitted candidate windows, present dated cost estimates and constraints, and require each relevant approval before booking. |
| Essential item left behind | Warn only with evidence fresh enough for the useful action window; avoid asserting current location from stale telemetry. |
| Event preregistration | Find the requirement and deadline, prepare the authorized step, preserve confirmation, and reconcile the obligation as fulfilled. |
| Weekly recipe planning | Respect individual constraints, rotate curated recipes, incorporate actual attendance and stock estimates, obtain approval, and update from what was eaten or wasted. |

## Repository ownership and implementation handoff

The existing [public routes](ROUTES.md) remain authoritative for ownership.
This table explains contribution, not new assignments or expanded mandates.

| Owning concern | Roadmap contribution |
| --- | --- |
| Sovereign Memory Protocol | Portable meaning for evidence, provenance, authority, temporal change, and receipts; do not infer protocol semantics from one database. |
| Sovereign Memory Core | PostgreSQL reference mechanisms and tests for durable evidence, custody, recovery, and supported contracts; avoid household-specific policy in the core. |
| Supabase User MCP | Verified principal and agent access, bounded capabilities, and authorization evidence for supported profiles. |
| Household OS | Household entities, resources, commitments, planning, attention semantics, workflow contracts, and provider reconciliation. |
| Sovereign Vault | Separate business-domain reference behavior with its own policies and identity boundaries. |
| Agent Coordination and authorized runtimes | Running workers, bounded delegation, and coordination through accepted contracts rather than agent chat as the source of truth. `jryski/Agent-Coordination` is archived; live household agent interaction routes to Household-OS (see sovereign-ai-os #12/#13). |
| Public AI Skills and domain contributions | Reusable working methods and public-safe domain knowledge where compatible with their licenses and ownership. |

A routed implementation issue should name the human outcome, capability family,
contract owner, existing mechanisms to reuse, evidence and authorization needs,
failure tests, dependency effects, and bounded acceptance criteria. Keep one
implementation owner and independent review where required. Do not create a
new repository simply because another use case appears.

The parent records direction. Child issues and evidence record delivery. This
roadmap does not grant agents merge, deployment, disclosure, or spending authority.

## Evaluation and open design questions

Evaluate desired outcomes against the overhead required to obtain them:

- Human time, corrections, and supervision required per useful outcome.
- Missed obligations, excess stock, waste, and avoidable trips.
- Relevant versus unwanted interruptions, including duplicate and stale alerts.
- Recovery from outages, duplicate inputs, and uncertain external outcomes.
- User understanding, consent, reversibility, and unauthorized disclosure.
- Cost and latency of rules, retrieval, models, integrations, and operations.
- Continuity after replacing a provider, model, worker, or interface.

These are candidate evaluation dimensions, not invented numerical targets.
Define practical measurements in each accepted slice without adding intrusive
telemetry solely to score the product.

Resolve detailed choices through the owning work surfaces: which source APIs
are actually available; how inventory uncertainty is represented; how shared
preferences resolve; what standing policies permit; how revocation reaches
connected subscribers; which local reactions are appropriate; and how completed
outcomes can be verified without burdensome manual confirmation.

The roadmap succeeds when shared infrastructure makes the next useful capability
cheaper and more dependable, while the person has less to remember and manage.
