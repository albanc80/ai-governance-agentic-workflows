# Decision: Establish 3-Domain Governance Framework

## Status: Decided
**Date:** 2026-07-04
**Owner:** Alberto

## Context
We needed a way to define AI governance for agentic workflows that balances the "magic" of autonomy with the strict requirements of the CISO and Cloud teams.

## The Decision
Adopt a three-domain governance structure:
1. **Security:** Focus on isolation, sanitization, and boundaries.
2. **Reliability/Cost:** Focus on limits, benchmarks, and recovery.
3. **Compliance:** Focus on audit traces and the 3-Tier HITL approach.

## Rationale
- Separates technical constraints (Security/Cost) from process constraints (Compliance).
- Allows us to tune "Tiers" of autonomy without rewriting the security architecture.
- Provides clear categories for different stakeholders (CISO $\rightarrow$ Security; Cloud $\rightarrow$ Cost; PM $\rightarrow$ Compliance/HITL).

## What would reverse this
- If the pilot project reveals that the "3-Tier" approach is too rigid and kills the utility of the agent.
- If a security breach occurs that bypasses the current "Forbidden Actions" logic.
