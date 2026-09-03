# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| **Correction Loop** | Planner accepts/modifies/rejects an AI insight + reason + actual outcome | Better customer-specific exception prioritization and explanation | Y | active |
| **Preference Loop** | Planner/team thresholds, review patterns, accepted/rejected recommendations | Customer/team-specific prioritization preferences | Y | broken |
| **Network Learning Loop** | Permissioned, de-identified patterns across customers | Shared benchmark intelligence | Y | missing |

**Broken loop identified by partner:** Preference Loop — ShelfSense observes planner behavior but does not yet persist it as a structured learning asset.

**Fix plan:** Add structured reason capture, associate feedback with planner/team/category context, and connect each decision to subsequent outcomes. Build customer-level personalization first. Do not make cross-customer network effects a dependency of the strategy.

---

## Context Connectivity

Within one customer, the target decision lineage is:

**Sales history → Promotion → Inventory → Retailer input → Forecast → AI flag → Planner decision + reason → Actual outcome**

ShelfSense should persist that lineage so future insights can reference not only the raw data but also what the planning team previously decided and what happened afterward.

### Current silo
The largest silo is **between customers**. Raw commercial data must remain isolated unless contracts explicitly permit another use.

### Strategic rule
Cross-customer learning is opt-in and secondary. The first compounding moat must work entirely within one customer's governed data boundary.

---

## Governance Policy

**Scope:**  
AI-assisted forecast exception prioritization, grounded driver explanation, and suggested investigation/planning actions.

**Autonomy boundaries:**  
- AI may rank, explain, and recommend.
- AI may not autonomously execute material forecast, inventory, pricing, production, or commercial changes in v1.
- Autonomy expansion requires a separate governance approval and reliability case.

**Escalation triggers:**  
- calibrated confidence <70%;
- stale/missing critical data;
- materially conflicting signals;
- high financial exposure;
- out-of-distribution / unevaluated scenario;
- policy or permission conflict;
- model/provider change that has not passed regression testing.

**Audit cadence:**  
- weekly pilot quality review;
- monthly reliability, cost, and feedback-loop review;
- quarterly model/vendor/data-governance review;
- immediate incident review after any material AI-related failure.

**Data governance:**  
- customer data remains tenant-isolated;
- least-privilege access applies to retrieval;
- prompt/output telemetry follows defined retention policy;
- model-training use requires explicit contractual permission;
- model/provider changes require documented regression testing.

**Regulatory exposure (EU AI Act / other):**  
No definitive regulatory classification is assumed in this fictional case. Before EU deployment or any expansion in autonomy, legal counsel must confirm applicable classification, transparency, data-governance, documentation, and human-oversight obligations.

---

## Agent Topology

ShelfSense v1 remains a **Copilot**, not an autonomous multi-agent system.

| Component | Can Do | Cannot Do | Approval |
|-----------|--------|-----------|----------|
| **Exception Triage** | Rank/flag high-impact forecast exceptions | Change forecasts or inventory plans | No approval needed to surface |
| **Driver Analysis** | Retrieve and summarize supporting sales, promotion, inventory, and retailer signals | Invent missing evidence or state unsupported causality | Planner reviews |
| **Action Suggestion** | Suggest next investigation or planning action | Execute consequential changes | Planner approval required |
| **Reliability / Policy Gate** | Check data freshness, risk tier, permissions, and escalation rules | Override governance rules | Automatically blocks/escalates |
| **Feedback Capture** | Record Accept/Modify/Reject + reason + eventual outcome | Use customer data outside permitted boundaries | Governed by tenant policy |

The planner remains accountable for consequential demand decisions.

---

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| Public generative AI used with planning data | Individual employees | H | govern |
| Approved enterprise Copilot environment | IT / business teams | M | keep / govern |
| Unapproved spreadsheet AI plug-ins/extensions | Individual planners | H | kill |

**Total tools found:** TBD — complete a 30-day discovery audit  
**Tools after triage:** TBD  
**Estimated hidden spend:** TBD — validate through procurement/expense review

### Shadow AI Policy

Do not invent precision before the audit. The first governance action is discovery: identify tools, data flows, owners, contracts, and spend.

Approved AI may be used only in enterprise-controlled environments consistent with customer data-handling rules. Customer sales, promotion, retailer, inventory, or forecast data must not be uploaded into unapproved public AI tools.

---

## Kill Switch

ShelfSense must be able to:
- disable generative recommendations while preserving core SaaS planning;
- revert to deterministic exception rules if model reliability degrades;
- isolate a faulty model/provider;
- pause learning/feedback ingestion without losing audit history; and
- notify affected customers when a material incident requires it.
