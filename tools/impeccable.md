# Impeccable

[Impeccable](https://github.com/pbakaus/impeccable), by Paul Bakaus, is an
open-source design toolkit: a detector that finds common design problems in
a page (tiny text, all-caps body, clipped overflow and more), and a skill
with design commands such as `critique` and `audit`. It isn't part of
design-buds; the team uses it when a project has it.

## First time design-buds runs in a project

Check whether the Impeccable skill is available in this session (it's
listed as `impeccable`) or present in the project at
`.claude/skills/impeccable/`.

- **Present:** use it as below.
- **Not present, and the project's notes don't say the owner declined it:**
  ask the owner once, in one line: "Impeccable (github.com/pbakaus/impeccable)
  checks designs for common problems — install it into this repo?"
  - **Yes:** install it (below) and note the version in
    `.claude/skills/impeccable/VENDOR.txt`.
  - **No:** say you'll note that in the repo so you don't ask again, and add
    `.claude/skills/impeccable.declined` with the date. Never ask again in
    this project unless the owner brings it up.

## Installing and updating

Impeccable's own installer needs impeccable.style, which some environments
block; install from GitHub instead.

1. Find the newest release tag named `skill-vX.Y.Z` in
   `https://github.com/pbakaus/impeccable`.
2. Copy that tag's `.claude/skills/impeccable/` folder into the project at
   `.claude/skills/impeccable/`, plus the repo's `LICENSE` into the same
   folder (it's Apache-2.0).
3. Write `VENDOR.txt` there: the tag, the date, and the npm version used for
   the detector (the newest `impeccable` on npm at that time).
4. Commit it under the project's rules.

**Updates:** the first time design-buds runs in a session, compare the
installed tag with the newest `skill-v*` tag. If there's a newer one,
update in place (same steps), and tell the owner in one line. Exception:
if the project pins Impeccable on purpose — its own design gate, or a
VENDOR file that says it's pinned — never update it; mention the newer
version once instead.

## How the team uses it

- **A project's own design gate wins.** If the project has its own gate
  built on Impeccable, run that instead of the steps below.
- **Builder, on any change to the real product's look:** run the detector
  on the page before and after the change —
  `npx -y impeccable@<npm version from VENDOR.txt> detect --json <file or URL>`.
  New findings block landing until they're fixed or the owner waives them.
  Findings that were already there before the change don't block.
- **Concepts and prototypes:** the detector is advisory — report findings,
  don't block on them.
- **Reviewer:** checks the detector ran and its result. "Couldn't run" is
  never a pass; say so.
- **Design director, critic and designers:** may use Impeccable's commands
  (`critique`, `audit`, and others) as input to their judgment — never as the
  verdict.
