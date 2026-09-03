# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| **Correction Loop** | Planner accepts, modifies, or rejects an AI recommendation + actual forecast outcome | Better understanding of which signals and recommendations work in similar situations | Y | active |
| **Preference Loop** | Planner/team review patterns, thresholds, accepted recommendations, override behavior | Planner- and team-specific prioritization and recommendation preferences | Y | broken |
| **Network Learning Loop** | De-identified outcome patterns and reusable planning signals across customers | Stronger CPG benchmarks and reusable decision intelligence | Y | missing |

**Broken loop identified by partner:** Preference Loop — ShelfSense observes planner behavior but does not yet persist and reuse that behavior as a structured preference profile.

**Fix plan:** Capture structured reasons when planners accept, modify, or reject recommendations; associate those decisions with planner/team context and actual outcomes; and use the resulting signals to personalize future prioritization and recommendations.

---

## Context Connectivity

ShelfSense already connects several domains within a customer's demand-planning workflow:

**Sales history → Promotions → Inventory → Retailer forecast → Forecast performance → Planner decision → Actual outcome**

This gives ShelfSense strong domain context and supports the **4/5 Contextual Moat** identified in Module 1.

The main silo exists **between customers**. Raw customer commercial data remains isolated because of contractual and privacy constraints, limiting ShelfSense's Network Loop.

The target architecture therefore keeps raw customer data separated while allowing permissioned, de-identified signals such as forecast-error patterns, promotion archetypes, correction outcomes, and benchmark ranges to contribute to reusable CPG intelligence.

---

## Governance Policy

**Scope:**  
AI-assisted forecast prioritization, driver analysis, explanation, and recommended planning actions inside ShelfSense.

**Autonomy boundaries:**  
The AI may identify issues, analyze evidence, and recommend actions. It may not autonomously execute material forecast changes, inventory decisions, or commercial commitments in the initial Copilot phase.

**Escalation triggers:**  
Human review is required when:
- confidence is below 70%;
- critical data is missing or stale;
- planning signals conflict materially;
- the recommendation exceeds configured forecast-change thresholds;
- the SKU, retailer, or promotion has high financial impact;
- the recommendation falls outside evaluated scenarios.

**Audit cadence:**  
- Monthly review of accuracy, hallucination, overrides, latency, and drift
- Quarterly governance review of model performance, vendor exposure, data usage, and incidents
- Immediate review after any material AI-related planning incident

**Regulatory exposure (EU AI Act / other):**  
ShelfSense is a B2B demand-planning Copilot and is not currently designed to make decisions about individuals or other obviously high-risk regulated use cases. However, deployments must still maintain appropriate transparency, data governance, auditability, privacy controls, vendor documentation, and human oversight, with requirements reassessed as markets and product autonomy expand.

---

## Agent Topology
<!-- If using agents: what can each agent do? What can't it do? Who approves what? -->

ShelfSense v1 is a **Copilot, not an autonomous multi-agent system**. AI capabilities are separated into constrained components with explicit boundaries:

| Component | Can Do | Cannot Do | Approval |
|-----------|--------|-----------|----------|
| **Exception Triage** | Rank and flag forecasts that require attention | Change forecasts or inventory plans | No approval needed to flag |
| **Driver Analysis** | Analyze sales, promotion, inventory, and retailer signals and explain likely drivers | Invent missing evidence or override source data | Planner reviews explanation |
| **Recommendation Engine** | Propose a planning action with rationale and confidence | Execute material forecast changes | Planner approval required |
| **Reliability / Policy Gate** | Check confidence, data freshness, thresholds, and escalation rules | Override governance rules | Automatically blocks or escalates |

The **Demand Planner remains the accountable decision-maker** for consequential planning changes.

---

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| **Public generative AI assistants used for planning analysis** | Individual employees | H | govern |
| **Microsoft Copilot used within approved enterprise environment** | IT / Business teams | M | keep |
| **Unapproved spreadsheet AI plug-ins / extensions** | Individual planners | H | kill |

**Total tools found:** 5  
**Tools after triage:** 3  
**Estimated hidden spend:** ~$2,400/month across uncoordinated individual subscriptions and tools

### Shadow AI Policy

Approved AI tools may be used only within enterprise-controlled environments and according to customer-data handling rules. Customer sales, promotion, retailer, inventory, or forecast data must not be uploaded into unapproved public AI tools.

The objective is not to prohibit useful AI experimentation, but to move high-value workflows into governed ShelfSense capabilities where data access, evaluation, cost, auditability, and feedback can be managed centrally.
