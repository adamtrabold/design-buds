# The design loop

For anything new to design: a feature, a new look, a redesign. You, the
orchestrator, run it; teammates design and build. Two phases, concept then
execution. Don't mix them: concepts are not final UI, and nothing is built
until a concept is approved.

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
  scores.md          every score and objection, phase and gate, in order
  owner.md           the owner's answers, rejections and reasons
  handoff.md         the spec: what the approved concept is, what must not
                     change, every state it needs
  handoff-notes.md   the rationale behind it, and the director's and
                     owner's notes
  notes/<role>.md    notes for teammates that persist: notes/ux.md,
                     notes/ui.md, notes/director-phase.md, notes/builder.md
```

## Keeping teammates going

- **Keep the same agent** while it's on the same work, across phases, until
  its context gets heavy. Continue it by its id or name if the session
  supports that; otherwise start a fresh one from its notes file.
- **Fresh every round, no notes:** the gate director, the UX job checker and
  the reviewer. Their value is that they haven't seen the work develop.
- **Every persisting teammate updates its notes file at the end of each
  round**: where things stand, decisions and why, scores and objections,
  open questions, what comes next. If an agent can't be continued, or its
  context gets heavy, a fresh one starts from that note — so the note is
  never more than a round old. Make it thorough. The same goes for you.

## Before the first round

If the product has no brand, visual reference or design system yet, the
first concept round is about setting that direction. The design director
asks the owner the questions it needs to establish the foundation first, and
the owner is told that early scores are provisional.

## Fidelity

Make each piece of work at the fidelity the feedback needs. Concepts can be
words, pictures, diagrams, or a prototype if the idea only shows when you
use it; execution is the real thing. Don't go to full polish when a sketch
answers the question — and don't hold back when the work needs it. Never
trade away quality to save cost.

## Concept phase — deciding what it should be

1. **Jam.** The product designers and the phase design director jam in
   `jam.md`, one turn at a time. Each turn, a teammate reads the file and
   adds to it — new ideas, sharper versions of others' ideas, combinations —
   then ends its reply with `NEXT: <role> — <why>`.
   - **The product designer (UX focus) goes first,** so it writes the
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
2. **Jobs check.** The product designer (UX focus) writes `jobs.md` from the
   jam. Send it to the owner in one short message: "these are the jobs —
   anything wrong or missing?" Don't wait for the answer: carry on, and fold
   it in when it arrives.
3. **Concepts.** The product designer (UI focus) alone picks from the jam
   and makes 2–4 distinct concepts against `jobs.md`, saying which
   directions each draws on and why. One designer decides — no design by
   committee.
4. **Score.** The phase design director scores all of the round's concepts
   in one pass, 1–10.
5. Concepts under 9 go back: improve them or replace them. Iterate until at
   least one scores 9 or more, or the team is stuck (below).
6. **Jobs coverage.** The product designer (UX focus) checks each 9+ concept
   against `jobs.md`. A concept that leaves a job unsupported goes back.
7. **Gate.** A fresh gate design director scores the remaining 9+ concepts.
   The owner sees only concepts that pass the gate, each with its score and
   the gate director's reasoning. The owner approves one, or sends the team
   back.
8. **Handoff.** The product designer (UI focus) writes `handoff.md` (the
   spec) and `handoff-notes.md` (the rationale and notes) for the approved
   concept — what each covers: `roles/product-designer-ui.md`. The product
   designer (UX focus) checks the jobs and flows in `handoff.md`. The
   builder can't see this conversation; the handoff is everything it knows.

## Execution phase — making the approved concept real

1. A builder builds the approved concept from `handoff.md` and
   `handoff-notes.md`.
2. Gaps or deviations the builder flags go to the designers who made the
   concept (or fresh designers of the same focus, starting from their notes
   and the handoff). If answering one would change the concept itself, it
   goes to the owner as a decision question — what changed, the options,
   the team's recommendation — not as work to approve. A builder that stops
   on a gap saves its partial work so the build continues from it.
3. Three checks run on the build at the same time:
   - the phase design director scores it 1–10 against `handoff.md`;
   - a fresh product designer (UX focus) walks every job in `jobs.md` on it;
   - a reviewer checks that it works and meets the project's standards.
4. **The bar** is all three: a 9 or more, every job passing, a clean review.
   Short of it, the builder fixes everything found in one batch, then the
   checks run again. Repeat until the bar is met, or the team is stuck.
5. **Gate.** A fresh gate design director scores it. At 9+, the owner sees
   the finished work; on the owner's "yes", it lands under the project's
   rules.

## Quality bar

The design director has the final say on quality before the owner. Every
concept and every execution gets a score from 1 to 10, where 9 means "I
would defend this to the owner as is". **The owner never sees anything that
scored under 9.** Concept and execution are scored separately: a polished
execution of a weak concept is still a weak concept.

- **Phase director** — stays with the work, scores its rounds and keeps its
  scoring history, so scores are consistent. It joins the jam, so it scores
  concepts that draw on directions it helped shape; the gate exists to
  correct for that. Beyond the jam, it doesn't get the designers' notes or
  `handoff-notes.md`. Each round it says whether the work really changed.
- **Gate director** — fresh every round, never saw the work develop, isn't
  told who proposed what. It gets the concepts or the build plus
  `handoff.md`, the owner's words and direction, `owner.md`, and any
  earlier gate's objections — never `handoff-notes.md`, the phase
  director's scores or anyone's notes. It judges the work on its own.
  - If, and only if, it can't make a call without knowing why something was
    done, it stops and returns `NEED REASONING: <question>`. You get the
    answer from the relevant teammate, then continue the **same** gate
    agent with only that answer. It judges the reasoning on its logic.
  - If it scores under 9, the work goes back to the phase loop: the gate's
    objections go to the phase director and the designers, and to the next
    gate director.

You enforce this:

- Nothing goes to the owner without a gate score of 9 or more, except the
  decision questions and stuck notes described here.
- Score again only after the work has really changed. Keep every score in
  `scores.md`; never discard one to get a better one.
- When the owner turns down something that scored 9+, record why in
  `owner.md` and give it to every design director after that — it's the
  best signal of what a 9 means to the owner.

## When the team is stuck

Stop iterating and bring the owner in to collaborate when any of these
happens:

- **Concept phase:** three rounds without a 9 from the phase director, or a
  round under 9 where the best score didn't go up.
- **Execution phase:** four rounds without meeting the full bar, or a round
  short of the bar where the score didn't go up.
- **Either phase:** two gate rejections in a row.

A round is one scoring pass; a gate rejection sends the work back into the
phase loop and its next pass counts as a round. Counts start over at each
phase and whenever the owner gives new direction.

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

- The director and UX checks exist because checking work only against the
  spec let bad work reach the owner.
- Concept and execution are separate so effort goes into the right idea
  before anything is built, and the owner judges ideas as ideas.
- The builder works from a written handoff because long, cluttered contexts
  make agents less reliable, and a builder told not to redesign keeps the
  approved concept intact.
