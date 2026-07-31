# O&G Reliability & Cost Governance (Enterprise Grade)

## Goal
Ensure system stability and prevent catastrophic failure or unsustainable resource expenditure.

## Ground Rules
1. **Deterministic Fallbacks:** In "Critical Asset" workflows, if agent confidence falls below 95%, the system must automatically fail-over to a deterministic, rule-based legacy system.
2. **Cost-to-Risk Ratio:** For high-risk operations, token efficiency is deprioritized in favor of maximum reasoning depth (Chain-of-Thought) and multi-agent verification.
3. **O&G Golden Dataset:** All agents must be validated against a "Black Swan" dataset containing edge cases such as pipeline ruptures, sensor failures, and contradictory telemetry.
4. **Recursion & Loop Protection:** Hard limit of 10 tool-calls per task. Repetitive tool-call patterns (Same Input $\rightarrow$ Same Output) must trigger an immediate system pause and alert.
5. **State Checkpointing:** Every "Critical" workflow must checkpoint state after every tool-call to ensure recovery from hardware or network failure without state loss.

## Provenance
- [industry-standard, ISO 27001]
- [stakeholder-verbal, Owner, 2026-07-04]
