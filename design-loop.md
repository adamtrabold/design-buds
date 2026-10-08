# The design loop

For anything new to design: a feature, a new look, a redesign. You, the
orchestrator, run it; teammates design and build. Two phases, concept then
execution. Don't mix them: concepts are not final UI, and nothing changes in
the real product until a concept is approved. Building to explore is always
allowed: when a prototype is the best way to show a concept, build one.

## The work folder

Every piece of design work gets **one** folder: `design/<work>/` in the
project unless the project says otherwise. Use a single absolute path that
every teammate reads and writes — design files are shared working files, so
teammates don't get private copies of this folder even if the project
isolates code changes. Pass every teammate the exact paths it needs.

```
design/<work>/
  jam.md             the shared jam
  jobs.md            the user's jobs and flows
  concepts/          one file or folder per concept
  scores.md          every score and objection, in order;
                     you write it
  owner.md           the owner's answers, rejections and reasons
  handoff.md         the approved concept, for the builder: how it works,
                     how it looks and feels, and why
  notes/<role>.md    notes for teammates that persist: notes/systems.md,
                     notes/visual.md, notes/director.md,
                     notes/builder.md,
                     and yours, notes/orchestrator.md
```

## Keeping teammates going

- **Keep the same agent** while it's on the same work, across phases, until
  its context gets heavy. Continue it by its id or name if the session
  supports that; otherwise start a fresh one from its notes file.
- **Fresh every round, no notes:** the jobs checker (a
  fresh product designer, systems focus) and the reviewer. Their value is that
  they haven't seen the work develop. Give them only the files they need, by
  path; they don't browse the work folder.
- **Every persisting teammate updates its notes file at the end of each
  round**: where things stand, decisions and why, scores and objections,
  open questions, what comes next. If an agent can't be continued, or its
  context gets heavy, a fresh one starts from that note — so the note is
  never more than a round old. Make it thorough. The same goes for you, in
  `notes/orchestrator.md`.

## Before the first round

If the product has no brand, visual reference or design system yet, the
first concept round is about setting that direction. The design director
asks the owner the questions it needs to establish the foundation first, and
the owner is told that early scores are provisional.

## Fidelity

Make each piece of work at the fidelity the feedback needs. Concepts can be
words, pictures, diagrams, or a working prototype when the idea or the
interaction only shows when you use it — built outside the real product, so
it can be thrown away. Execution is the real thing. Don't go to full polish
when a sketch answers the question — and don't hold back when the work needs
it. Never trade away quality to save cost.

## Concept phase — deciding what it should be

The design director owns this phase's outcome: delivering the best
concepts. It steers the team and decides which concepts go forward. The two
product designers build every concept together — neither makes the call
alone.

1. **Jam.** The product designers and the design director jam in
   `jam.md`, one turn at a time. Each turn, a teammate reads the file and
   adds to it — new ideas, sharper versions of others' ideas, combinations —
   then ends its reply with `NEXT: <role> — <why>`.
   - **The product designer (systems focus) goes first,** so it writes the
     user's jobs before reading anyone else's ideas.
   - You follow the nominations, with guardrails: everyone gets at least
     one turn per pass, nobody goes twice in a row, and a pass is over once
     everyone has had a turn. Two or three passes, no scoring.
   - The jam covers **the jobs** — what the user needs to get done — and
     **creative directions** — the big idea behind a concept: a metaphor, a
     philosophy, a reference point (for example, a settings screen treated
     like a well-organised toolbox), drawing on the owner's inspiration.
   - Keep it moving: every addition must add something new or make an idea
     sharper; drop weak ideas fast rather than polishing them; never settle
     on the idea everyone can live with. The jam ends after its passes even
     if it's still going.
2. **Jobs to the owner.** The product designer (systems focus) writes `jobs.md`
   from the jam. Send it to the owner in one short message: "these are the
   jobs — anything wrong or missing?" Don't wait for the answer: carry on,
   and fold it in when it arrives.
3. **Concepts.** The two product designers build 2–4 distinct concepts
   together in `concepts/`, taking turns with the same `NEXT:` relay (the
   systems designer starts): the
   systems designer on how each one works, the visual designer on how it
   looks and feels. Either can push or reshape any concept, or propose
   killing one, and says why in the concept file. Each concept says which
   directions it draws on. After every pair of designer turns, the design
   director steers: it gives direction, decides on any proposed kills, and
   either sends the designers round again or ends the building with
   `READY: <concepts going forward>`.
4. **Score.** The design director scores all of the round's concepts
   in one pass, 1–10.
5. Concepts under 9 go back: improve them or replace them. Iterate until at
   least one scores 9 or more, or the team is stuck (below).
6. **Jobs coverage.** The product designer (systems focus) checks each 9+
   concept against `jobs.md`. A concept that leaves a job unsupported goes
   back.
