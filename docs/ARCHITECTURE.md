# LIVECORE Architecture Baseline

## Architectural style

LIVECORE uses a **self-healing federated architecture**: central coordination provides shared identity, configuration, topology, policy and observability, while decentralized nodes execute time-critical work locally. Loss of a coordinator or external service must not automatically stop an already-running critical audio path.

The system is not one monolithic process. It is a collection of isolated services with explicit contracts, bounded resource budgets and defined degraded modes.

## Logical domains

1. **Real-time audio domain** — native audio engine, scheduler, device I/O, DSP graph, buses, monitor paths, metering and recording taps.
2. **Show-control domain** — scenes, cues, timelines, macros, MIDI, timecode, lighting/video/stage adapters and event orchestration.
3. **Distributed runtime domain** — node membership, resource reservations, time synchronization, state replication, failover and health.
4. **Device integration domain** — discovery, drivers/adapters, capability profiles, certification state and lifecycle.
5. **Project and configuration domain** — show packages, versioned state, transactional changes, dependencies, restore points and archives.
6. **Operator experience domain** — specialized FOH, monitor, performer, routing, system, production and administration workspaces.
7. **Extension and API domain** — plugin hosting, SDK, adapter API, event streams, sandboxing and trust/revocation.
8. **Security and identity domain** — identity, roles, device trust, policy, audit, secrets and security monitoring.
9. **Observability domain** — metrics, traces, logs, topology, diagnostics, event correlation and forensic exports.
10. **Production operations domain** — workforce, safety, logistics, economics, communications, customer support and deployment.
11. **Knowledge and AI domain** — documentation, training, specialist agents, search and decision support.
12. **Governance domain** — architecture decisions, compatibility policy, certification, release approvals and lifecycle controls.

## Real-time design

- The native audio engine owns the critical processing path.
- The scheduler must define execution classes, deadlines, affinity/parallelism rules, overload behavior and measurable timing guarantees.
- Real-time threads must avoid unbounded locks, unpredictable allocation, blocking I/O and uncontrolled callbacks.
- Best-effort AI, UI, analytics, archive, network management and cloud tasks must not preempt reserved real-time capacity.
- DSP quality/load profiles may change only through explicit, validated transitions; no silent signal-path mutation.
- Distributed audio processing is permitted only when the complete hardware/network/clock path satisfies a measured timing budget. Otherwise processing remains local.
- Failure behavior is explicit: continue locally, mute/hold/transition to a defined safe state, fail over, or request operator action according to validated policy.

## Distributed state and transactions

Show configuration and runtime state are distinct. Configuration updates use versioned transactions with validation, conflict detection, staged activation, commit acknowledgments and rollback. Network partitions must not produce ambiguous split-brain control. Nodes rejoining a cluster reconcile against explicit version and authority rules.

## Time and synchronization

A common time model coordinates audio clocks, network timing, timecode, cues and automation. Every synchronized subsystem declares its clock source, accuracy, drift behavior, latency and holdover capability. Loss of timing must trigger a documented degraded mode rather than an implicit resynchronization that surprises operators.

## Extensibility and isolation

Plugins, adapters, automation scripts and AI agents receive least-privilege capabilities. They run in process or service boundaries appropriate to their risk, with resource quotas, watchdogs, versioned APIs and revocation. An extension cannot gain direct unrestricted access to the engine, credentials, unrelated show data or safety-critical controls.

## User experience

Specialized workspaces share a consistent interaction model. Role, task, device and context may prioritize information, but critical controls remain stable and discoverable. UI layout changes are validated, versioned and reversible. Touch, mouse and keyboard are first-class input methods.

## Cross-platform deployment

The intended client/server footprint spans Windows, Linux and macOS, with dedicated services on separate nodes where necessary. OS-specific audio backends and device drivers sit behind explicit platform adapters. Support claims must be tied to tested OS versions, hardware and driver combinations.

## Architecture quality attributes

- Deterministic and measurable real-time behavior
- Fault containment and graceful degradation
- Security by default and least privilege
- Offline autonomy for critical operation
- Interoperability and versioned contracts
- Portability and reproducible deployment
- Observability with bounded overhead
- Reversible configuration and safe migration
- Accessibility, localization and operator clarity

## Required architecture artifacts before production

Context/container/component diagrams; data-flow and trust-boundary diagrams; real-time scheduling model; timing budget; network and clock design; failure-mode analysis; threat model; state/transaction model; extension sandbox model; hardware compatibility matrix; operational runbooks; and test evidence. Each artifact must be versioned with the implementation it describes.
