---
description: 30-second nit sweep: catch the one-word comments before Raffael has to type them
argument-hint: "[base branch]"
---

Diff the current branch against $ARGUMENTS (if empty, the PR base or `main`/`master`)
and look only for the quick nits Raffael leaves as one or two words. Do not do a
full review.

Check for: unformatted code (`prettier` pls / rubocop), bad indentation
(Indention), missing newline at end of file (Newline pls :)), hardcoded
user-facing strings (I18n), booleans or defaulted columns without `null: false`
(`null: false` pls), typos in names and strings (typo), leftover `console.log`,
`puts`, `binding.pry`, `debugger` or commented-out code (?), and lint rules
disabled for a whole file.

Output one line per hit, in his style: `file:line` then the nit exactly as he'd
write it, e.g. `app/models/plan.rb:12  null: false pls`. Fix the trivial ones
right away if the user agrees.

If nothing is found: "No nits. Raffael is going to need new material 😄"
