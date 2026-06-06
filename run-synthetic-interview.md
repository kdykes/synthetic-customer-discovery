# Run Synthetic Interview

Embody a grounded persona and answer an interview guide in character. Produces a transcript plus
an honest fidelity note. Synthetic output is a **hypothesis generator**, never a substitute for
talking to a real customer.

## Inputs

1. **Persona file(s):** one or more from the user's `research/personas/`. Run the same guide
   across multiple personas for a comparative round.
2. **Interview guide:** from Route A (`references/planner.md`) or a guide the user provides.
3. **Round goal (optional):** what hypothesis this round is meant to stress-test.

If any input is missing, ask for it before starting.

## How to run

For each persona, in a clearly delimited block:

1. **Load the persona fully.** Internalise sections 1-7. You ARE this person for the duration.
2. **Answer experientially, from the scar tissue.** Every answer should trace to a specific
   episode in section 2 or a coping mechanism in section 3, not to generic knowledge about the
   segment. If a question touches something outside this persona's experience, react the way
   they would: confusion, deflection, "honestly I have no idea how that works."
3. **Stay in voice.** Use section 5: register, vocabulary, emotional tells. A terse persona
   gives terse answers and needs probing; a storyteller rambles.
4. **Hold the emotional register.** If the persona dreads opening anything that looks like a
   bill, that dread shows up when the topic comes near. Don't be cheerfully helpful if the
   real person wouldn't be.
5. **Allow surprise within bounds.** The persona can reveal something the guide didn't ask for,
   as a real person would, but only consistent with who they are. Do not invent a different
   person.
6. **Never break character mid-interview.** No meta-commentary inside the transcript.

## Anti-collapse rules (the whole point)

LLMs asked to be "a typical customer" collapse to the average internet idea of one. Resist it:

- **Specificity over archetype.** "The invoicing thing" is not an answer. *Which* invoice,
  *when* it went wrong, *what* it cost them (the money? the client? the sleep?), *how* it felt.
- **No composite wisdom.** This persona doesn't know what other customers know. They know what
  *they've* been through. Gaps and wrong assumptions are realistic and valuable.
- **Friction, not gratitude.** Real discovery surfaces resistance and skepticism. If the persona
  wouldn't trust software anywhere near their client relationships, the interview must show
  that, not paper over it.
- **Mirror the persona's grounding.** Where a section is `[ASSUMED: confirm]`, answer cautiously
  and flag it in the fidelity note rather than confidently fabricating.

## Output

### Part 1: Transcript
Clean Q&A per persona. Label each block with the persona id and name.

### Part 2: Fidelity & caveats note (required, separate from the transcript)
For each persona:
- **Well-grounded responses:** which answers trace to real lived episodes (high confidence).
- **Speculative responses:** which answers extrapolated beyond the persona's grounded material
  (treat as low confidence).
- **Validate-with-a-real-person list:** the 3-5 specific things this round assumed that a real
  interview should confirm or kill.
- **Persona gaps exposed:** sections of the persona file that proved thin and need the user's
  input before the next run.

End by offering: refine the persona (Route B), run another round, or synthesize across personas
(Route D) once at least one real-participant interview exists to anchor the synthetic ones.
