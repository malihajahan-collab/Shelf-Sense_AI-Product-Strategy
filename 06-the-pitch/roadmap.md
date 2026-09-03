# Three-Horizon Roadmap & Board Pitch

## Roadmap

### Horizon 1 — Now (0-3 months)
*Quick wins. Ship with existing capabilities.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Pilot the ShelfSense AI Copilot for forecast exception flagging, driver explanation, and recommended planner actions with human approval | ≥90% golden-dataset accuracy, <2% hallucination rate, 100% human approval for consequential forecast changes | H |
| Capture structured planner feedback — Accept / Modify / Reject + reason — and connect it to actual outcomes | ≥80% of reviewed AI recommendations generate usable correction feedback | H |

### Horizon 2 — Next (3-9 months)
*Bets. Requires new capabilities or integrations.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Build planner/team preference learning and confidence-based model routing | ≥20% reduction in planner investigation time while maintaining reliability thresholds | M |
| Pilot permissioned, privacy-safe cross-customer learning using de-identified outcome patterns and benchmarks | Cross-customer learning pilot with at least 3 customers without pooling raw proprietary data | M |

### Horizon 3 — Bet (9-18 months)
*Moonshots. High uncertainty, high potential.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Evolve ShelfSense from forecast-support software into a trusted CPG demand-decision layer that learns from planner decisions and business outcomes | Demonstrated improvement in decision efficiency and forecast outcomes across multiple enterprise customers, with a measurable compounding data advantage | L |

## Board Pitch

**Thesis (1 sentence):**

ShelfSense should use AI to become the trusted decision layer for CPG demand planning by combining our workflow context with proprietary planner feedback and outcome data—not by competing on the underlying AI model.

**The case:**
1. **Why now:** Customers are asking for AI-enabled planning, competitive pressure from platforms such as SAP is increasing, and ShelfSense needs a stronger growth and differentiation engine as traditional planning capabilities become easier to replicate.
2. **What's defensible:** Our strongest advantage is the combination of embedded CPG workflow context, planner corrections, forecast-versus-actual outcomes, and the opportunity to create compounding feedback loops that generic AI platforms do not automatically possess.
3. **The economics:** At the Module 3 baseline of $2,500 normalized revenue per AI-enabled planner/month, AI adds approximately $18 in monthly COGS and can be reduced toward $10.80 through cascading and model routing. This preserves approximately 80% gross margins before incremental AI monetization and supports a hybrid base + usage pricing model.

**The risks:**
1. **Trust / failure modes:** Incorrect but plausible recommendations could influence high-value inventory and promotion decisions; confidence UX, abstention, golden-dataset evaluation, and human approval remain mandatory.
2. **Scale / governance:** Customer data cannot simply be pooled, model/vendor dependency must remain portable, and AI usage requires auditability, privacy controls, drift monitoring, and clear autonomy boundaries.
3. **Competitive:** SAP can attack ShelfSense by embedding comparable AI decision support directly into ERP and IBP workflows; ShelfSense must strengthen its data flywheel faster than competitors can copy the visible AI features.

**The ask:**

Approve the staged AI initiative within the existing **$3M / 12-month validation envelope**, with continued investment gated by customer value, reliability, data-flywheel strength, and unit economics. Do not approve autonomous planning at this stage; approve a human-in-the-loop Copilot and the infrastructure required to validate whether it can become a defensible decision platform.

## M1 Baseline vs. Now
*Your 3-sentence AI strategy from Module 1 vs. what you'd say now:*

**M1 baseline:**

**Vision:** ShelfSense becomes the trusted decision layer for CPG demand planning.  

**Strategy:** We will use AI selectively in high-value planning decisions where our data, workflow integration, and human oversight can create a defensible advantage.  

**Plan:** We will validate those use cases against customer value, reliability, trust, and unit economics before scaling.

**Now:**

ShelfSense will build a human-in-the-loop AI Copilot that helps CPG demand planners identify, understand, and act on the forecasts that matter most. Our moat will not be the model; it will be the compounding system created from CPG workflow context, structured planner corrections, preferences, and observed business outcomes. We will scale toward a trusted demand-decision platform only when the product proves reliable, economically sustainable, portable across AI vendors, and measurably better with continued use.
