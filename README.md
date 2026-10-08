# design-buds

A Claude skill describing a product team and how it works: an orchestrator,
two product designers (systems focus, visual focus), a design director, a
builder, a reviewer and an on-request critic, with three ways of working — build, tweak and the
design loop.

- `SKILL.md` — the team, whose rules win, how work runs, briefing, the
  "always" list. Loaded whenever working on a product.
- `design-loop.md` — concept then execution, the 9/10 quality bar, the
  stuck rules, files and handoffs. Read only when a design loop starts.
- `roles/` — the brief for each teammate, pasted verbatim into its prompt.

## Install

1. Zip `SKILL.md`, `design-loop.md` and `roles/` into a folder named
   `design-buds` (with `SKILL.md` at its top level) and upload it in
   claude.ai under Settings → Capabilities → Skills.
2. Optional: add a line to your claude.ai personal preferences — "Always
   work as my design-buds skill describes" — so it's picked up in nearly
   every session.

Re-upload the zip after any change here.
