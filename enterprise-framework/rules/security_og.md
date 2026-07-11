# O&G Security Governance (Enterprise Grade)

## Goal
Ensure that AI agents cannot be used as attack vectors for Industrial Control Systems (ICS) or SCADA networks.

## Ground Rules
1. **Network Air-Gapping:** Agents interacting with Critical Assets must reside on isolated networks. Zero direct routing to the public internet is permitted for these agents.
2. **Zero-Trust Tool Execution:** Every tool-call must be authenticated and signed via a Hardware Security Module (HSM). Tooling must follow the principle of least privilege.
3. **O&G Forbidden Actions List:**
    - `[REVIEW]` Agents are strictly prohibited from modifying pressure thresholds in active pipelines.
    - `[REVIEW]` Agents are strictly prohibited from overriding Emergency Shutdown (ESD) systems.
    - `[REVIEW]` Agents are strictly prohibited from modifying valve states in hazardous zones without a confirmed PVS.
4. **Input Sanitization:** All inputs must be processed by an O&G-specific guardrail that detects "industrial-sabotage" prompt patterns.
5. **Data Exfiltration Prevention:** Agents must not transmit telemetry data to external endpoints not explicitly whitelisted by the Cloud Team.

## Provenance
- [industry-standard, NIST AI RMF, API RP 75]
- [stakeholder-verbal, Alberto, 2026-07-04]
