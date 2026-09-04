# Golden Dataset & Reliability Contract

## Golden Dataset Spec

> The five rows below are the **seed set**, not a production-ready evaluation dataset. Before external pilot launch, expand to at least **100 labeled cases** stratified across normal, edge, adversarial, category, retailer, promotion, and data-quality scenarios.

| # | Input | Expected Output | Edge Case? | Judge Type |
|---|-------|----------------|-----------|-----------|
| 1 | Forecast is 18% above baseline during a planned promotion with strong historical uplift | Flag for review, identify promotion as a supported driver, cite evidence, and suggest validating the uplift assumption | N | LLM |
| 2 | Recorded sales decline while inventory shows repeated stockouts | Do not infer demand decline; identify availability as a confounder and recommend planner review | Y | LLM |
| 3 | New SKU with limited history and no comparable promotion history | Abstain from a strong recommendation; label insufficient evidence and trigger review | Y | rule |
| 4 | Retailer forecast decreases while recent sales increase and a promotion is scheduled | Surface conflicting signals, avoid a definitive causal claim, and require planner confirmation | Y | LLM |
| 5 | Required retailer or inventory data is missing or stale | Do not generate a planning recommendation; identify missing/stale inputs and request refresh or review | Y | rule |

Dataset health
- Total: 5
- Edge cases: 4 (80.0%)
- Judge mix: 40% rule / 60% LLM / 0% both

**Adversarial / edge rows included:** 4  
**Coverage gaps to close before pilot:** New launches, assortment/distribution changes, promotion cannibalization, competitor actions, seasonality shifts, supply disruptions, external shocks, sparse data, delayed feeds, duplicate records, extreme outliers, and category-specific behavior.

---

## Confidence UX Design

**Approach:** Tiered, calibrated confidence with visible supporting evidence and a human-in-the-loop trigger; ShelfSense shows uncertainty explicitly and abstains when the available planning evidence is insufficient.

**Confident (>90%):** Show the forecast exception, supporting evidence, key demand drivers, data freshness, and suggested next investigation/action. The planner can Accept, Modify, Reject, or Escalate. ShelfSense may recommend but does not automatically change the forecast.

**Uncertain (50-90%):** At 70–90% confidence, show the recommendation with uncertainty and conflicting signals clearly highlighted and require explicit planner review. At 50–69%, do not give a directional recommendation; show the evidence gaps or conflicts and route the case for human review.

**Not confident (<50%):** Abstain from generating a planning recommendation. Show what evidence is missing, stale, or contradictory and escalate to the planner for manual investigation.

**User control surface:** 

Every AI insight shows confidence level, supporting demand drivers, source evidence, and data freshness. Planners can Accept, Modify, Reject, or Escalate the recommendation and select a structured reason such as wrong driver, missing context, incorrect priority, or insufficient evidence. Corrections are stored with the planning context and later linked to actual outcomes to improve ShelfSense's customer-specific correction and preference loops. Feedback does not automatically retrain the production model; it enters a governed evaluation/learning dataset first.

- Users see AI reasoning / drivers
- Users correct & override outputs
- Corrections feed back into the model / dataset
- Users adjust the confidence threshold _(not yet)_

---

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | ≥90% case-level correctness on the approved 100+ case eval set; ≥85% precision on high-priority exception flags | Pre-release eval + weekly sampled production review | <85% case correctness or <80% exception precision |
| Hallucination rate | **0% unsupported material numeric claims**; <1% non-material unsupported claims | Grounding checks + human-reviewed samples | Any repeated material unsupported claim or >1% non-material |
| Latency (p95) | <8 seconds for standard explanation flow | Production telemetry | >12 seconds sustained |
| Drift velocity | <5 percentage-point decline over rolling 30 days | Compare current eval/production performance with approved baseline | >5-point decline |

---

## HITL Architecture

ShelfSense v1 is advisory. It does not autonomously change material forecasts.

Human review is mandatory when:
- the system proposes any material forecast adjustment;
- confidence is below 70%;
- required data is missing or stale;
- signals conflict materially;
- the item is high financial impact;
- the case falls outside evaluated scenarios.

**Escalation path:**  
AI flags exception → planner reviews evidence → planner accepts/modifies/rejects → reason is captured → actual outcome is observed → result enters the correction loop.

---

## Release Gates

A model/version cannot move to broader pilot traffic unless:
1. the 100+ case golden dataset passes reliability thresholds;
2. high-impact edge cases pass separately;
3. no unresolved material grounding failure exists;
4. the backup model/provider has been regression-tested; and
5. confidence tiers are calibrated against observed performance.

---

## Red-Team Findings

**Failure mode:** The AI may produce a plausible causal story when the data only supports correlation. A sales decline could be caused by stockouts, distribution loss, retailer execution, or competitor activity rather than true demand decline.

**Mitigation:** Separate **observed evidence** from **inferred explanation** in the UX. Require the system to cite supporting signals, identify confounders, and abstain when the causal explanation is not sufficiently supported.
