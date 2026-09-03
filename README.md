# ShelfSense AI Product Strategy

> A living AI product strategy built across six modules. Each module strengthens one component of the strategy — from selecting the right AI bet to proving defensibility, economics, reliability, governance, and board-level investment readiness.

---

## Executive Strategy

### Vision
**ShelfSense becomes the trusted decision layer for CPG demand planning.**

### Strategy
Start with a human-in-the-loop AI Copilot for **high-impact forecast exception triage and evidence-grounded driver explanation**, then build customer-specific decision intelligence from planner corrections, decision reasons, and observed outcomes.

### Plan
Scale only after the product proves measurable planner productivity, reliability, paid demand, provider portability, controlled AI economics, and a learning loop that improves with continued use.

### Strategic Principle
> **The model is not the moat. ShelfSense's advantage must come from the CPG workflow context and decision feedback surrounding the model.**

---

## Strategy at a Glance

| Component | Module | Status | Key Artifact |
|-----------|--------|--------|-------------|
| **The Bet** | M1 | [x] | `01-the-bet/` |
| **The Moat** | M2 | [x] | `02-the-moat/` |
| **The Margin** | M3 | [x] | `03-the-margin/` |
| **The Contract** | M4 | [x] | `04-the-contract/` |
| **The Guardrails** | M5 | [x] | `05-the-guardrails/` |
| **The Pitch** | M6 | [x] | `06-the-pitch/` |

---

## The Bet (M1)

**What we're building, for whom, and why now.**

- **Product:** ShelfSense — B2B Demand & Promotion Planning Platform
- **AI Value Archetype:** Copilot
- **Target User:** CPG Demand Planner
- **Initial AI Wedge:** High-impact forecast exception triage, grounded driver explanation, and suggested next investigation step
- **Vulnerability Scores:** Contextual Moat **4/5** · Data Advantage **3/5** · Platform Exposure **3/5**
- **Top Risk:** ShelfSense has valuable customer context but has not yet converted planner corrections and outcomes into a proven compounding data advantage
- **Confidence:** **M — Medium**
- **Pilot North Star:** **High-value forecast exceptions resolved per planner-hour**
- **Prototype:** https://shelfsense-ai-copilo-udma.bolt.host
- **Kill Criteria:** Pivot or stop if the pilot fails to deliver at least 15% improvement in planner investigation time, ≥80% precision on priority flags, reliable grounded outputs, and willingness to pay from at least 2 of 3 design partners

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this becomes harder to replace with continued use.**

- **Data Flywheel Score:** **10/20**
- **Strongest Loop:** Domain Context — **4/5**
- **Weakest Loop:** Network — **1/5**
- **Near-Term Moat:** Customer-specific decision intelligence created from CPG workflow context + structured planner corrections + decision reasons + observed outcomes
- **Competitive Position:** Strong workflow context, moderate proprietary data advantage, and meaningful exposure to larger enterprise platforms
- **Primary Encroachment Threat:** **SAP / SAP IBP**
- **Encroachment Defense:** Build a deeper decision lineage that learns what each planning team changed, why they changed it, and what happened afterward rather than competing feature-for-feature with platform AI
- **Cross-Customer Network Effect:** Not assumed as part of the core strategy; treated as optional future upside subject to customer consent and contractual permission
- **Vendor Portability:** **Partial — must be proven before production launch**
- **Kill-Switch Requirement:** No production dependency on a single model provider without an approved and tested fallback path

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this create profitable customer value rather than expensive AI usage?**

- **Normalized Revenue:** **$2,500 per AI-enabled planner/month**
- **Traditional SaaS Gross Margin:** **81.0%**
- **Fully Loaded AI COGS — Baseline:** **$35/user/month**
- **Fully Loaded AI COGS — Optimized Target:** **$21/user/month**
- **Gross Margin — AI Baseline:** **~79.6%**
- **Gross Margin — AI Optimized:** **~80.2%**, before incremental AI revenue
- **Pricing Model:** **Hybrid — enterprise base subscription + AI add-on + included usage allowance/overage**
- **Pricing Principle:** Price against demonstrated workflow value, not token cost
- **Cascading Strategy:** Deterministic rules and small/mid models handle routine workloads; frontier models are reserved for ambiguous, conflicting-signal, or high-impact cases
- **Target Model Mix:** Approximately **90% lower-cost processing / 10% frontier escalation**
- **Cost Optimization Goal:** **40% reduction in fully loaded AI COGS without reducing reliability**
- **Economic Break-Even:** AI add-on revenue must exceed approximately **$35/user/month at baseline** or **$21/user/month after optimization**
- **Commercial Gate:** At least **2 of 3 design partners** demonstrate paid continuation or equivalent willingness to pay before broad commercialization
- **AI Add-On Margin Goal:** ≥70% incremental gross margin at steady state

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users should trust a probabilistic system influencing consequential planning decisions.**

- **Golden Dataset:** Minimum **100+ labeled cases before external pilot**, beginning from a 5-case seed set
- **Seed Edge / Adversarial Cases:** 4
- **Accuracy Target:** ≥90% case-level correctness and ≥85% precision on high-priority exception flags
- **Material Hallucination Target:** **0% unsupported material numeric claims**
- **Non-Material Hallucination Target:** <1%
- **Latency Target:** p95 <8 seconds for standard explanation flows
- **Confidence UX:** Calibrated tiered confidence based on data quality, evaluated-case similarity, signal agreement, historical performance, and decision risk — not model self-reported confidence
- **High Confidence:** Show insight + evidence + suggested action
- **Medium Confidence:** Highlight uncertainty and require explicit planner review
- **Low Confidence:** Abstain from directional recommendation
- **HITL Architecture:** ShelfSense remains advisory; consequential forecast changes require human approval
- **Core Failure Mode:** Plausible but unsupported causal explanations
- **Failure Defense:** Separate observed evidence from inferred explanation, surface confounders, and abstain when evidence is insufficient

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales — and what should compound.**

