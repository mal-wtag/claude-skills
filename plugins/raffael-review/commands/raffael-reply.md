---
description: Paste Raffael's review comments and get a fix or a reply that will land for each one
argument-hint: "<pasted review comments>"
---

Review comments from Raffael:

$ARGUMENTS

If nothing was pasted, ask for the comments (or a PR number to read them with `gh`).

Use the `raffael-review` skill's "When Raffael has reviewed a PR" steps. For each
comment:
- Quote it briefly, name the pattern behind it.
- Decide: **Fix** (make the change, or show it) or **Reply** (the code is right).
- For a reply, draft it so it lands with him: short, polite, a concrete reason and
  evidence (a link, a log line, the gem source, SQL output). Never "it works on my
  machine" or "smallest change to close the review".

Finish with one line on any habit that showed up more than once, so it gets caught
before the next PR.
