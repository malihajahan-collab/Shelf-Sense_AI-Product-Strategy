# Three-Axis Vulnerability Diagnostic

## Product

**Product:** ShelfSense — B2B Demand & Promotion Planning Platform  
**Your Role:** Senior Product Manager

---

## Scores

### Contextual Moat — 4/5
*Workflow depth × switching cost. Would users leave in a weekend if a competitor showed up?*

**Score rationale:**  
ShelfSense is embedded in a recurring, high-value demand-planning workflow and already connects historical sales, promotions, inventory, retailer forecasts, forecast history, planner overrides, and S&OP preparation. That creates meaningful workflow depth and switching cost. The score remains below 5 because large planning suites can replace this layer if they combine comparable capabilities with easier integration and procurement.

**Named attacker (from partner challenge):** SAP / SAP Integrated Business Planning (IBP)

---

### Data Advantage — 3/5
*Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?*

**Score rationale:**  
ShelfSense sees customer-specific signals a generic model does not automatically possess: forecast-versus-actual performance, promotion history, inventory constraints, planner overrides, and workflow outcomes. However, many correction reasons are unstructured and customer contracts restrict broad cross-customer model training, so ShelfSense has valuable data but not yet a proven compounding data moat.

**Named attacker (from partner challenge):** SAP / SAP IBP, because it already sits close to source-of-truth enterprise planning data.

---

### Platform Exposure — 3/5
*Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native — then what?*

**Score rationale:**  
A generic assistant cannot easily replace the full ShelfSense workflow, but SAP, Microsoft, Blue Yonder, and similar platforms can reproduce visible AI features such as summarization, anomaly explanation, and recommendations. ShelfSense is protected by workflow context, but not by the AI feature itself.

**Named attacker (from partner challenge):** SAP / SAP IBP

---

## Top Vulnerability

**Data Advantage.** ShelfSense has strong customer context but has not yet converted planner corrections and business outcomes into a proprietary learning loop that clearly improves the product with continued use.

## Confidence Level

**M — Medium confidence.** The problem and contextual moat are credible, but the data flywheel, willingness to pay, and competitive durability remain unproven.

## Board Revision

The first AI bet should not attempt to become a broad autonomous decision engine. ShelfSense should begin with the workflow where its context is most useful and the risk is controllable: **prioritizing high-impact forecast exceptions, explaining the evidence behind them, and helping planners determine what to investigate next.**
