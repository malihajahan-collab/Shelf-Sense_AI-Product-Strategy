# Three-Horizon Roadmap & Board Pitch

## Roadmap

### Horizon 1 — Now (0-3 months)
*Prove the wedge before scaling the platform.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Run a 3-design-partner Copilot pilot focused on high-impact forecast exception triage, grounded driver explanation, and next investigation step | ≥15% reduction in investigation time; ≥80% precision on high-priority flags; ≥2 of 3 partners indicate willingness to pay/continue | M |
| Build the minimum reliability + learning foundation: 100+ case golden dataset, structured Accept/Modify/Reject reasons, outcome linkage, provider fallback, and telemetry | Reliability contract passes; ≥80% of reviewed insights generate usable structured feedback; backup provider passes regression gate | M |

### Horizon 2 — Next (3-9 months)
*Commercialize only after Horizon 1 gates are met.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Build customer-specific preference learning and closed-loop decision intelligence | ≥20% investigation-time reduction vs. pre-AI baseline while maintaining reliability thresholds | M |
| Launch paid AI packaging with included usage allowance + overage and optimized cascading | ≥2 paid enterprise continuations; fully loaded AI COGS ≤$21/user/month; AI add-on designed for ≥70% incremental gross margin | M |

### Horizon 3 — Bet (9-18 months)
*Expand the moat only where evidence supports it.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Expand from exception Copilot toward a broader trusted demand-decision layer; optionally pilot consent-based cross-customer benchmarking | Demonstrated improvement in decision outcomes across multiple customers; preference/correction loops measurably improve quality over time; legal/contract approval for any shared benchmark layer | L |

---

## Investment Gates

### Gate 1 — 3 months
Proceed only if customer value, reliability, feedback capture, and commercial interest pass Horizon 1 thresholds.

### Gate 2 — 9 months
Proceed to broader scale only if:
- customers pay;
- fully loaded AI COGS is controlled;
- provider portability is tested;
- customer-level learning improves performance; and
- no unresolved material governance issue exists.

---

## Board Pitch

**Thesis (1 sentence):**
ShelfSense should earn the right to become the trusted decision layer for CPG demand planning by first proving that it can help planners resolve high-value forecast exceptions faster, reliably, and at economics customers will pay for.

**The case:**
1. Why now: The external market-timing case is not yet sufficiently evidenced in the strategy, so we should not manufacture an “AI is accelerating” argument. The credible timing case is competitive and internal: SAP / SAP IBP can absorb generic AI assistance into the platform layer, so ShelfSense has a limited window to prove a differentiated workflow around customer-specific corrections, decision outcomes, and planner trust before that functionality becomes table stakes. The next three months tell us whether that wedge is real.
2. What's defensible: The moat is the **customer-level correction, preference, and outcome loop** identified in M2—not the model itself. Today that moat is incomplete: the Data Flywheel scores 10/20 and the Network Loop only 1/5. Horizon 1 therefore funds the missing asset directly: structured Accept/Modify/Reject reasons, outcome linkage, and customer-specific feedback. If repeated use does not measurably improve recommendation quality, we do not have the moat we are claiming.
3. The economics: **AI COGS can be brought to approximately $21 per user per month**, versus a modeled $2,500 per AI-enabled planner per month revenue allocation. At baseline, AI reduces total product gross margin by approximately 1.4 points; after workload optimization, that falls to approximately 0.8 points before any AI revenue. The commercial model is a base subscription plus AI add-on with included usage and predictable overage. Horizon 2 only proceeds if fully loaded AI COGS stays at or below $21/user/month and the AI add-on supports at least 70% incremental gross margin.

**The risks:**
1. Trust / failure modes: The highest-risk failure is ShelfSense presenting a confident causal explanation that the underlying data does not support—for example, attributing a sales decline to demand when the real cause is stockout, lost distribution, retailer execution, or competitive activity. The contract is explicit: ≥90% case-level correctness on the approved 100+ case evaluation set, ≥85% precision on high-priority exception flags, visible supporting evidence, calibrated confidence, and mandatory human review. Below 70% confidence, the system escalates rather than pretending certainty. ShelfSense v1 recommends; it does not autonomously change material forecasts.
2. Scale / governance: At 10x usage, the risks are cost escalation, declining quality across more heterogeneous customer data, weak auditability, and pressure to automate beyond what the evidence supports. The control system is therefore built before scale: model cascading, provider fallback, telemetry, weekly quality review during pilot, explicit autonomy boundaries, and structured feedback linked to outcomes. We do not expand autonomy simply because usage grows.
3. Competitive: The kill scenario is straightforward: if SAP / SAP IBP can deliver equivalent exception prioritization and explanation while ShelfSense fails to demonstrate a customer-specific learning advantage, we should not fund a broader AI platform. After two complete planning cycles, if the pilot does not show meaningful investigation-time reduction, acceptable reliability, evidence of willingness to pay, and measurable improvement from the correction/outcome loop, we kill or materially pivot the bet.

**The ask:**
Approve **$750K and a 4-person team for 3 months** to run the 3-design-partner pilot and prove four things: **customer value, reliability, willingness to pay, and defensibility**. Further funding from the $3M envelope is released only if Gate 1 is met. The trade-off: this funding should delay an equivalent lower-priority H2/H3 initiative.

---

## M1 Baseline vs. Now

**M1 baseline:**

**Vision:** ShelfSense becomes the trusted decision layer for CPG demand planning.  

**Strategy:** We will use AI selectively in high-value planning decisions where our data, workflow integration, and human oversight can create a defensible advantage.  

**Plan:** We will validate those use cases against customer value, reliability, trust, and unit economics before scaling.

**Now:**

**Vision:** ShelfSense becomes the trusted decision layer for CPG demand planning.  

**Strategy:** Start with a human-in-the-loop Copilot for high-impact forecast exception triage and evidence-grounded driver explanation, then build customer-specific decision intelligence from planner corrections and observed outcomes.  

**Plan:** Scale only after the pilot proves measurable planner productivity, reliability, paid demand, provider portability, controlled fully loaded AI COGS, and a learning loop that improves with continued use.
