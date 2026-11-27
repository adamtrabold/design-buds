# design-buds

A Claude skill describing a design team and how it works: an orchestrator,
two product designers (systems focus, visual focus), a design director, a
builder, a reviewer, an expert seat and an on-request critic. It scales
from "just do it" to a full design loop, depending on how open the work is.

## What's here

```
.claude-plugin/marketplace.json   lists the two plugins below
plugins/design-buds/              the team
  skills/design-buds/
    SKILL.md        intent line, how much team, fidelity, rules, talking
                    to the owner
    shared.md       pasted at the top of every brief: the owner's words,
                    getting to unexpected ideas, writing
    design-loop.md  concept rounds, handoff, execution, when stuck
    roles/          each teammate's brief, pasted verbatim
    tools/          Impeccable
plugins/taste/                    the owner's taste log (Adam's)
  skills/adam-taste/
    SKILL.md        how the log is read and added to
    taste.md        the log
```

## Install

**claude.ai (reaches chat, Cowork and Claude Code):**

1. Customize → Plugins → Add → Add marketplace, and enter
   `adamtrabold/design-buds`.
2. Install `design-buds`. Install `adam-taste` only if you're Adam.
3. Turn on "Sync automatically" so changes pushed here arrive on their own.
4. If you uploaded design-buds as a zip before, delete that copy under
   Customize → Skills so they don't compete.

**Claude Code only:**

```
/plugin marketplace add adamtrabold/design-buds
/plugin install design-buds@design-buds
```

Turn on auto-update for the marketplace in `/plugin` → Marketplaces.

**Your own taste log:** copy `plugins/taste` into your own repo (or this
one, forked), rename the skill to `<you>-taste`, empty `taste.md`, and
point its "Adding to it" section at your repo. design-buds reads whichever
`*-taste` skill is installed.

Optional: add a line to your claude.ai personal preferences, such as
"Always work as my design-buds skill describes when we're making things."

## Credits

- [Impeccable](https://github.com/pbakaus/impeccable) by Paul Bakaus: an
  open-source design toolkit (Apache-2.0) that detects common design
  problems. design-buds offers to install it into a project and uses it
  when the real product's look changes (`tools/impeccable.md`). It's a
  separate project with its own licence.
- [Oblique Strategies](https://en.wikipedia.org/wiki/Oblique_Strategies)
  by Brian Eno and Peter Schmidt (1975). The team draws cards by chance to
  push past obvious ideas. The deck is referenced, not reproduced: one card
  is quoted at a time, and no copy of the deck is included here.
