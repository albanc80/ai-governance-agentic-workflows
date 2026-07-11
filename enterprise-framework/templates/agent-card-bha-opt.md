# Agent Card: BHA Maintenance Optimizer (Pilot-B)

**Agent ID:** `PILOT-BHA-OPT-01`
**Version:** `v0.1-SYNTHETIC`
**Business Objective:** Analyze drilling telemetry to identify early signs of BHA (Bottom Hole Assembly) wear and recommend replacement windows to prevent unplanned NPT (Non-Productive Time).

## 1. Scope & Boundaries
- **Primary Domain:** Drilling Telemetry Analysis.
- **Allowed Actions:** 
    - `query_telemetry`: Read-only access to drilling data.
    - `log_recommendation`: Propose a maintenance window in the operational log.
    - `trigger_alert`: Send a high-priority warning to the drilling engineer.
- **Restricted Actions:** 
    - The agent CANNOT trigger any physical equipment change.
    - The agent CANNOT modify the drilling plan.
- **Out-of-Scope:** Financial cost estimation of the BHA replacement.

## 2. Governance Config
- **Asset Class:** **Operational (Medium)**.
- **HITL Strategy:** 
    - **Tier 1 (Autonomous):** Analyzing telemetry and flagging "Healthy" status.
    - **Tier 2 (Conditional):** Proposing a maintenance window. Required human approval if confidence $< 90\%$.
    - **Tier 3 (Mandatory):** Not applicable for this agent (it has no "Critical Asset" write access).
- **Failure Handling:** If telemetry is contradictory, the agent must trigger a "Data Ambiguity" alert and escalate to a human analyst.

## 3. Technical Stack
- **Model:** Reasoning-heavy LLM (e.g., Claude 3.5 Sonnet) for signal analysis.
- **Memory Strategy:** Short-term session memory for telemetry windows; long-term knowledge of BHA failure patterns.
- **Knowledge Sources:** Volve Telemetry (Synthetic for Pilot), BHA Failure Signature Library.
- **Tools:** `query_telemetry`, `log_recommendation`, `trigger_alert`.

## 4. Escalation Policy
- **Primary Human Contact:** Drilling Engineer.
- **Secondary:** Cloud/Data Team (for telemetry gaps).
- **Emergency Stop:** Immediate suspension of all recommendations if "Loop Detection" is triggered.
