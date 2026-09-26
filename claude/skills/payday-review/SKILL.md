---
name: payday-review
description: Review a Bazous household’s upcoming bills, available cash before the next income and lowest projected balance. Use for payday reviews and questions about what must be paid before the next salary.
---

1. Identify the intended household. If several are available, ask the user to select one. Do not guess an ID or retry with another household after an access denial.
2. Call `get_household_snapshot`, `get_upcoming_obligations` and `get_pay_cycle_forecast` for that same household.
3. Use the forecast’s exact amounts, dates, currency and completeness status. Do not recalculate totals or substitute a bank balance for safe-before-payday. If any value is null, explain the missing input and ask for it.
4. Summarize cash now, due before the next scheduled income, safe-before-payday and the 30-day low point. The next scheduled income may be irregular income, not necessarily a salary.
5. Explain the main known obligations behind the result, without inventing dates or amounts. A forecast is conditional on recorded inputs, not financial advice.
6. Do not mark a bill paid or change data during a read-only review. Suggest inviting a partner only after a successful review; never send an invitation without a request.
