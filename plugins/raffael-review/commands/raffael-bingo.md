---
description: Play Raffael Bingo against the current diff. How many of his classics does your branch trigger?
argument-hint: "[base branch]"
---

Diff the current branch against $ARGUMENTS (if empty, the PR base or `main`/`master`).
Using the `raffael-review` skill's patterns, check which of these 16 classics the
diff would trigger. Only mark a square when there is a real line in the diff that
earns it.

|  |  |  |  |
|---|---|---|---|
| `prettier` pls | I18n | Why is this needed? | This should be authorized. |
| `null: false` pls | Don't we have this already? | ditto | What if it's an empty array? |
| Indention | Please also test the reverse | IMHO this belongs into a service | Newline pls :) |
| Could we name it after what it does? | Never use floats for money | Is this test red if you revert it? | Could you create a follow-up story? |

Print the card as a 4x4 markdown table with `✅` on the triggered squares and `·`
on the rest. Under it, for each triggered square, one line: the square, then
`file:line`.

Then the score:
- 0 squares: "Clean card. Raffael may just say LGTM 👍"
- a full row, column or diagonal: "**BINGO!** 🎉" plus which line
- 8 or more: "Blackout incoming. Maybe grab a coffee before opening the PR ☕"
- otherwise: "N/16. Not bad, not great 😄"

Keep it fun but honest: never mark a square without evidence.
