# Enterprise Architecture: AI Governance for Energy & O&G

## 1. Asset Criticality Matrix
All agentic workflows must be classified by the impact of their failure on physical assets and human safety.

| Agent Class | Impact Level | Example | Governance Mode | HITL Requirement |
| :--- | :--- | :--- | :--- | :--- |
| **Informational** | Low | Market Analysis, Policy Search, Knowledge Retrieval | **Autonomous** | Tier 1 (None/Log only) |
| **Operational Support** | Medium | Maintenance Scheduling, Log Analysis, Report Generation | **Conditional** | Tier 2 (Confidence-based) |
| **Critical Assets** | High | Valve Control, Pressure Settings, Grid Load, ESD Systems | **Mandatory HITL** | Tier 3 (Physical Verification) |

## 2. The Safety-Valve Protocol (PVS)
For any action classified under **Critical Assets**, the system enforces a **Physical Verification Step (PVS)**.

**The Logic Flow:**
1. Agent proposes an action $\rightarrow$ 2. System flags as "Critical" $\rightarrow$ 3. Mandatory Tier 3 Approval $\rightarrow$ 4. **Field Engineer performs Physical Verification of asset state** $\rightarrow$ 5. PVS Signature uploaded to Audit Trail $\rightarrow$ 6. Action Executed.

## 3. The Governance Stack
- **Guardrail Layer (Technical):** Real-time filters, API sandboxing, and HSM-signed tool calls.
- **Oversight Layer (Process):** 3-Tier HITL and immutable audit trails.
- **Compliance Layer (Regulatory):** Mapping to ISO 27001, NIST AI RMF, and API RP 75.
