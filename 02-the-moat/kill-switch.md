# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** | OpenAI is the primary provider for complex reasoning; lower-cost models can handle routine classification and explanation tasks. | M | Shift non-critical traffic to an alternate approved model provider and reserve OpenAI only for high-consequence recommendations. |
| **Abstraction** | ShelfSense uses a model-agnostic service layer so prompts, retrieval, business rules, and application logic are not tightly coupled to one provider. | L | Update provider configuration and run regression tests against the approved evaluation set before routing production traffic. |
| **Routing** | Requests are routed by complexity: small models for forecast flagging, mid-tier models for driver analysis, and frontier models only for complex or high-impact recommendations. | L | Reduce frontier routing, activate backup models, and temporarily restrict high-cost or non-essential AI workflows if required. |
| **Eval** | ShelfSense maintains task-level evaluation criteria for accuracy, grounded explanations, recommendation quality, and planner trust before a model is approved. | M | Run the replacement model against the same evaluation set and block migration if it falls below the minimum quality threshold. |

## Portability Score
**Partial**

ShelfSense is designed to avoid complete vendor lock-in, but frontier-model quality for complex planning recommendations may not be immediately interchangeable across providers.

## If OpenAI doubles pricing tomorrow:
Within 48 hours, ShelfSense would route routine workloads to lower-cost approved models, reduce frontier-model usage to only high-risk or ambiguous decisions, and benchmark alternative providers against the existing evaluation set. The objective would be to protect the quality threshold while keeping the blended AI cost within the planned unit economics.

## If OpenAI ships a competing product:
ShelfSense's defensibility is not the underlying model. Its advantage comes from its CPG-specific workflow context, historical sales and promotion data, planner corrections, forecast-versus-actual outcomes, enterprise integrations, and the proprietary learning loops created inside the demand-planning workflow.

A generic model provider could replicate AI capabilities such as summarization or recommendation generation, but it would not automatically possess ShelfSense's customer-specific planning context or accumulated decision feedback.
