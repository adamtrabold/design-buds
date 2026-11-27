# The design loop

For work where the idea itself is open: a new feature, a new look, a
redesign. You, the orchestrator, run it; teammates design and build.

Two phases: **concepts**, then **execution**. Nothing changes in the real
product until the owner picks a concept. The owner sees every concept
round; the director advises, it doesn't gatekeep.

## The work folder

One folder per piece of work: `design/<work>/` unless the project says
otherwise. One absolute path that every teammate reads and writes.

```
design/<work>/
  jam.md             the jam
  jobs.md            the user's jobs and flows
  concepts/          one file or folder per concept
  scores.md          the director's scores, takes and changes, in order
  owner.md           the owner's words, verbatim and dated, and what they
                     picked, rejected and why; ends with the tally
  handoff.md         the picked concept, for the builder
  notes/<role>.md    each persisting teammate's notes, and yours
```

Older work folders use the same names; carry on in them.

**The tally.** Keep three lines at the end of `owner.md`, updated each
round: rounds to the owner's pick, times the owner pushed back on the same
point, messages sent to the owner.

## Before the first round

1. **Intent line**, from `SKILL.md`.
2. **Structure first**, if the work has structure to agree: the user's
   jobs, requirements, or the categories of what goes on the screen or
   panel. The systems designer drafts it (`jobs.md`); send it to the owner
   in one short message and wait for their yes before concepts. On
   physical products, requirements and an engineering check come before
   form.
3. **Foundation.** If the product has no brand, visual reference or design
   system yet, the director asks the owner what it needs to know, one
   question at a time, before the first round.

## A concept round

1. **Jam (one pass).** Systems designer, then visual designer, then the
   director, each adding to `jam.md` once. Each starts with a real draw
   (`shared.md`) and records it. Add a second pass only if the first
   produced nothing that passes the generic test. Jobs and directions
   only, no scoring.
2. **Concepts.** The two designers make 2–4 concepts in `concepts/`,
   systems designer on how each works, visual designer on how it looks and
   feels. Concepts differ in kind. Each concept file holds the four-line
   summary (`shared.md`) and which draw or direction it came from. Make
   one only if the owner asked for one. At the fidelity the intent line
   needs: sketches by default.
3. **Director's review.** For each concept: a score 1–10 (9 means "I'd
   defend this to the owner as is"), a one-line take, and what it would
   change. It checks each against the intent line's "done when" and
   "keeping", runs the generic test, and names the source of every
   objection.
4. **One revision.** The designers act on the director's changes once.
   Changes it labels "director's opinion" are optional. The director
   re-scores. No further loops: whatever the scores, the round goes to the
   owner.
5. **Expert**, if one is on the work: reviews the revised concepts
   alongside the director, separately.
6. **To the owner, one message.** Each concept side by side:
   - its four lines;
   - the director's score, take and what it would still change;
   - the expert's view, if any. If the expert and director disagree, show
     both. Nobody loops to settle it.
   Then one line listing killed ideas ("Killed: X, Y"). Sketches of killed
   ideas only if the owner asks.
7. **The owner picks, combines, or sends notes.** Record their words in
   `owner.md`. Notes start the next round. Approved parts are kept from
   then on.

**Stale round.** If the owner calls a round average or weak, or a concept
fails the generic test, the next round starts with fresh draws, and at
least one concept must come from one. A stale round never gets just a
polish.

**Disagreeing with the owner.** A teammate who thinks the owner's direction
is wrong says so in one line, as a question you pass on. It never becomes a
concept on its own.

## Handoff

Once the owner picks:

1. The systems designer writes **How it works** in `handoff.md`:
   structure, flows, interaction patterns, every state (empty, error,
   sizes).
2. The visual designer writes **How it looks and feels**, for every state
   the first part names.
3. Both add a short **Why**: the decisions that make it work, and the
   owner's notes.
4. The director checks it matches what the owner picked and the owner's
   words in `owner.md`. Gaps are fixed before building.

The builder can't see this conversation; the handoff is everything it
knows.

## Execution

1. **Build** from `handoff.md` (`roles/builder.md`). Gaps go back to the
   designers; anything that would change the picked concept goes to the
   owner as a question, never decided by the team.
2. **Checks, at the same time:**
   - the director scores the build against `handoff.md`;
   - a fresh reviewer checks it works, meets the project's standards and
     lets the user do every job in `jobs.md` (`roles/reviewer.md`);
   - a blind read, if it encodes meaning (`SKILL.md`);
   - Impeccable, per `tools/impeccable.md`.
3. **Fix rounds: two at most.** The builder fixes everything found in one
   batch, the checks run again.
4. **To the owner:** stills or a live link, with the director's score and
   the review result. A clean review is required unless the owner says
   otherwise; anything still open after two fix rounds is listed plainly.
5. **Lands on the owner's yes** under the project's rules. A no: record
   why in `owner.md`; the director says whether it's a build fix or a
   concept change.

## When the team is stuck

Bring the owner in when:

- two concept rounds in a row end without a pick and the owner's notes
  keep hitting the same point (that's two pushes: re-state the intent line
  and check it);
- execution still has open problems after two fix rounds;
- the director, the expert or the designers keep raising the same blocker.

Send one short note: where it stands, why the team thinks it's stuck, and
the one question or decision that would unblock it. Pictures are fine,
labelled as not ready.

## Keeping teammates going

- **Keep the same agent** while it's on the same work, until its context
  gets heavy. Continue it by id or name if the session supports that;
  otherwise start a fresh one from its notes.
- **Fresh every time, no notes:** the reviewer, blind readers and the
  critic. They read only the files they're given by path.
- **Notes:** each persisting teammate updates `notes/<role>.md` briefly at
  the end of each round (where things stand, what's open, what's next),
  and fully before a handoff or when its context is heavy.
- **Your context:** pass paths, not contents. Don't read work in depth;
  skim the scores and notes. When your own context gets heavy, write a
  handoff with a ready-to-paste prompt and tell the owner.

## Why it's set up this way

- The owner sees every round, side by side, because they asked to ("I
  want to see every round but with the directors score, opinion, and what
  they'd change"), because the director's 9s often didn't match their eye,
  and because "I can only see one version how am I supposed to judge".
- One revision per round because looping for the director's 9 cost days
  without matching the owner's eye.
- Structure before layout because 13 rounds of panel layouts didn't land,
  and the category tree did in one pass.
- Concepts before execution so effort goes into the right idea before
  anything is built.
- The builder works from a written handoff because long, cluttered
  contexts make agents less reliable.
