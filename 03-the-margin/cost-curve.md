# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | $9.60 | Frontier-model usage for complex, ambiguous, or high-impact planning recommendations |
| Inference (cascading/triage) | $8.40 | Small and mid-tier models for forecast flagging, prioritization, and standard driver analysis |
| Infrastructure | $0 incremental | Core platform infrastructure is already captured within ShelfSense's existing non-AI COGS baseline |
| Data/storage | $0 incremental | Existing planning data storage is included within current SaaS COGS for this model |
| Human-in-the-loop | $0 incremental | Planner review is part of the existing customer workflow; no dedicated human-review operation is assumed at steady state |
| **Total AI COGS** | **$18.00** | Based on ~300 AI requests/user/month at a blended cost of ~$0.06/request |

## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->

**Triage model:** Small model for routine forecast classification, flagging, and prioritization  
**Frontier model:** High-reasoning model for ambiguous, multi-signal, or financially consequential planning recommendations  
**Routing rule:** Use the cheapest model that meets the required quality threshold. Route routine tasks to small/mid models and escalate only low-confidence, conflicting-signal, unusual, or high-financial-impact cases to the frontier model.  
**Expected cascade ratio:** Current baseline ~80% lower-cost models / 20% frontier; target ~90% lower-cost models / 10% frontier

### Cost Optimization Target

Management target: **Reduce AI COGS by 40% without compromising quality.**

Target blended cost:

- Current: **$0.060/request**
- Target: **$0.036/request**
- Current AI COGS: **$18.00/user/month**
- Target AI COGS: **$10.80/user/month**

Target workload mix:

| Workload | Model | Volume | Target Cost/Request | Why This Model |
|----------|-------|--------|--------------------|----------------|
| Routine flagging / prioritization | Small | 50% | $0.008 | Primarily classification, ranking, and threshold-based work. A frontier model adds limited incremental quality for repetitive structured tasks. |
| Standard driver analysis | Mid | 40% | $0.040 | Requires combining several planning signals and generating grounded explanations. Small models may oversimplify relationships; frontier reasoning is unnecessary for most standard cases. |
| Complex / high-risk decisions | Frontier | 10% | $0.160 | Used only where signals conflict, confidence is low, or financial impact is high. Stronger reasoning is justified because recommendation quality matters more than inference cost. |

Quality is protected through evaluation thresholds and confidence-based escalation rather than using cheaper models indiscriminately.

## Pricing Model

**Current pricing:** ShelfSense is sold as an enterprise SaaS subscription. For Module 3 unit-economics modeling, revenue is normalized to **$2,500 per AI-enabled planner per month**. This is an internal allocation for the case study, not a literal seat price.

**Proposed AI pricing:** Retain the existing ShelfSense platform subscription and add an AI usage allowance / consumption component tied to AI-assisted planning activity. Final pricing should be validated through customer willingness-to-pay testing rather than derived from model cost alone.

**Model:** **Hybrid — base subscription + usage**

ShelfSense should monetize the value of AI-assisted planning work rather than simply charge customers for access to an AI feature. Pure outcome-based pricing is premature because inventory reduction, forecast improvement, and avoided stockouts cannot yet be attributed solely to ShelfSense.

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | AI COGS rises from $18 to ~$54/user/month. With $475 non-AI COGS, gross margin falls from ~80.3% to ~78.8%. | Increase cascading, reserve frontier models for high-value decisions, activate alternate providers, and optimize context/token usage. |
| Heaviest segment doubles | Assuming the highest-usage cohort represents ~40% of AI volume, AI COGS rises to ~$25.20/user/month and gross margin remains ~80.0%. | Apply usage allowances, caching, batching, and model routing so higher adoption does not translate linearly into frontier-model cost. |
| Model provider raises prices 50% | If the primary frontier-model cost rises 50%, AI COGS increases from ~$18 to ~$22.80/user/month and gross margin is ~80.1%. | Trigger vendor portability plan, benchmark alternate models against ShelfSense's eval set, and route only quality-sensitive workloads to the premium provider. |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->

**Before (traditional SaaS):**  
Normalized revenue of **$2,500/user/month**, non-AI COGS of **$475/user/month**, and approximately **81.0% gross margin**.

**After (AI-enabled):**  
At baseline usage, AI adds approximately **$18/user/month** in COGS. Total COGS becomes **$493/user/month**, gross profit is approximately **$2,007/user/month**, and gross margin is approximately **80.3%** before any incremental AI revenue.

With the 40% AI cost-optimization strategy, AI COGS falls to approximately **$10.80/user/month**. Total COGS becomes approximately **$485.80/user/month**, and gross margin improves to approximately **80.6%**.

**Net margin shift:**  
Approximately **-0.7 percentage points at baseline AI cost**, improving to approximately **-0.4 percentage points after cost optimization**, before any incremental AI monetization. Because AI COGS remains small relative to ShelfSense's normalized enterprise revenue base, even a modest AI expansion charge could make the AI offering margin-accretive while preserving healthy SaaS economics.
