# Data Flywheel Map


## Flywheel Loops

| Loop | What It Measures | Score 1 | Score 5 | Score |
|------|------------------|---------|---------|-------|
| **Correction** | Do users fix AI outputs? Is that signal captured and reused? | No capture | Automated learning loop | 3/5 |
| **Preference** | Does the product learn individual / team preferences over time? | Stateless | Deep personalization | 2/5 |
| **Domain Context** | Does usage in one area improve quality in adjacent areas? | Siloed | Cross-domain transfer | 4/5 |
| **Network** | Does each new user / team make the product better for everyone? | Isolated | Strong network effects | 1/5 |

### Correction Loop - 3/5
**What we capture today:** Planner overrides, forecast-versus-actual outcomes, timing of forecast changes, and some planner behavior. Structured reasons for overrides are inconsistent.  
**How it compounds:** The AI Copilot will explicitly capture Accept / Modify / Reject decisions plus reason codes and later connect those decisions to actual outcomes. This can improve future prioritization and explanations inside the same customer's workflow.

### Preference Loop - 2/5
**What we capture today:** Planner review and override behavior, but no persistent preference layer.  
**How it compounds:** Repeated usage can teach ShelfSense which signals, thresholds, categories, and risk conditions matter to each team. This becomes a customer-specific personalization asset.

### Domain Context Loop - 4/5
**What we capture today:** Historical sales, promotions, inventory, retailer forecasts, forecast performance, planner decisions, and outcomes within one planning workflow.  
**How it compounds:** More decisions create richer context across adjacent demand-planning scenarios, strengthening the customer-specific decision graph.

### Network Loop - 1/5
**What we capture today:** Customer-specific data is largely isolated, and current contractual constraints do not provide a reliable cross-customer learning mechanism.  
**How it compounds:** It does not meaningfully compound across customers today. Cross-customer learning is therefore **not part of the core moat assumption**.

**Total Flywheel Score: 10/20**  
**Weakest Loop:** Network Loop - 1/5  
**Fix for weakest loop:** Do not depend on a network effect that does not yet exist. First build strong customer-level correction, preference, and outcome loops. Explore opt-in, privacy-safe benchmarking only after legal, contractual, and customer validation.

---

## Revised Moat Thesis

ShelfSense's near-term moat is:

> **Customer-specific decision intelligence created by combining CPG workflow context with structured planner corrections and observed outcomes.**

The long-term opportunity for cross-customer learning is optional upside, not a requirement for the initial strategy to work.

---

## Encroachment Threat Assessment

### 1. Platform Encroachment
**Attacker:** SAP / SAP IBP  
**Vector:** Embed "good enough" AI exception management and driver explanation directly inside the ERP/planning workflow, using native data access, bundling, procurement simplicity, and existing contracts.  
**Time-to-threat:** 6-12 months  
**% of value at risk:** ~40% scenario estimate

### 2. Vertical Competitor
**Attacker:** Blue Yonder  
**Vector:** Provide deeper supply-chain-specific AI planning and exception management inside an established planning suite.  
**Time-to-threat:** 6-12 months  
**% of value at risk:** ~30% scenario estimate

### 3. Adjacent Expansion
**Attacker:** Microsoft  
**Vector:** Extend Copilot, Power BI, and enterprise data tooling into planning analysis and explanation, reducing the need for a separate generic AI interface.  
**Time-to-threat:** 12-18 months  
**% of value at risk:** ~20% scenario estimate

> Percentages above are strategic stress-test assumptions for the fictional case, not market measurements.

---

## 90-Day Encroachment Plan

**Attacker:** SAP / SAP IBP  
**Attack vector:** Use installed base, source-data proximity, and bundling to make standalone ShelfSense AI appear redundant.

**Weeks 1-4 - what they ship:**  
A native AI assistant flags forecast exceptions, summarizes drivers, and suggests planner checks using SAP data already in the customer's environment.

**Weeks 5-8 - how they poach users:**  
SAP bundles the feature into enterprise agreements and emphasizes lower integration effort, fewer vendors, and simpler governance.

**Weeks 9-12 - why users don't come back:**  
Customers accept a "good enough" AI feature because it lives where their source data and planning processes already exist.

**Our defense:**  
Do not compete on the visible assistant. Build a deeper decision lineage that remembers what each planning team changed, why they changed it, and what happened afterward. Use that feedback to make ShelfSense measurably more useful with continued use inside each customer's CPG planning workflow.
