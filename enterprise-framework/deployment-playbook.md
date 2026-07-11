# Operational Deployment Playbook: AI Governance

## Goal
Standardize the transition of AI agents from development to production in O&G environments.

## The Onboarding Lifecycle
No agent may enter production without completing the following four gates:

### Gate 1: Risk Assessment
- Map the agent to the **Asset Criticality Matrix**.
- Define the **Forbidden Actions** specific to the agent's domain.
- Identify required **PVS (Physical Verification Steps)**.

### Gate 2: Adversarial Red-Teaming
- Attempt to bypass the Guardrail Layer using prompt injection.
- Attempt to force the agent to execute a "Forbidden Action."
- Simulate sensor failure to test **Deterministic Fallbacks**.

### Gate 3: Shadow Mode (30 Days)
- Agent runs in parallel with existing human workflows.
- Agent's "Proposed Actions" are compared against human "Actual Actions."
- Accuracy is measured against the **Golden Dataset**.

### Gate 4: Pilot Deployment
- Limited rollout to a single asset/facility.
- 100% HITL (Tier 3) enabled for all write operations.
- Weekly review of the Audit Trail to refine ground rules.

## Post-Deployment Maintenance
- **Weekly Sweep:** Review all "Confidence $< 90\%$" actions to update the Golden Dataset.
- **Annual Recertification:** Re-run Red-Teaming against new LLM versions/model updates.
