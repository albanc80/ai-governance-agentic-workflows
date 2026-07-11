# Compliance & Governance: Agentic Workflows

## Goal
Ensure complete auditability and maintain a balanced "Human-in-the-Loop" (HITL) approach.

## Ground Rules
1. **The Audit Trace:** Every agent session must generate a deterministic log following the pattern: `[Timestamp] [Thought] [Action] [Result] [Human-Approval-ID]`. Logs are immutable and stored in a central compliance repository.
2. **HITL Tiers (The Balance Approach):**
    - **Tier 1 (Autonomous):** Low-risk "Read" operations (e.g., querying a dashboard). No approval needed.
    - **Tier 2 (Conditional):** Medium-risk "Write" operations (e.g., updating a project status). Approval required if the agent's confidence score is below 90%.
    - **Tier 3 (Mandatory):** High-risk "Impact" operations (e.g., sending external communications, deploying code). Mandatory human sign-off regardless of confidence.
3. **Provenance Tracking:** All final deliverables produced by an agent must include a "Source" section citing the specific documents or tool results used to derive the answer.
4. **Human Override:** A human operator must be able to interrupt and take over an agentic thread at any point without losing the current state.

## Provenance
- [stakeholder-verbal, Alberto, 2026-07-04]
