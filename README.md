# What would Raffael review? 🔍

A Claude Code plugin, lovingly extracted from real code reviews.

> Could we review this before Raffael does? IMHO that would save us a round trip, no? 🤔

You open a PR. You wait. Then it lands:

> `prettier` pls

> I18n

> Why is this needed?

> This should be authorized.

> ditto

`raffael-review` lets you take that review **before** you open the PR. It reads your
branch and tells you what Raffael would most likely comment, in his voice, with a fix
or a ready-made reply for each one.

It was distilled from years of his real code reviews. Here are the greatest hits:

| He says | What it means |
|---|---|
| "Could we name it after what it does?" | `fetch_x` that also saves is not a fetch |
| "This should be authorized." | every endpoint, every record, no exceptions |
| "Is this test red if you revert the change?" | a test that can't fail is decoration |
| "What is this used for?" | if nobody knows, delete it |
| "Don't we have this already?" | we do. it's two folders over |
| "`prettier` pls" | the robot was right, run it |
| "I18n" | yes, even that one string |
| "`null: false` pls" | booleans have two states, not three |

### Install

```bash
/plugin marketplace add mal-wtag/what-would-raffael-review
/plugin install raffael-review@raffael
```

### Commands

| Command | What it does |
|---|---|
| `/what-would-raffael-review` | The full prediction: every comment he'd likely leave, in his voice, with a fix or reply, plus his verdict (✅ approved / 💬 a few "Could we…?" / 🔁 requested changes) |
| `/raffael-bingo` | Plays **Raffael Bingo** against your diff. 16 classics, from "`prettier` pls" to "Never use floats for money". Get a full row and you win nothing, but you'll know 🎉 |
| `/raffael-pls` | 30-second sweep for the one-word nits ("I18n", "Indention", "Newline pls :)") so he never has to type them again |
| `/ask-raffael <question>` | "Model or service?" "Do I need a migration for this?" Get the answer he'd most likely give, IMHO-first |
| `/raffael-reply <comments>` | Paste his review, get a fix or a reply that will actually land with him (hint: evidence, not "works on my machine") |

Or just talk to it:

```
What would Raffael say about this branch?
```

```
Raffael left these comments, help me reply: <paste>
```

### Raffael Bingo 🎱

Tape this to your monitor. Before opening a PR, try to keep your card empty.

|  |  |  |  |
|---|---|---|---|
| `prettier` pls | I18n | Why is this needed? | This should be authorized. |
| `null: false` pls | Don't we have this already? | ditto | What if it's an empty array? |
| Indention | Please also test the reverse | IMHO this belongs into a service | Newline pls :) |
| Could we name it after what it does? | Never use floats for money | Is this test red if you revert it? | Could you create a follow-up story? |

### Field guide to his comments

- **"Could we…?"** is not a question. It's a change request wearing a nice shirt.
- **"IMHO"** means he's pretty sure. **"Not sure, but…"** means he's very sure.
- **"…, no?"** at the end means "I already checked, but I'm giving you a chance".
- **"ditto"** means you did it again. Probably in the next file too.
- **"?"** alone means he read it twice and still has no idea why it exists.
- **Bold text** means stop everything, it's security or money.
- **😄** means it's a nit and he's being nice about it. Fix it anyway.
- **"Nice catch 👍"** is rare. Screenshot it.

You get each predicted comment the way he would write it, plus a **Fix** or a **Reply**:

> **`app/controllers/reports_controller.rb:42`** · Blocker · authorization
>
> Could we authorize the specific report here? Right now anyone with `:read, Report`
> can pass any id, no?
>
> **Fix:** load it through `accessible_by`.

### Hack on it

Want your local skill to always match this repo? Clone it and link the skill
folder into your skills directory:

```bash
git clone git@github.com:mal-wtag/what-would-raffael-review.git ~/src/what-would-raffael-review
ln -s ~/src/what-would-raffael-review/plugins/raffael-review/skills/raffael-review ~/.claude/skills/raffael-review
```

Edit `SKILL.md`, try it straight away, then commit and push. Everyone else gets it
with `/plugin marketplace update raffael`.

If you have the plugin installed as well, the linked folder and the plugin both
provide the skill. That's harmless, but uninstall one if Claude gets confused.

### FAQ

**Will this get my PR approved first try?**
Not sure, but... IMHO it can't hurt 😄

**Does it replace Raffael?**
No. It replaces the *second* round of review, which is the one nobody enjoys.

**Is it always right?**
It's a prediction. If he says something the skill didn't see coming, congratulations,
you've found new material. Please update the skill.

**Why does it ask so many questions?**
Could we not ask that question? 😉

---

*No Raffaels were harmed in the making of this skill. Several `console.log`s were.*
