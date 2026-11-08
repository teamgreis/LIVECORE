# LIVECORE Security Baseline

## Security objectives

Protect live production continuity, operator authority, show/project confidentiality, device integrity, partner boundaries and the safety of people and equipment. Security controls must not introduce unbounded latency into critical audio paths.

## Identity and access

- Use federated identity where appropriate, MFA for privileged and external access, and short-lived scoped grants.
- Enforce least privilege across people, devices, services, plugins, adapters and AI agents.
- Separate operator, administrator, developer, support, vendor and emergency roles.
- Record privileged actions in tamper-resistant audit logs.
- Support rapid revocation and controlled offline credential behavior.

## Device trust

Devices authenticate and declare identity, capabilities, software/firmware version and trust posture. Trust is continuously assessed. Suspicious devices may be isolated, but the system must first evaluate dependencies and the consequences for active audio and safety functions. Automatic isolation must not create an unexamined production hazard.

## Network security

The selected planning direction is monitoring and alerting for anomalous network activity; operators decide countermeasures. Use secure management interfaces, authenticated control protocols, explicit trust boundaries, network visibility and documented hardening profiles. Do not silently block production traffic based solely on an anomaly score.

## Plugins, adapters and AI agents

- Signed artifacts, provenance, dependency checks and reproducible build evidence.
- Sandboxing, capability permissions, CPU/memory quotas and watchdogs.
- No direct unrestricted access to critical engine memory, credentials or unrelated show data.
- Versioned APIs and explicit deprecation windows.
- Emergency revocation and safe fallback behavior.
- AI actions affecting critical configuration require validation and authorized human approval.

## Secrets and data

Encrypt sensitive data in transit and at rest where appropriate. Keep secrets out of show files, logs and diagnostics. Classify show content, telemetry, personnel data, safety records and commercial information separately. Provide retention, export and deletion controls appropriate to jurisdiction and contract.

## Logging and incident response

Maintain resilient local event records with central correlation where available. Protect logs against tampering, restrict access, document retention and provide privacy-conscious exports. Incident response includes triage, containment, evidence preservation, communication, recovery and post-incident review.

## Assurance

Use threat modeling, secure code review, dependency and vulnerability scanning, SBOMs, signed releases, penetration testing and independent audits. Operate a responsible disclosure process and risk-based remediation policy.

## Non-negotiable production rule

Security controls must be designed with real-time and safety dependencies. No automated security response may blindly interrupt active audio, timing, intercom or emergency control. Where immediate containment is required, use a validated workflow with explicit operator awareness and a defined safe state.
