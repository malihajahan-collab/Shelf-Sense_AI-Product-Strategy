# Three-Horizon Roadmap & Board Pitch

# ShelfSense AI Initiative Roadmap

## Horizon 1 — Ship (0-4 weeks)

| Initiative | Strategy Component | Why it ships now | Confidence |
|---|---|---|---|
| **Build structured planner feedback capture** | Moat | The correction loop cannot begin without capturing Accept / Modify / Reject + reason from the first pilot interaction. Every uncaptured decision is lost proprietary learning. | H |
| **Create 100+ case golden evaluation dataset** | Contract | The current 5-row seed set is insufficient to judge reliability. The expanded dataset is required for model approval, pilot testing, and provider comparison. | H |
| **Build human-in-the-loop approval workflow** | Contract | ShelfSense v1 is explicitly advisory, so planner approval for consequential recommendations must exist before the Copilot enters a real planning workflow. | H |
| **Implement AI governance and kill switch** | Guardrails | Tenant isolation, escalation rules, auditability, and the ability to disable AI without disrupting core ShelfSense are minimum release controls. | H |
| **Run Shadow AI discovery audit** | Guardrails | This low-cost discovery activity establishes evidence on unapproved AI use, customer-data exposure, tool ownership, and hidden spend before broader governance decisions are made. | H |

---

## Horizon 2 — Validate (1-3 months)

| Initiative | Strategy Component | Hypothesis | Kill Criteria | Confidence |
|---|---|---|---|---|
| **Implement calibrated confidence and abstention** | Contract | Confidence derived from data freshness, completeness, signal conflict, scenario similarity, and historical performance will reliably distinguish actionable cases from cases where ShelfSense should abstain. | **If higher-confidence tiers do not demonstrate meaningfully higher observed accuracy by week 6, stop automated confidence tiering and revert to conservative rule-based escalation.** | M |
| **Implement multi-model routing and provider fallback** | Moat | ShelfSense can preserve reliability while moving routine workloads across lower-cost or alternate models, reducing strategic dependence on a single provider. | **If the backup or routed model cannot meet ShelfSense's approved reliability threshold on routine cases by week 6, stop expanding routed traffic and retain the proven provider for the pilot.** | M |
| **Optimize fully loaded AI COGS** | Margin | Cascading, caching, retrieval optimization, infrastructure efficiency, and risk-based QA can move fully loaded AI COGS from $35 toward $21/user/month without compromising reliability. | **If we cannot demonstrate at least a 20% fully loaded cost reduction with no material reliability decline by week 6, stop prioritizing cost optimization and redirect resources toward proving customer value.** | M |
| **Validate AI pricing and willingness to pay** | Margin | Customers experiencing measurable planning value will pay for a predictable enterprise AI add-on rather than expect the capability to be included at no additional charge. | **If fewer than 2 of 3 design partners demonstrate credible willingness to pay or enter a paid-continuation discussion by week 6, stop the current packaging proposal and revisit the value proposition.** | M |
| **Create customer-specific decision lineage** | Moat | Connecting planning context → AI insight → planner decision → reason → actual outcome will create proprietary customer-level intelligence that strengthens future prioritization and recommendations. | **If fewer than 70% of pilot decisions can be reliably linked to subsequent outcomes by week 6, stop expanding the learning layer and fix instrumentation and data linkage first.** | M |
| **Measure pilot business value** | Bet | The exception-focused Copilot will materially reduce the time planners spend investigating high-impact forecasts while preserving planner trust and decision quality. | **If we do not see at least a 15% improvement in investigation efficiency or a strong trajectory toward it by week 6, stop expanding the Copilot scope and revisit the initial wedge.** | M |
| **Prepare Gate 1 executive review** | Bet | Combining customer value, reliability, commercial demand, economics, portability, and feedback-loop evidence will provide leadership with enough evidence for a clear go / pivot / stop decision. | **If the Gate 1 evidence package cannot demonstrate customer value, acceptable reliability, and credible commercial demand by the end of the pilot, do not release the next funding tranche.** | M |

---

## Horizon 3 — Explore (3-6 months)

| Initiative | Strategy Component | What must be true first | Confidence |
|---|---|---|---|
| **Build customer-specific preference learning** | Moat | ShelfSense first needs sufficient structured planner corrections, reliable outcome linkage, repeated usage, and evidence that planner/team behavior contains stable patterns before investing in personalization. | L |

---
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

1. **Why now:** SAP / SAP IBP can make generic AI assistance table stakes quickly. ShelfSense has a narrow window to prove a differentiated advantage through customer-specific corrections, outcomes, and planner trust.

2. **What's defensible:** The moat is the **customer-level correction, preference, and outcome loop**—not the model. Today it is still unproven: Data Flywheel 10/20, Network Loop 1/5. Horizon 1 tests whether repeated use measurably improves quality and creates a real data advantage.

3. **The economics:** AI COGS can reach **~$21/user/month**, with gross-margin impact improving from ~1.4 points to ~0.8 points after optimization. The paid AI add-on only scales if it maintains **≥70% incremental gross margin**.

**The risks:**

1. **Trust / failure modes:** The key risk is a confident but wrong causal explanation. We mitigate this with ≥90% case-level correctness, ≥85% precision on high-priority flags, visible evidence, calibrated confidence, and mandatory human review. Below 70% confidence, the system escalates. ShelfSense v1 recommends; it does not change forecasts autonomously.

2. **Scale / governance:** At 10x usage, cost, quality, and auditability become the pressure points. We control for this through model cascading, provider fallback, telemetry, weekly quality reviews, explicit autonomy limits, and outcome-linked feedback before scaling.

3. **Competitive:** If SAP / SAP IBP can match the core workflow and ShelfSense does not show a measurable customer-specific learning advantage, we stop. After two planning cycles, failure to prove time savings, reliability, willingness to pay, and a strengthening correction loop triggers a kill or material pivot.


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
