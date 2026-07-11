# Security Governance: Agentic Workflows

## Goal
Prevent the agent from becoming a security liability or an attack vector.

## Ground Rules
1. **Tool Sandboxing:** Agents must not have direct access to production databases or critical infrastructure. All interactions must be mediated via a secure, authenticated API layer that enforces its own permissions.
2. **Input Sanitization:** Every user input must pass through a "Guardrail" layer to detect and mitigate prompt injection and jailbreak attempts before reaching the agent.
3. **Credential Management:** Agents are prohibited from storing or knowing long-lived secrets. All tool access must use short-lived, scoped tokens managed by the central Cloud Team vault.
4. **Execution Boundaries:** a "Forbidden Actions" list is maintained. Agents are strictly blocked from performing destructive operations (e.g., `DROP TABLE`, `DELETE ALL`, `IAM_UPDATE`) regardless of the LLM's requested tool call.
5. **Data Leakage Prevention:** Agents must not echo PII or sensitive system internals (e.g., stack traces, internal IP addresses) in their final responses to the user.

## Provenance
- [stakeholder-verbal, Alberto, 2026-07-04]
