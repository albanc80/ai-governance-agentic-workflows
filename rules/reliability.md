# Reliability & Cost Governance: Agentic Workflows

## Goal
Prevent "Runaway Agents," infinite loops, and unsustainable token expenditure.

## Ground Rules
1. **Recursion Limits:** Every agentic task has a hard cap on the number of tool-calls/turns (Default: 10). Upon reaching the limit, the agent must stop and request human intervention.
2. **Budget Circuit Breakers:** Per-session cost limits are enforced. If a single thread exceeds a predefined token/cost threshold, the process is paused for human approval.
3. **Accuracy Benchmarks:** No agent is deployed to the pilot without passing a "Golden Dataset" benchmark, ensuring core reliability on known high-value tasks.
4. **State Recovery:** Agents must implement checkpointing. In the event of a crash or timeout, the agent must be able to resume from the last successful tool-call rather than restarting the entire workflow.
5. **Loop Detection:** The system must monitor for repetitive tool calls (same input $\rightarrow$ same output $\rightarrow$ same tool call) and trigger a failure state if a loop is detected.

## Provenance
- [stakeholder-verbal, Owner, 2026-07-04]
