---
name: cashflow-what-if
description: Show what moving, adding or removing a Bazous payment would change, without saving anything. Use for "et si je décale un paiement ?", what-if cash-flow questions, postponement comparisons and payment scenarios.
---

1. Resolve the intended authorized household. If several are available, ask which one; never guess an ID or retry with another household after an access denial.
2. Start with `get_household_answers` in the user's language (`fr`, `de`, `it`, `rm` or `en`). Its `what-if` answer is Bazous's best move, already computed by the engine: which bill to postpone to payday and how much the low point rises. Where the app shows the Bazous cards, it is drawn before and after; say its answer as given (and its `because`), without reading the whole card again.
3. Only when the user names a specific payment, date or amount that the best move does not cover: fetch `get_upcoming_obligations` to find that existing payment for move/remove (never invent an obligation ID), get the requested date, and for add require an explicit positive amount in the household's base currency (never convert a foreign amount or infer a missing value). Then call `simulate_payment_change` with action move, add or remove, within its 120-day horizon; omit amount for move/remove and obligation_id for add.
4. Compare the baseline and scenario returned by that same call, with their exact safe-before-payday, low balance and date. Do not calculate these yourself or mix snapshots from different households or times.
5. Say that nothing was changed. If the forecast is incomplete, say which inputs are missing; never present null as zero. A postponement only works if the creditor accepts it: remind the user to check.
6. A simulation is not an authorization to reschedule or mark paid. If the user later asks to persist a change, use the supported explicit workflow and its confirmation.
