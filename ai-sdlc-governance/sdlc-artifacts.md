# SDLC Artifact Registry

To maintain auditability, the following artifacts must be produced and version-controlled for every agent.

## 1. Strategy & Design Artifacts
- **AI Governance Charter:** High-level principles (OECD/UNESCO) adopted by the project.
- **Agent Card:** The "ID Card" of the agent (Objectives, Allowed/Restricted actions, HITL checkpoints).
- **Model Card:** Documentation of the underlying LLM (Version, training cut-off, known biases).
- **Prompt Catalog:** Version-controlled system prompts and few-shot examples.

## 2. Data & Tooling Artifacts
- **Data Catalog:** Lineage and ownership of all knowledge sources used by the agent.
- **Tool Registry:** Specification of every tool the agent can call, including the API contract and HSM requirements.
- **DPIA (Data Protection Impact Assessment):** Privacy review for agents handling PII.

## 3. Validation & Security Artifacts
- **AI Risk Register:** Living document tracking identified risks $\rightarrow$ mitigation $\rightarrow$ residual risk.
- **Evaluation Report:** Quantitative results from the Golden Dataset tests.
- **Security Assessment:** Formal sign-off from the CISO on network isolation and sandboxing.

## 4. Operational Artifacts
- **Monitoring Dashboard:** Real-time view of token spend, latency, and HITL trigger rates.
- **Audit Report:** Monthly summary of agent decisions and human overrides.
- **Incident Response Plan:** Step-by-step guide for "Kill-Switch" activation and recovery.
