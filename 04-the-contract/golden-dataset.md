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

**Adversarial / edge rows included:** 4  
**Coverage gaps to close before pilot:** New launches, assortment/distribution changes, promotion cannibalization, competitor actions, seasonality shifts, supply disruptions, external shocks, sparse data, delayed feeds, duplicate records, extreme outliers, and category-specific behavior.

---

## Confidence UX Design

**Approach:** tiered, **calibrated system confidence** + visible evidence + human-in-loop trigger.

Confidence must not be the LLM's self-reported certainty. It should combine:
- data completeness and freshness;
- similarity to evaluated cases;
- agreement/conflict among planning signals;
- historical performance for the scenario;
- business impact/risk level.

**High confidence (>90% calibrated):** Show the finding, evidence, and suggested next investigation/action. Planner remains free to accept, modify, or reject.  
**Medium confidence (70-90% calibrated):** Highlight uncertainty and conflicting evidence; require explicit planner review.  
**Low confidence (<70% calibrated):** Abstain from a directional recommendation and explain what evidence is missing or conflicting.

**User control surface:**  
Every insight shows source evidence, data freshness, confidence tier, rationale, and controls to **Accept / Modify / Reject / Escalate**. The user's reason is captured as structured feedback.

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
