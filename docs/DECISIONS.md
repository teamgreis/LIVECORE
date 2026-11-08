# LIVECORE Decision Register

This register is the navigable index for the 100 product-planning decisions. The complete numbered baseline, including each selected direction, is maintained in [MASTER_PLAN.md](MASTER_PLAN.md).

## Decision status

All 100 choices are **accepted as planning direction**. They are not proof of implementation, feasibility, certification or production readiness. Detailed engineering decisions remain open where numerical budgets, protocol versions, supported devices or legal requirements have not yet been established.

## Core architectural commitments

| Area | Accepted direction |
|---|---|
| Product audience | FOH engineers and live performers equally |
| Audio core | Self-developed native real-time engine |
| Mixer and routing | Modular mixer, channel strips, free routing and multi-view routing |
| Processing | Modular DSP, plugin standards and own API |
| Show control | Scenes, events, macros, timelines, MIDI, timecode and multi-discipline control |
| Distribution | Federated, self-healing cluster with bounded real-time resource reservations |
| Synchronization | Unified time/event architecture with explicit failure modes |
| Projects | Portable show packages, transactional config, backups, restore and archives |
| Hardware | Open adapters, profiles, certification and compatibility lifecycle |
| Reliability | Isolation, redundancy, observability, recovery and service assurance |
| Security | Zero-trust identity, least privilege, audited controls and independent assurance |
| AI | Specialist agents with local-first critical tasks and governed permissions |
| Operations | Workforce, safety, logistics, economics, communications and production readiness |
| Learning | Integrated documentation, contextual help, simulations and competency paths |
| Governance | Product/architecture governance with independent review for critical changes |

## Decision record rules

Each future architecture decision should have:
- A stable identifier and title
- Status: proposed, accepted, superseded or rejected
- Context and problem statement
- Options considered and rationale
- Consequences, risks and alternatives
- Security, reliability and real-time impact
- Migration and compatibility implications
- Owner, reviewers and approval date

Use Architecture Decision Records (ADRs) for consequential technical choices. Do not silently reinterpret the original 100 decisions; record refinements as new decisions with explicit links to the baseline.
