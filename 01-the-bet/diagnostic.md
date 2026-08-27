# Three-Axis Vulnerability Diagnostic

## Product

**Product:** ShelfSense — B2B Demand & Promotion Planning Platform
**Your Role:** Senior Product Manager

## Scores

### Contextual Moat — 4/5

_Workflow depth × switching cost._

**Score rationale:**
ShelfSense is embedded in a high-value, recurring demand-planning workflow. It brings together historical sales, promotions, inventory, retailer forecasts, forecast history, and planner overrides inside the same planning cycle, creating meaningful workflow depth and switching cost. It is not a 5 because customers could still migrate to another enterprise planning suite with sufficiently strong integrations and implementation support.

Named attacker (from partner challenge): SAP / SAP Integrated Business Planning (IBP)

### Data Advantage — 3/5

_Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?_

**Score rationale:**
ShelfSense has valuable customer-specific data, including forecast-versus-actual performance, promotions, inventory, and planner overrides. However, the advantage does not yet compound strongly: customer datasets are siloed and inconsistent, contracts restrict cross-customer model training, and many planner overrides lack structured reasons. ShelfSense therefore has rich data, but not yet a defensible proprietary data flywheel.

Named attacker (from partner challenge): SAP / SAP Integrated Business Planning (IBP)

### Platform Exposure — 3/5

_Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native — then what?_

**Score rationale:**
A generic AI assistant cannot easily replace ShelfSense's end-to-end planning workflow, but established enterprise planning platforms could embed comparable AI capabilities around forecasting, anomaly detection, and decision support. ShelfSense has some protection from workflow depth and integration, but the AI features themselves would not be difficult enough to copy to provide a moat on their own.

Named attacker (from partner challenge): SAP / SAP Integrated Business Planning (IBP)

## Top Vulnerability

Data Advantage. ShelfSense has rich customer-specific data, but it does not yet have a proprietary data loop that compounds across customers.

## Confidence Level

H — High confidence. The workflow moat is credible, but the lack of a compounding proprietary data advantage is a clear strategic weakness that should carry forward into Module 2's flywheel analysis.
