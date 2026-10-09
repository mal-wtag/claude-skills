---
description: Predict Raffael's full review of the current branch, in his voice, with fixes and replies
argument-hint: "[base branch, default: the PR base or main/master]"
---

Use the `raffael-review` skill to predict the review Raffael would leave on the
current branch. Base branch: $ARGUMENTS (if empty, use the open PR's base, else
`main` or `master`, whichever exists).

Follow the skill's "Predicting his review of a branch" steps and write every
comment the way he would. Blockers first, then frequent asks, then a short
"probably fine" list.

End with his likely verdict on one line, one of:
- `✅ Approved from security perspective` (nothing blocking)
- `💬 Approved, with a few "Could we…?"` (only asks and nits)
- `🔁 Requested changes` (any blocker), followed by the blocker count
