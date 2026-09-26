# North Star: personal infrastructure that gives people their time back

> Product direction requested by the principal on 2026-09-26.
> This is a statement of purpose, not deployed-capability evidence, a runtime
> permission, or approval of every proposed implementation choice.

## The human outcome

Build a user-controlled system that turns the ordinary evidence of life into
coordinated assistance. Reduce the effort people spend remembering, preparing,
checking, replenishing, scheduling, and following up. Preserve their attention
for family, creativity, meaningful work, rest, and whatever else they choose.

The product is not a chatbot with a better memory, a calendar connector, or a
collection of unrelated automations. It is personal infrastructure that connects
what happened to what matters next, helps carry out authorized responses, and
checks whether the intended outcome actually happened.

School menus, grocery replenishment, home repairs, maintenance, forgotten items,
and shared trips are reference cases. None defines the boundary of the product.
The same foundations should support household and organizational life while
preserving their separate identities, policies, records, and authority.

## Put the value of data to work for the people it concerns

Purchases, messages, appointments, documents, device signals, preferences,
promises, and completed work can supply useful evidence when access is permitted.
The program's purpose is to use that evidence for the person's benefit: less
waste, fewer avoidable problems, lower coordination costs, and more agency.

Existing commercial infrastructure can provide storage, models, devices,
retailers, logistics, and services. Integrate those capabilities where useful
without making a provider the owner of the person's durable context or goals.

Human benefit is the objective, not increased consumption, advertising
engagement, behavioral-profile sales, or lock-in. Funding, maintenance, and
support can sustain the work, but must remain subordinate to user control and
interoperability. These are product principles, not changes to component licenses.

## The observation-to-outcome loop

```text
Observe permitted evidence or an expected event that did not occur
    -> connect it to people, resources, intentions, and prior evidence
    -> update known, estimated, disputed, and missing state
    -> detect a useful need, opportunity, conflict, or obligation
    -> prepare a response within the relevant authority
    -> stay quiet, present, ask, or carry out an authorized action
    -> verify the real outcome and reconcile dependent plans
    -> improve future assistance without silently rewriting history
```

A receipt is not consumption. A calendar opening is not willingness to travel.
An offer to help is not an accepted appointment. An order is not a delivery, and
a delivery is not proof that a maintenance task was completed.

The system must preserve those distinctions. It should be useful with incomplete
information rather than require omniscience or continuous surveillance.

## Familiar experiences, shared capabilities

The following are synthetic illustrations, not records about real people or
claims that specific integrations are available.

| Experience | Useful response | Reusable capability |
| --- | --- | --- |
| Purchase history suggests a condiment is usually replaced every few shopping trips. | Estimate whether it may run out before the next order; account for stock uncertainty and suggest replenishment. | Consumption estimation and replenishment planning. |
| A person accepts a commitment to help a relative install an appliance. | Assemble the agreed scope, relevant instructions, tools, parts, and missing prerequisites before the appointment. | Commitment preparation and dependency checking. |
| A household member requests that a picture be hung. | Preserve the agreed location, dimensions, mounting constraints, materials, and completion evidence. | Intent capture and resource-aware task preparation. |
| A vehicle reports low washer fluid. | Connect the alert to the right consumable, available stock, and an authorized purchase or refill task. | Condition-to-maintenance planning. |
| A recorded pet-care due date approaches. | Prepare a task or appointment proposal and close it only when the relevant completion is recorded. | Recurring obligations and outcome verification. |
| Another household's assistant proposes a vacation. | Exchange permitted candidate windows and constraints, prepare costed options, and seek the required approvals. | Purpose-bound multi-party coordination. |
| Fresh tracker evidence suggests an essential item stayed behind. | Warn during the useful action window without treating stale location data as certainty. | Timely mismatch detection. |
| An upcoming event requires preregistration. | Detect the prerequisite and deadline, prepare the registration step, and retain confirmation. | Requirement and expectation tracking. |
| A new school menu arrives. | Reconcile accepted meal information, calendars, meal plans, and relevant shopping needs. | Evidence intake, change propagation, and external reconciliation. |

The value increases when these domains connect. An accepted repair commitment
may reduce available cooking time. That can change the proposed dinner, its
ingredient needs, and a planned pickup. Resolve those dependencies coherently
rather than produce four unrelated notifications.

