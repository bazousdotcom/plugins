---
name: cashflow-what-if
description: Simulate moving, adding or removing a Bazous payment without saving changes. Use for what-if cash-flow questions, postponement comparisons and payment scenario analysis.
---

1. Resolve the intended authorized household. Fetch `get_upcoming_obligations` to identify an existing payment for move/remove; do not invent an obligation ID.
2. Get the requested date for move/add. For add, require an explicit positive amount in the household’s base currency. Do not silently convert a foreign amount or infer a missing value.
3. Call `simulate_payment_change` with action move, add or remove. Dates must be within its supported 120-day horizon. Omit amount for move/remove, and omit obligation_id for add.
4. Compare the baseline and scenario returned by the same call. Use their exact safe-before-payday, low balance and date. Do not calculate these with an LLM or combine snapshots from different households/times.
5. Explain that no payment was changed. If the forecast is incomplete, state which inputs are missing; never represent null as zero.
6. A request to simulate is not authorization to reschedule or mark paid. If the user later asks to persist a change, use the supported explicit workflow and required confirmation.
