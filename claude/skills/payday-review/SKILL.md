---
name: payday-review
description: Review a Bazous household's bills before the next income, available cash and lowest projected balance. Use for payday reviews and questions about what must be paid before the next salary.
---

1. Identify the intended household. If several are available, ask the user to select one. Never guess an ID or retry with another household after an access denial.
2. Start with `get_household_answers` in the user's language. Its answers already say what is due before payday (`due-before-payday`), how low the balance goes (`low-point`), what will be left (`margin-after-payday`) and whether a pay cycle eats into reserves (`pay-cycles`), with the figures of the engine and, where the app shows Bazous cards, their drawing. Say those answers as given, most urgent first; do not read the whole card again.
3. Use `get_upcoming_obligations`, `get_pay_cycle_forecast` or `get_household_snapshot` only when the user asks for the detail behind an answer (the list of bills, the exact safe-before-payday), for that same household.
4. Use the exact amounts, dates, currency and completeness status returned. Do not recalculate totals or substitute a bank balance for safe-before-payday. If a value is missing, say which input is missing and that it can be completed in Bazous.
5. The next scheduled income may be irregular income, not necessarily a salary. A forecast depends on the recorded inputs; it is not financial advice.
6. Do not mark a bill paid or change data during a review. Suggest inviting a partner only after a successful review; never send an invitation without a request.
