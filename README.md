# ShelfSense — B2B Demand & Promotion Planning Platform

> We are building an AI Copilot for CPG demand planners that reduces time spent investigating high-impact forecast exceptions while keeping the planner in control of consequential decisions.

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

**What we're building, for whom, why now.**

- **Product:** ShelfSense — B2B Demand & Promotion Planning Platform
- **AI Value Archetype:** Copilot
- **Vulnerability Scores:** _(add: Moat _/5 · Data _/5 · Platform _/5)_
- **Top Risk:** **Data Advantage.** ShelfSense has strong customer context but has not yet converted planner corrections and business outcomes into a proprietary learning loop that clearly improves the product with continued use.
- **Confidence:** M
- **Prototype:** https://shelfsense-ai-copilo-udma.bolt.host
- **Kill Criteria:** Kill or materially pivot the bet if, after two complete planning cycles with design partners:

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:**
- **Weakest Loop:** Network Loop - 1/5
- **Top Encroachment Threat:** SAP / SAP IBP
- **Encroachment Defense:** Do not depend on a network effect that does not yet exist. First build strong customer-level correction, preference, and outcome loops.…
- **Vendor Portability:** Partial — design intent exists, but portability is not yet proven.

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this make money or bleed it?**

- **Gross Margin (current):**
- **Gross Margin (AI-adjusted):**
- **Pricing Model:** **Hybrid — base subscription + AI add-on + usage allowance/overage**
- **Pricing Today → Tomorrow:** ShelfSense is sold as an enterprise SaaS subscription. For Module 3 modeling, revenue is normalized to **$2,500 per AI-enabled planner per month**. This is a unit-economics allocation, not a literal seat price. → Enterprise AI add-on with an included monthly analysis allowance, plus predictable overage for materially higher usage.
- **Total AI COGS / unit:** $35.00
- **Cascading Strategy:** Triage: Small model + deterministic rules for routine classification and prioritization; frontier: High-reasoning model for ambiguous, conflicting-signal, or high-financial-impact cases; ratio Baseline target 80% lower-cost / 20% frontier; optimized target 90% lower-cost / 10% frontier
- **Net Margin Shift:** The AI layer reduces total product gross margin by ~1.4 points at baseline and ~0.8 points after optimization before any AI revenue.…
- **Break-even at:**

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:** ≥90% case-level correctness on the approved 100+ case eval set; ≥85% precision on high-priority exception flags
- **Golden Dataset:** 5 rows, __ adversarial
- **Confidence UX:** tiered, **calibrated system confidence** + visible evidence + human-in-loop trigger.
- **HITL Architecture:** ShelfSense v1 is advisory. It does not autonomously change material forecasts.
- **Failure Mode Coverage:** **Failure mode:** The AI may produce a plausible causal story when the data only supports correlation. A sales decline could be caused by stockouts, distribution loss, retailer execution, or competitor activity rather than true demand decli…

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales, and what compounds.**

- **Compounding System:** | Loop | Input | Output | Compounds? | Status | |------|-------|--------|-----------|--------| | **Correction Loop** | Planner accepts/modifies/rejects an AI insight + reason + actual outcome | Better customer-specific e…
- **Governance Posture:** AI-assisted forecast exception prioritization, grounded driver explanation, and suggested investigation/planning actions.
- **Autonomy Boundaries:** - AI may rank, explain, and recommend.
- **Escalation Triggers:** - calibrated confidence <70%;
- **Audit Cadence:** - weekly pilot quality review;
- **Shadow AI Audit (user-side):** __ workarounds found · TBD build candidates · adjacent spend TBD — validate through procurement/expense review
- **Agent Boundaries:** ShelfSense v1 remains a **Copilot**, not an autonomous multi-agent system.
- **Regulatory Exposure:** No definitive regulatory classification is assumed in this fictional case. Before EU deployment or any expansion in autonomy, legal counsel must confirm applicable classification, transparency, data-governance, documenta…

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):** Run a 3-design-partner Copilot pilot focused on high-impact forecast exception triage, grounded driver explanation, and next investigation step · Build the minimum reliability + learning foundation: 100+ case golden dataset, structured Accept/Modify/Reject reasons, outcome linkage, provider fallback, and telemetry
- **Horizon 2 (Next):** Build customer-specific preference learning and closed-loop decision intelligence · Launch paid AI packaging with included usage allowance + overage and optimized cascading
- **Horizon 3 (Bet):** Expand from exception Copilot toward a broader trusted demand-decision layer; optionally pilot consent-based cross-customer benchmarking
- **Board Narrative:** ShelfSense should use AI first to resolve high-impact forecast exceptions faster, then earn the right to become a broader demand-decision layer by proving customer value, reliability, willingness to pay, and compounding customer-specific learning.
- **Ask:** Approve the existing **$3M / 12-month validation envelope as stage-gated capital, not an upfront scale commitment**:
- **Key Strategic Change:**

→ Details: [`06-the-pitch/`](06-the-pitch/)