- **Correction Loop:** Active — planner decisions + reasons + actual outcomes feed future improvement
- **Preference Loop:** Broken — behavior is observed but not yet persisted as structured personalization
- **Network Learning Loop:** Missing — cross-customer learning is not assumed without explicit permission
- **Compounding Priority:** Build customer-level learning first
- **Decision Lineage:**  
  `Sales → Promotion → Inventory → Retailer Input → Forecast → AI Flag → Planner Decision + Reason → Actual Outcome`
- **Governance Posture:** Human-in-the-loop, tenant-isolated, least-privilege, auditable, and reversible
- **Autonomy Boundary:** AI may rank, explain, and suggest; it may not autonomously execute material forecast, inventory, production, pricing, or commercial decisions in v1
- **Escalation Triggers:** Low confidence, stale/missing data, conflicting signals, high financial impact, unevaluated scenarios, permission conflicts, or untested model changes
- **Agent Architecture:** Constrained Copilot components rather than autonomous multi-agent execution
- **Shadow AI Status:** **Discovery required — 30-day audit before claiming tool count or hidden spend**
- **Kill Switch:** Generative AI can be disabled while preserving ShelfSense's core SaaS planning workflow
- **Regulatory Exposure:** No definitive classification assumed; legal review required before EU deployment or expansion of autonomy

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How ShelfSense earns the right to fund, scale, and expand the AI strategy.**

### Horizon 1 — Now (0-3 months)
Prove the narrow Copilot wedge with three design partners.

**Key gates:**
- ≥15% reduction in planner investigation time
- ≥80% precision on high-priority exception flags
- ≥2 of 3 partners demonstrate willingness to pay/continue
- 100+ case reliability dataset passes agreed thresholds
- structured planner feedback is captured
- backup model/provider passes regression testing

### Horizon 2 — Next (3-9 months)
Commercialize only after Horizon 1 succeeds.

**Focus:**
- customer-specific preference learning
- closed-loop decision intelligence
- optimized model cascading
- paid AI packaging
- fully loaded AI COGS ≤$21/user/month

### Horizon 3 — Bet (9-18 months)
Earn the right to expand from exception Copilot toward a broader demand-decision layer.

**Focus:**
- measurable decision-outcome improvement
- compounding correction and preference loops
- broader workflow coverage
- optional consent-based cross-customer benchmarking

---

## Board Narrative

> **ShelfSense should use AI first to resolve high-impact forecast exceptions faster, then earn the right to become a broader demand-decision layer by proving customer value, reliability, willingness to pay, and compounding customer-specific learning.**

### Why Now
Demand planners spend too much time investigating fragmented signals, customers increasingly expect AI-enabled planning, and large platforms can quickly commoditize generic AI features.

### What's Defensible
Not the foundation model. The defensible asset is ShelfSense's **customer-specific CPG decision graph**: workflow context, planner corrections, decision reasons, preferences, and observed outcomes.

### The Economics
AI cost is manageable relative to ShelfSense's enterprise revenue base, but affordable inference alone is not a reason to scale. Commercial value and willingness to pay remain mandatory gates.

### Primary Competitive Threat
SAP does not need to build a better AI model than ShelfSense. It can win with a "good enough" capability through native data access, bundling, procurement simplicity, and existing enterprise distribution.

### ShelfSense's Response
Go deeper into the decision workflow rather than broader into generic AI functionality.

---

## Investment Ask

Approve the existing **$3M / 12-month validation envelope as stage-gated capital rather than an upfront scale commitment**.

| Stage | Investment | Release Condition |
|------|-----------:|------------------|
| **0-3 months** | **$750K** | Authorized for design-partner pilot, evaluation, feedback capture, routing, and governance |
| **3-9 months** | **$1.25M** | Released only if customer-value, reliability, feedback, and commercial gates pass |
| **9-12+ months** | **$1.0M** | Released only if paid adoption, portability, learning-loop, and economic gates pass |

**Autonomous planning is not approved in this phase.**

---

## Strategy Evolution

### Module 1 Baseline

**Vision:** ShelfSense becomes the trusted decision layer for CPG demand planning.

**Strategy:** We will use AI selectively in high-value planning decisions where our data, workflow integration, and human oversight can create a defensible advantage.

**Plan:** We will validate those use cases against customer value, reliability, trust, and unit economics before scaling.

### Refined Strategy

**Vision:** ShelfSense becomes the trusted decision layer for CPG demand planning.

**Strategy:** Start with a human-in-the-loop Copilot for high-impact forecast exception triage and evidence-grounded driver explanation, then build customer-specific decision intelligence from planner corrections and observed outcomes.

**Plan:** Scale only after the pilot proves measurable planner productivity, reliability, paid demand, provider portability, controlled fully loaded AI COGS, and a learning loop that improves with continued use.

---

## Repository Structure

```text
Shelf-Sense_AI-Product-Strategy/
│
├── README.md
├── ShelfSense_Product_Overview_Executive_Summary.md
│
├── 01-the-bet/
│   ├── diagnostic.md
│   └── prototype.md
│
├── 02-the-moat/
│   ├── data-flywheel.md
│   └── kill-switch.md
│
├── 03-the-margin/
│   └── cost-curve.md
│
├── 04-the-contract/
│   └── golden-dataset.md
│
├── 05-the-guardrails/
│   └── compounding-system.md
│
└── 06-the-pitch/
    └── roadmap.md
