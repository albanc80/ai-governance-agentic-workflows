# AI Governance Framework for Agentic Workflows

Enterprise-grade governance for AI agents operating in high-stakes industrial environments (Energy & Oil & Gas). This framework answers one question: **how do you give AI agents real power without losing human control?**

It provides a complete, deployable system: a 3-tier human-in-the-loop (HITL) strategy, an asset criticality matrix, a physical verification protocol (PVS), an AI SDLC pipeline, audit schemas, and the templates needed to operationalize all of it.

---

## What this is

- **A decision framework** — classifies every agent action by risk and applies the right governance mode.
- **A deployment playbook** — 4-gate onboarding (Risk → Red-Team → Shadow → Pilot) before any agent touches production.
- **An engineering spec** — the technical requirements (governance proxy logic, HSM-signed requests, PVS state machine, WORM-compatible audit schema) needed to implement it.
- **A validation kit** — Golden Datasets, agent cards, red-teaming checklists, and audit log schemas.
- **Reference-aligned** — structured around ISO/IEC 42001, NIST AI RMF, and DAMA-DMBOK.

It is **not** a compliance checklist. It is a reasoning system that surfaces risk and enforces control where it matters.

---

## The core model: 3-Tier HITL Strategy

| Tier | Governance Mode | Example Action | Oversight |
| :--- | :--- | :--- | :--- |
| **Tier 1** | Autonomous | Low-risk reads, status updates | None (log only) |
| **Tier 2** | Conditional | Medium-risk writes, recommendations | Confidence-based approval (< 90% → human sign-off) |
| **Tier 3** | Mandatory HITL | High-risk / critical asset changes | Mandatory human sign-off + PVS |

For the Energy & O&G specialization, an **Asset Criticality Matrix** maps agents to risk classes (Informational / Operational Support / Critical Assets), and the **Physical Verification Step (PVS)** requires a field engineer to physically verify asset state before any critical command is released.

---

## Repository structure

```
CLAUDE.md                        Operating manual for agentic tooling (internal)
INDEX.md                         Master routing
enterprise-framework/
  architecture.md                Asset Criticality Matrix, Safety-Valve (PVS) protocol
  deployment-playbook.md         4-Gate onboarding: Risk → Red-Team → Shadow → Pilot
  rules/
    security_og.md               Air-gapping, HSM-signing, Forbidden Actions
    reliability_og.md            Deterministic fallbacks, Black Swan datasets
    compliance_og.md             Golden Audit Trail, WORM storage
  templates/
    agent-card-*.md              Agent identity + governance mode (e.g. BHA Optimizer)
    risk-assessment-template.md  Standard risk form for new agents
    red-teaming-checklist.md     Adversarial bypass testing
    audit-log-schema.md          Immutable JSON trace schema
    pvs-signature-log.md         Physical verification sign-off records
    golden-dataset-bha-synthetic.md  Benchmark scenarios for validation
ai-sdlc-governance/
  sdlc-architecture.md           11-stage AI SDLC lifecycle
  sdlc-artifacts.md              Required artifacts per stage
  sdlc-scorecard.md              Maturity scoring
  templates/agent-card-template.md
final_deliverables/
  framework_documentation.html   Stakeholder/executive presentation
  engineering_implementation_spec.html  Developer implementation guide
decisions/                       Append-only decision log
rules/                           Operating rules (security, reliability, compliance, data, discovery)
knowledge/                       Strategy, roadmap, org, features
docs/                            Overview, schemas, workflows
```

---

## How to use this

### 1. For a new AI agent (the main path)

1. **Classify** — use the Asset Criticality Matrix to determine the agent's risk class.
2. **Card it** — fill out an Agent Card (scope, forbidden actions, governance mode).
3. **Assess** — complete the Risk Assessment template.
4. **Validate** — run the agent against a Golden Dataset (synthetic first, real data second).
5. **Red-team** — run the Adversarial Red-Teaming checklist.
6. **Deploy** — shadow mode → pilot (100% HITL) → production, per the deployment playbook.

### 2. For the engineering team

Open [`final_deliverables/engineering_implementation_spec.html`](./final_deliverables/engineering_implementation_spec.html). It contains the governance proxy pseudocode, HSM signing requirements, the PVS state machine, the JSON audit schema, and the CI/CD validation gates.

### 3. For executives / stakeholders

Open [`final_deliverables/framework_documentation.html`](./final_deliverables/framework_documentation.html).

---

## Validation & evidence

The framework has been validated at two levels:

- **Synthetic stress test** — the BHA Maintenance Optimizer agent (Pilot B) was tested against a 5-scenario Golden Dataset covering autonomous, conditional, HITL-escalation, critical-alert, and data-gap paths. All scenarios passed.
- **Real-data audit** — validated against structured tables derived from Equinor's open **Volve Field** and **Northern Lights CO₂ storage** datasets:
  - **Bias detection** — failures distributed proportionally across criticality classes; no discrimination by well complexity.
  - **Risk assessment** — strong correlation between high-criticality assets and failure severity.
  - **Explainability** — failure events traceable to specific integrity metrics.
  - **Compliance auditing** — silent anomalies (integrity flags with no recorded action) surfaced for remediation.
  - **Predictive maintenance** — ~14-day lead time between integrity anomaly and failure, supporting a 14-day warning rule.

See [`NOTICE`](./NOTICE) for data attribution.

---

## Deployment readiness

The framework ships with:

- ✅ Risk assessment, red-teaming, and audit templates
- ✅ Governance proxy logic and PVS state machine specs
- ✅ WORM-compatible audit trail schema
- ✅ CI/CD validation gates
- ✅ Stakeholder and engineering deliverables

## License

Apache License 2.0 — see [LICENSE](./LICENSE).
