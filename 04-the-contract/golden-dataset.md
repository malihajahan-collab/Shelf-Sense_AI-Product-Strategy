# Golden Dataset & Reliability Contract

## Golden Dataset Spec

| # | Input | Expected Output | Edge Case? | Judge Type |
|---|-------|----------------|-----------|-----------|
| 1 | Forecast is 18% above baseline during a planned promotion with strong historical uplift | Flag the forecast for review, identify the promotion as the primary driver, cite supporting signals, and recommend validating the uplift assumption | N | LLM |
| 2 | Recorded sales decline while inventory shows repeated stockouts | Do not interpret lower sales as true demand decline; identify stock availability as a confounding factor and recommend planner review | Y | LLM |
| 3 | New SKU with limited sales history and no comparable promotion history | Return low confidence, explain insufficient evidence, avoid a strong recommendation, and trigger human review | Y | rule |
| 4 | Retailer forecast decreases while recent sales increase and a promotion is scheduled | Surface the conflicting signals, provide a medium-confidence explanation, and require planner confirmation before changing the forecast | Y | LLM |
| 5 | Required retailer or inventory data is missing or stale | Do not generate a planning recommendation; identify the missing data and request refresh or manual review | Y | rule |

**Adversarial rows included:** 3 — stockout-distorted demand, conflicting signals, and missing/stale data  
**Coverage gaps identified by partner:** New product launches, sudden retailer assortment changes, competitor promotions, and external shocks where ShelfSense has limited historical context

## Confidence UX Design

**Approach:** tiered confidence + visible uncertainty + human-in-loop trigger

**High confidence (>90%):** Show recommendation, key evidence, expected impact, and allow the planner to accept, modify, or reject it.  
**Medium confidence (70-90%):** Show recommendation with conflicting or incomplete signals clearly highlighted and require planner confirmation before action.  
**Low confidence (<70%):** Do not recommend an automatic forecast change. Explain why confidence is low and escalate to planner review.

**User control surface:** Every recommendation shows confidence level, supporting signals, data freshness, rationale, and controls to **Accept / Modify / Reject / Escalate**. Planner corrections and reasons are captured as feedback for the ShelfSense correction loop.

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | ≥90% on approved recommendation/evaluation cases | Weekly golden-dataset evaluation plus sampled production outcomes | <85% |
| Hallucination rate | <2% unsupported factual claims | Grounding checks against source planning data and human-reviewed samples | >3% |
| Latency (p95) | <5 seconds for standard analysis | Production request telemetry | >7 seconds |
| Drift velocity | <5 percentage-point decline in eval performance over 30 days | Compare rolling production/eval performance with approved baseline | >5-point decline |

> These are initial case-study reliability targets and should be validated during pilot testing before production commitments.

## HITL Architecture
<!-- When does a human step in? What's the escalation path? -->

A human planner remains accountable for consequential forecast changes.

Human review is triggered when:
- confidence is below 70%;
- important source data is missing or stale;
- signals materially conflict;
- the recommendation affects a high-financial-impact SKU, retailer, or promotion;
- the AI proposes a change outside configured planning thresholds.

**Escalation path:**  
AI flags issue → planner reviews evidence and recommendation → planner accepts, modifies, or rejects → reason is captured → actual outcome is later compared with the decision → feedback enters the correction loop.

ShelfSense does not autonomously execute high-impact forecast changes during the initial AI Copilot phase.

## Red-Team Findings

A plausible-looking recommendation can still be wrong when the underlying sales signal is distorted by operational constraints. For example, the AI could interpret declining sales as declining consumer demand when the real cause is repeated stockouts.

**Mitigation:** Before generating a demand recommendation, ShelfSense must validate critical contextual signals such as inventory availability, promotion status, data freshness, and retailer inputs. When those signals are incomplete or contradictory, the system should lower confidence or abstain rather than produce a confident recommendation.
