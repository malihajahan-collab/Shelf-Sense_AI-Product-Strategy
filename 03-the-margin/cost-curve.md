# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | $9.60 | Frontier-model usage for ambiguous or high-impact planning cases |
| Inference (cascading/triage) | $8.40 | Small/mid models for flagging, prioritization, and standard explanations |
| Infrastructure / observability | $6.00 | Retrieval compute, tracing, monitoring, orchestration, and incremental AI runtime |
| Data / storage | $3.00 | Incremental embeddings/vector storage, feature retrieval, and AI telemetry |
| Human-in-the-loop / quality operations | $8.00 | Risk-based QA sampling, eval maintenance, and escalation support; excludes the customer's normal planner labor |
| **Total AI COGS** | **$35.00** | Synthetic fully-loaded case assumption for Module 3 |

## Cascading Strategy

**Triage model:** Small model + deterministic rules for routine classification and prioritization  
**Frontier model:** High-reasoning model for ambiguous, conflicting-signal, or high-financial-impact cases  
**Routing rule:** Use the cheapest system that meets the required quality and risk threshold. Deterministic logic handles deterministic work; small/mid models handle standard analysis; frontier inference is an exception path.  
**Expected cascade ratio:** Baseline target 80% lower-cost / 20% frontier; optimized target 90% lower-cost / 10% frontier

### Cost Optimization Target

Management target: **Reduce fully loaded AI COGS by 40% without compromising quality.**

- Baseline AI COGS: **$35/user/month**
- Target AI COGS: **$21/user/month**
- Reduction: **40%**

### How the 40% reduction is achieved

| Cost Lever | Baseline | Target | Strategy |
|-----------|---------:|-------:|----------|
| Frontier inference | $9.60 | $4.80 | Cut frontier volume through confidence/risk-based escalation |
| Triage inference | $8.40 | $6.00 | Smaller models, deterministic rules, caching, and batching |
| Infrastructure / observability | $6.00 | $4.20 | Cache repeated context and optimize orchestration |
| Data / storage | $3.00 | $2.00 | Retrieve only decision-relevant context; manage retention |
| Quality operations | $8.00 | $4.00 | Move from broad manual review to risk-based sampling after reliability is proven |
| **Total** | **$35.00** | **$21.00** | **40% reduction** |

Quality remains a hard gate: the optimized architecture is adopted only if it passes the same golden-dataset and production reliability thresholds.

---

## Pricing Model

**Current pricing:** ShelfSense is sold as an enterprise SaaS subscription. For Module 3 modeling, revenue is normalized to **$2,500 per AI-enabled planner per month**. This is a unit-economics allocation, not a literal seat price.

**Proposed AI pricing:** Enterprise AI add-on with an included monthly analysis allowance, plus predictable overage for materially higher usage.

**Model:** **Hybrid — base subscription + AI add-on + usage allowance/overage**

### Pricing principle

Do not price from token cost. Price from demonstrated workflow value while maintaining predictable enterprise spend.

**Commercial gate:** Before broad launch, at least 2 of 3 design partners should accept a paid continuation, paid pilot, or equivalent commercial commitment.

**Margin floor:** AI packaging should be designed to maintain at least **70% incremental gross margin on the AI add-on** after steady-state optimization.

---

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | Inference rises from $18 to $54; fully loaded AI COGS rises to ~$71/user/month. Overall gross margin falls to ~78.2% before AI revenue. | Shift traffic to backup models, tighten frontier escalation, cache repeated context, and temporarily disable non-essential generative flows. |
| Heaviest segment doubles | If the highest-volume 40% of inference doubles, fully loaded AI COGS rises to roughly $42.20/user/month; gross margin remains ~79.3% before AI revenue. | Enforce included usage allowances, caching, batching, and routing; price predictable overage for sustained heavy usage. |
| Primary model provider raises prices 50% | Fully loaded AI COGS rises from $35 to ~$39.80/user/month; gross margin is ~79.4% before AI revenue. | Trigger the kill-switch plan and route only quality-sensitive cases to the premium provider. |

---

## Board One-Pager

**Before (traditional SaaS):**  
Normalized revenue: **$2,500/user/month**  
Non-AI COGS: **$475/user/month**  
Gross margin: **81.0%**

**After (AI-enabled, baseline):**  
AI COGS: **$35/user/month**  
Total COGS: **$510/user/month**  
Gross profit: **$1,990/user/month**  
Gross margin: **79.6%** before incremental AI revenue

**After (AI-enabled, optimized):**  
AI COGS: **$21/user/month**  
Total COGS: **$496/user/month**  
Gross margin: **~80.2%** before incremental AI revenue

**Net margin shift:**  
The AI layer reduces total product gross margin by ~1.4 points at baseline and ~0.8 points after optimization before any AI revenue. The economic risk is manageable; the more important commercial question is whether customers will pay for measurable planning value.

## CFO Gate

Do not scale merely because inference is affordable. Scale only when:
- value is measurable;
- willingness to pay is demonstrated;
- fully loaded AI COGS is tracked;
- optimized routing passes quality gates; and
- the AI package is margin-accretive or strategically justified.
