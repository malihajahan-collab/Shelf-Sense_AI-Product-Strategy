# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** | Production provider has not been permanently committed. The prototype proves workflow, not provider portability. | M | Maintain an approved primary + backup provider before production launch; reserve frontier inference for high-risk cases. |
| **Abstraction** | Model-agnostic abstraction is a design requirement, not yet a proven production capability. | H | Implement provider adapters so retrieval, prompts, policy logic, and application state remain outside vendor-specific APIs. |
| **Routing** | Cascading logic is defined conceptually but has not yet been production-tested. | M | Build confidence/risk-based routing and a deterministic fallback for basic triage before launch. |
| **Eval** | A seed golden dataset and reliability contract exist, but the evaluation set is too small for production portability decisions. | H | Expand the eval suite and require every backup model to pass the same task-level thresholds before being approved. |

## Portability Score

**Partial — design intent exists, but portability is not yet proven.**

Production launch is blocked until ShelfSense can switch the high-volume triage path to an approved backup model without breaking quality or policy controls.

## If the primary vendor doubles pricing tomorrow:

**48-hour response after portability readiness is achieved:**

1. Route routine classification and prioritization to the approved low-cost backup model.
2. Keep the premium/frontier model only for low-confidence or high-financial-impact cases.
3. Disable non-essential generative features temporarily if needed.
4. Run the backup provider against the golden dataset before increasing traffic.
5. Use cached context, retrieval filtering, and batching to reduce token consumption.

## If the primary vendor ships a competing product:

ShelfSense does not defend itself through model ownership. Its defensible asset is the **customer-specific CPG decision graph**: planning context + structured planner corrections + decision reasons + observed outcomes + workflow integration.

A model provider can reproduce generic explanation and recommendation capabilities, but it does not automatically inherit the customer's operational decision history or ShelfSense's embedded planning workflow.

## Board Requirement

**No production dependency on a single model provider without a tested fallback path.** Vendor portability is a release criterion, not a future optimization.