7. **Owner.** The owner sees the concepts that scored 9+ and cover every
   job, each with its score and the design director's reasoning. The owner
   approves one, or sends the team back.
8. **Handoff.** The two product designers write `handoff.md` for the
   approved concept, in this order: the systems designer the **How it
   works** part (structure, flows, interaction patterns, every state); then
   the visual designer the **How it looks and feels** part (visual design,
   motion, feedback, for every state the first part names); both add to a
   short **Why** part (the decisions that make it work, and the director's
   and owner's notes). Then two checks, and gaps are fixed before the build
   starts:
   - the systems designer checks the whole handoff against `jobs.md`;
   - the design director checks it matches the concept the owner approved
     and the owner's notes in `owner.md`.

   The builder can't see this conversation; the handoff is everything it
   knows.

## Execution phase — making the approved concept real

1. A builder builds the approved concept from `handoff.md`.
2. Gaps or deviations the builder flags go to the designers who made the
   concept (or fresh designers of the same focus, starting from their notes
   and the handoff). The design director decides whether answering one
   would change the concept itself; if it would, it goes to the owner as a
   decision question — what changed, the options,
   the team's recommendation — not as work to approve. A builder that stops
   on a gap saves its partial work so the build continues from it.
   Answers to gaps are added to `handoff.md`, so it stays the builder's
   single source.
3. Three checks run on the build at the same time:
   - the design director scores it 1–10 against `handoff.md`;
   - the jobs checker walks every job in `jobs.md` on it;
   - a reviewer checks that it works and meets the project's standards.
4. **The bar** is all three: a 9 or more, every job passing, a clean review.
   Short of it, the builder fixes everything found in one batch, then the
   checks run again. Repeat until the bar is met, or the team is stuck.
5. **Owner.** Once the bar is met, the owner sees the finished work; on the
   owner's "yes", it lands under the project's rules. On a no, record why in
   `owner.md`; the design director decides whether it's a fix to the build
   (back to step 4) or a change to the concept (back to the concept phase).

## Quality bar

Every concept and every build gets a score from 1 to 10 from the design
director, where 9 means "I would defend this to the owner as is". **The
owner never sees anything that scored under 9.** Concept and build are
scored separately: a polished build of a weak concept is still a weak
concept. The director keeps its scoring history so scores are consistent,
and says each round whether the work really changed.

The owner can ask for the critic (`roles/critic.md`) on any work, at any
point, for a separate set of eyes. Give it only the work, the owner's words
and direction, `handoff.md` if there is one, and `owner.md`. Its view goes
straight to the owner and changes nothing on its own.

Here the design director scores concepts it helped steer, and the systems
designer checks coverage on concepts it helped build. That's by design: the
owner is the independent check, and the critic is there when they want one.

You enforce this:

- No work goes to the owner without a design director score of 9 or more. The
  only other messages in the loop are the jobs sent to the owner, foundation
  questions, decision questions, stuck notes, and critic reports the owner
  asked for.
- Score again only after the work has really changed. Keep every score in
  `scores.md`; never discard one to get a better one.
- When the owner turns down something that scored 9+, record why in
  `owner.md` and give it to the design director — it's the best signal of
  what a 9 means to the owner.

## When the team is stuck

Stop iterating and bring the owner in to collaborate when any of these
happens:

- **Concept phase:** three rounds without a 9 from the design director, or a
  round under 9 where the best score didn't go up.
- **Execution phase:** four rounds without meeting the full bar, or a round
  short of the bar that made no progress — the score didn't go up and the
  number of open blockers (failed jobs plus review blockers) didn't fall.
- **Either phase:** the owner turns down two 9s in a row — the director's
  sense of a 9 has drifted from the owner's. Turning down a set of concepts
  counts as one rejection, and this count doesn't reset when the owner
  gives new direction.

A round is one scoring pass. Round counts start over at each phase and
whenever the owner gives new direction.

There's usually a reason: the goal is unclear, two constraints conflict,
information is missing, or the idea can't work as framed. Ask the design
director and the designers what keeps blocking the bar and why. Then send
the owner a short note:

1. Where it stands: rounds run, best score, the recurring objection.
2. Why the team thinks it's stuck.
3. The specific questions the owner can answer, or the decision they can
   make, to unblock it.

This is a request for help, not a review: don't present sub-9 work as a
candidate for approval. If a picture helps explain a question, include it,
clearly labelled as not ready.

## Keeping your own context

Pass teammates file paths, not file contents, and don't read work in depth
yourself — use the `NEXT:` lines to run the jam, and skim `scores.md` and
the notes files. Keep your context for running the loop.

## Why it's set up this way

- The director and jobs checks exist because checking work only against the
  spec let bad work reach the owner.
- Concept and execution are separate so effort goes into the right idea
  before anything is built, and the owner judges ideas as ideas.
- The builder works from a written handoff because long, cluttered contexts
  make agents less reliable, and a builder told not to redesign keeps the
  approved concept intact.