## Make routine intelligence reusable

Established relationships, date arithmetic, validation, authorization,
deduplication, and known procedures belong in testable software. Statistical
estimates and constrained planning can handle uncertainty without a language
model reconstructing the problem from an archive on every run.

Models should interpret messy inputs, propose uncertain connections, explain
options, and handle unfamiliar situations. Small or local models should be able
to consume bounded, authorized context and structured outcomes. More capable
models can handle ambiguity where that capability is genuinely needed.

The design target is not to remove AI. It is to stop paying in tokens, latency,
and inconsistency to rediscover stable operational knowledge. A model remains a
replaceable worker, not the exclusive owner of the person's understanding.

## Food illustrates the complete loop

A curated recipe collection or functional-cooking cookbook can supply structured
domain knowledge: ingredients, techniques, substitutions, equipment, preparation
time, portions, and stated recipe characteristics.

Combine that knowledge with individual and household preferences, restrictions,
planned attendance, available time, desired variety, existing stock, and budget.
Propose a rotating weekly menu. Let people approve or revise it. Derive ingredient
and preparation requirements, prepare authorized fulfillment, then learn from
what was actually cooked, eaten, enjoyed, changed, or wasted.

A recipe's name or marketing description is not evidence for a health outcome.
Health-related inputs retain their own consent and evidence requirements.

Fulfillment is replaceable: a shopping list, grocery cart, delivery service,
prepared meal, or a future compatible robotic kitchen. Physical automation is
an extension, not a prerequisite, and cannot bypass device safety or approval.
Do not assume a retailer or appliance exposes an integration until verified.

## Learn progressively without taking over

Onboarding should begin with a useful domain, a few explicit preferences, and
consent for the relevant records. Do not require someone to document their whole
life before receiving value.

Corrections must be easy: there are still two bottles; that recipe is too much
work on a weekday; the proposed date was never agreed. Preserve their scope and
provenance. Silence is not approval, dislike, or proof of completion.

Autonomy should grow through explicit, revocable standing policies, not through
a model deciding it has earned broader authority. A person can permit drafting
routine carts while retaining purchase approval, spending limits, and exceptions.

Multiple people have different preferences, private records, responsibilities,
and permissions. Another household's assistant should receive only the permitted
constraints necessary to cooperate, not an unrestricted copy of a calendar or
profile. A household is not a single shared credential or a universal consent.

## Protect attention as carefully as data

A machine-level change is not automatically a human notification. Choose the
recipient, timing, urgency, surface, and level of detail deliberately. Combine
related suggestions, suppress obsolete ones, support quiet periods, and preserve
unread state without repeatedly interrupting someone.

Broadcasts signal changes. Durable work records preserve unfinished obligations.
A persistent inbox preserves what a person has not seen or resolved. None is a
substitute for the others.

A useful warning may need to execute locally. One architecture does not require
one execution location. Disconnection or a missed live message must not silently
destroy important work.

## What success means

Success is less cognitive and logistical burden without unwanted control.
Measure time and supervision saved, preventable waste avoided, obligations met,
useful preparation, reliable recovery, and outcomes people actually wanted.
Balance those against false alarms, corrections, interruptions, privacy costs,
and operating expense. More notifications, more purchases, more model calls,
and more retained data are not success measures by themselves.

The system must remain understandable, correctable, exportable, and replaceable.
A different authorized model or interface should continue useful work without
the person rebuilding their life history or surrendering new authority.

## How this fits the repository series

This parent owns the human-outcome framing and cross-program orientation.
[THESIS.md](THESIS.md) retains invariant principles. [FEATURE-ROADMAP.md](FEATURE-ROADMAP.md)
translates this direction into reusable capability targets and proposed dependency
gates. [HORIZON.md](HORIZON.md) retains broader future possibilities.

[ROUTES.md](ROUTES.md) identifies component ownership. Protocol semantics,
PostgreSQL implementation, bounded access, domain workflows, and agent execution
remain separate concerns with their own evidence and review. Do not create a
second task database here or duplicate private deployment records in public docs.

Build thin, useful slices, but evaluate them against this whole-system purpose:
**personal infrastructure that gives people their time and attention back.**
