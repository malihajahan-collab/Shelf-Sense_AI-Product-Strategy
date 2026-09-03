# Data Flywheel Map


## Flywheel Loops

| Loop | What It Measures | Score 1 | Score 5 | Score |
|------|------------------|---------|---------|-------|
| **Correction** | Do users fix AI outputs? Is that signal captured and reused? | No capture | Automated retraining | 3/5 |
| **Preference** | Does the product learn individual / team preferences over time? | Stateless | Deep personalization | 2/5 |
| **Domain Context** | Does usage in one area improve quality in adjacent areas? | Siloed | Cross-domain transfer | 4/5 |
| **Network** | Does each new user / team make the product better for everyone? | Isolated | Strong network effects | 2/5 |

### Correction Loop - 3/5
**What we capture today:** Planner overrides, forecast-versus-actual outcomes, and the timing of forecast changes. Structured reasons for overrides are still inconsistent.  
**How it compounds:** When planners accept, reject, or change recommendations and ShelfSense later observes the actual outcome, those interactions become proprietary feedback on which signals and interventions worked.

### Preference Loop - 2/5
**What we capture today:** How planners review, prioritize, and override forecasts, but not a persistent planner or team preference profile.  
**How it compounds:** Repeated usage can teach ShelfSense which signals users trust, what thresholds trigger action, and how different teams respond to promotions, stockout risk, or forecast variance.

### Domain Context Loop - 4/5
**What we capture today:** Historical sales, promotions, inventory, retailer forecasts, forecast performance, and planner behavior within the same demand-planning workflow.  
**How it compounds:** More planning activity creates richer CPG-specific context across forecasting, promotions, inventory, and planner decisions, improving the quality of adjacent recommendations.

### Network Loop - 2/5
**What we capture today:** Customer-specific planning data and feedback, but customer data remains siloed and contractually restricted from broad cross-customer model training.  
**How it compounds:** A stronger loop would use permissioned, privacy-safe learning to identify reusable planning patterns across customers without exposing raw commercial data.

**Total Flywheel Score: 11/20**  
**Weakest Loop:** Network Loop - 2/5  
**Fix for weakest loop:** Build a permissioned, privacy-safe learning layer using shared taxonomies, de-identified outcome patterns, and benchmark signals so usage can improve ShelfSense across customers without pooling raw proprietary data.

---

## Encroachment Threat Assessment

### 1. Platform Encroachment
**Attacker:** SAP / SAP Integrated Business Planning (IBP)  
**Vector:** Embed AI forecasting, exception detection, driver analysis, and planner recommendations directly into the ERP and planning environment where many CPG customers already keep their source-of-truth data.  
**Time-to-threat:** 6-12 months  
**% of value at risk:** 40%

### 2. Vertical Competitor
**Attacker:** Blue Yonder  
**Vector:** Add deeper CPG-specific AI demand sensing, exception management, and planner recommendations inside an established supply-chain planning suite.  
**Time-to-threat:** 6-12 months  
**% of value at risk:** 30%

### 3. Adjacent Expansion
**Attacker:** Microsoft  
**Vector:** Extend Copilot across Dynamics 365, Power BI, and enterprise data workflows to provide planning analysis and recommendations without requiring a separate ShelfSense layer.  
**Time-to-threat:** 12-18 months  
**% of value at risk:** 20%

---

## 90-Day Encroachment Plan


**Attacker:** SAP / SAP Integrated Business Planning (IBP)  
**Attack vector (target the weakest loop):** Exploit ShelfSense's weak Network Loop by using SAP's installed base, native enterprise data access, and integrated planning workflow to offer comparable AI decision support inside SAP IBP.  
**Weeks 1-4 - what they ship:** SAP launches an AI planning assistant that flags forecast exceptions, explains likely demand drivers, and recommends planner actions using ERP and IBP data already available in the customer's environment.  
**Weeks 5-8 - how they poach users:** SAP bundles the capability into existing enterprise contracts, emphasizes lower integration effort and governance risk, and targets ShelfSense customers already using SAP with migration incentives.  
**Weeks 9-12 - why users don't come back:** Planning teams avoid duplicate data movement, procurement manages fewer vendors, and users receive similar AI support directly inside the system they already use for planning and execution.  
**Our defense:** Turn ShelfSense's workflow depth into a stronger proprietary learning loop by capturing structured planner corrections, linking them to actual outcomes, learning team preferences over time, and creating privacy-safe cross-customer intelligence that improves CPG-specific recommendations faster than a broad enterprise platform can.
