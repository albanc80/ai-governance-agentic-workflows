# Rules: Data Governance

## Source of Truth
The ultimate source of truth for agentic behavior is the **Agent Card** and the **Forbidden Actions List**.

## Data Quality Standards
1. **Provenance:** Every claim in the governance framework must be tagged (e.g., `[documented]`, `[verbal]`).
2. **Immutability:** Audit logs must be stored in a format that prevents retroactive editing.
3. **Privacy:** All PII must be stripped from training/few-shot datasets used in the Golden Dataset.

## Retention Policy
- **Audit Logs (Critical Assets):** Retained for 10 years (Regulatory Requirement). `[REVIEW]`
- **Audit Logs (Informational):** Retained for 1 year.
