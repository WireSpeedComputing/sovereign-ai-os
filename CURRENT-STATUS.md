# Program status

Updated September 7, 2026. This checkpoint distinguishes public source, local work and deployment evidence. It supersedes older program summaries only on the subjects below. Component acceptance and release decisions remain separate.

WIRE SPEED COMPUTING LLC maintains the program. Repository namespace, copyright ownership and license terms are different questions; this update does not transfer rights or change licenses.

| Component | Current evidence | Next gate |
| --- | --- | --- |
| [SMP](https://github.com/jryski/sovereign-memory-protocol/pull/13) | Public draft; package/case validation improvements in draft PR 13 | Independent review; not a published standard |
| [Core](https://github.com/jryski/sovereign-memory-core) | PostgreSQL reference implementation with scope-specific restore evidence | Review open work against exact base/head; no blanket deployment certification |
| [User MCP](https://github.com/jryski/Supabase_user_MCP/pull/66) | PR 65 merged. Subsequent local driver work passes 134 offline tests and both type checks | Lab contract alignment, real login/consent, isolation and revocation tests; local changes are not merged source |
| [Household OS](https://github.com/jryski/Household-OS/pull/3) | Calendar foundation exists; fresh-session routing can bypass HOUSE startup discovery | Boot-gated read path and synthetic regression tests; mobile integration remains separate |
| [Vault](https://github.com/WireSpeedComputing/Sovereign-Vault) | Business-domain implementation and bounded retrieval work | Shared credentials do not establish user/agent identity |
| [Public skills](https://github.com/jryski/Public_AI_SKills) | Versioned public skill repository; local revisions await review | Publish tested revisions through review, not installed-cache edits |

Hermes coordinates workers; the wiki UI is an interface; federated-vault explores a separate storage profile. None independently grants access or proves SMP conformance. Private household operations and lab receipts stay in private repositories.

Household OS is the household operating layer, not merely a calendar connector. Its intended experience includes preparation, coordination, useful reminders and approved action using durable household context. Calendar delivery is an early slice. A provider-neutral frontend remains a direction, not a delivered product.

Current priority: repair reliable household discovery and finish User MCP dogfood integration. Use deterministic checks, Cursor and suitable local models for bounded work. No merge, release, production rollout or new spending is authorized by this status file.
