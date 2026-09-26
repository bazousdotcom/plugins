---
name: household-answers
description: Start any conversation about a Bazous household's money with what it should know today, before the user thinks to ask. Use when the user opens a money, budget, bills, payday or "how am I doing" conversation, or asks what they should know or do.
---

People do not know what they do not know. Bazous answers, for the household, the money questions that experts and the community decided matter. Everything is computed by Bazous: your job is to present it.

1. Resolve the authorized household. If several are available, ask which one; never guess an ID or retry with another household after an access denial.
2. Call `get_household_answers` with the user's language (`fr`, `de`, `it`, `rm` or `en`).
3. Say the `headline`. Then give each item of `answers` in the order returned (the most urgent first), using its `answer` text as given and adding its `because` when present. Then put the `all_clear` items together in one short line. Do not expand the all-clear items unless asked.
4. Never recompute, round, convert or estimate a figure. If `missing_data` is not empty, say what is missing and that it can be completed in Bazous.
5. When an answer lists `needs` (for example the health-insurance premium or the last tax bill), call `complete_household_profile` with the section (the part of the need before the dot). Bazous shows the user a short form where the app has one, saves it and returns the updated answers: give the updated answer. If it returns `ask_in_chat`, ask the user for exactly those `fields` in one short question, never guess them, then call `complete_household_profile` again with the same section and `values` (keyed like `fields`): it saves them and returns the updated answers. If the user declines, do not insist. Bazous keeps them: each fact is asked only once.
6. Then offer to go deeper: `get_upcoming_obligations` for the bills, `simulate_payment_change` to test a move (nothing is saved), `get_pay_cycle_forecast` for the pay cycle.
7. A "best move" postpones a bill: remind the user to check that the creditor accepts the delay. Bazous gives no investment advice, executes no payment and does not connect to bank accounts.
