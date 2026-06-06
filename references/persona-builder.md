# Build a Persona

Get the user from "I know my customer" to a grounded persona file in about ten minutes,
without them ever staring at a blank template. You own the structure (`personas/_TEMPLATE.md`);
they only have to talk, or paste.

## First, pick the path

Ask one question: **"Who is this persona based on, and what do you have on them?"** Route by
the answer:

| They have | Path |
|---|---|
| A real person they know well (themselves, a customer, a friend in the segment) | **Interview mode** |
| Raw material: sales-call transcripts, support tickets, interview notes, community threads | **Extraction mode** |
| Only beliefs and hunches | **Assumption draft** |

## The anti-composite rule (applies to every path)

One persona = one real person wherever possible. Blending three customers into one "typical"
persona recreates the exact collapse this skill exists to prevent. If the source material is
aggregated (a ticket queue, a forum), the output is an archetype: cap its grounding status at
`partly-grounded` and say so in the file.

---

## Interview mode (the default)

Interview the user about the real person. One question at a time, conversational, 8-12
questions total. Ten minutes is the budget; this is an excavation, not an interrogation.

Mine in this order; adapt wording to their domain:

1. **Anchor:** "Who are we building? Name or initials, and how do you know them?"
2. **Situation, fast:** role, how long they've been in the situation, what binds them
   (contract, visa, certification, cash). Two or three quick questions, not a form read aloud.
3. **Episodes (spend most of the time here).** "Tell me about a specific time this problem
   actually bit them. What happened, when, what did it cost?" Push past categories to the
   story, same craft as a real interview: "Which invoice? How did they find out? What did
   they do that night?" Get 2-3 episodes minimum. An episode without a cost (money, time,
   sleep, pride) isn't done yet.
4. **Coping today:** "Walk me through what they do about it now, before any product exists."
5. **Trust line:** "What would they never let software do here? What would make them delete
   it on day one?"
6. **Voice:** "Say one line the way they'd say it. Something you've actually heard."
7. **Stop check:** offer to stop at ten minutes. "I have enough for a working persona. Keep
   going on [thinnest area], or draft it now?"

Rules while interviewing:
- One question per turn. No multi-part question stacks.
- If they generalize ("she's always stressed about money"), redirect to an incident once,
  then move on. Don't grind.
- If they don't know something, that's an answer. Mark the gap; never fill it with a guess
  silently.

## Extraction mode

They paste or point you at raw material.

1. Confirm scope: is this material from or about **one** person? If not, apply the
   anti-composite rule.
2. Pull episodes with their specifics intact (amounts, dates, named counterparty types).
   Prefer verbatim quotes; real language goes straight into the Voice section.
3. Where the material is silent (psychology, trust line), either ask the user 2-3 interview-mode
   questions to close the biggest gaps, or mark the section `[ASSUMED: confirm]`. Offer both.

## Assumption draft

They have no real person and no material, only beliefs. Build it anyway, honestly:

- Take their hunches section by section, fast.
- Mark **every** substantive claim `[ASSUMED: confirm]`. Status: `draft`.
- Tell them plainly what it's for: a draft persona can't validate anything. It exposes what
  they don't know and gives them a recruiting target. Their next step is the planner
  (`references/planner.md`), which includes recruitment; the first real interview upgrades
  this file.

---

## Writing the file

Use `personas/_TEMPLATE.md` structure exactly. Then the honesty pass, which is the whole
point of the builder:

- Everything the user told you or the material showed: attribute it in "Grounded in".
- Everything you inferred to make sections read complete: mark `[ASSUMED: confirm]`. When in
  doubt, mark it.
- Set grounding status honestly: `grounded` only for a specific real person with firsthand
  episodes; `partly-grounded` for secondhand or archetype material; `draft` for assumption
  work.
- Fill the validation ledger (section 8) with the 3-5 things a real interview should confirm
  or kill, ranked.
- Suggest a save path in the user's project: `research/personas/persona-NN-name.md`.

Close by showing the user two things only: the grounding status with the two or three
thinnest sections, and the single next action (run a synthetic round against it, or book the
real interview that upgrades it).
