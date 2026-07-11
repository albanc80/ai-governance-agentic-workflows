# AI SDLC Maturity Scorecard

Use this scorecard to determine if an agent is production-ready. 
**Score: 0 (Missing) to 5 (Optimized)**

| Domain | Control Requirement | Score (0-5) | Evidence/Artifact |
| :--- | :--- | :--- | :--- |
| **Governance** | Business ownership & AI Charter defined | | |
| **Risk** | Risk Register mapped to Asset Criticality | | |
| **Regulatory** | Compliance mapping to API RP 75 / NIST | | |
| **Data** | Data lineage and quality verified (DAMA) | | |
| **Security** | HSM-signed tools & Sandbox isolation | | |
| **Privacy** | DPIA completed and PII filters active | | |
| **Model** | Model Card and versioning established | | |
| **Agents** | Agent Card defines Restricted Actions | | |
| **Human Oversight**| HITL Tiers (1-3) implemented | | |
| **Testing** | Golden Dataset & Red-Teaming passed | | |
| **Monitoring** | Real-time audit trace in WORM storage | | |
| **Incident Resp.** | Kill-Switch tested and documented | | |
| **Business Value** | KPIs defined and monitored | | |

**Total Score Calculation:** $\frac{\sum \text{Scores}}{65} \times 100$

**Interpretation:**
- **90-100%:** Production-Ready.
- **75-89%:** Minor Remediation required.
- **60-74%:** Significant gaps; block deployment.
- **< 60%:** Not production ready; return to Design phase.
