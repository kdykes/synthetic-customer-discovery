---
name: synthetic-customer-discovery
description: >
  Customer discovery with grounded synthetic personas. Plan interview studies, build
  evidence-grounded persona files, run synthetic discovery interviews against them, and
  synthesize transcripts (real or synthetic) into evidence-backed reports. Use when planning
  customer or user interviews, writing screeners or interview guides, building or refining
  personas or an ICP profile, pressure-testing positioning or pricing hypotheses before
  talking to real people, or synthesizing interview transcripts. Synthetic output is always
  framed as hypothesis, never as validation.
---

# Synthetic Customer Discovery

End-to-end customer discovery with the methodological craft of a professional research shop,
plus a synthetic-interview engine that runs on hand-built, grounded personas instead of a
one-line profile string.

## Design stance

- **Synthetic output is a hypothesis, never a verdict.** Every synthetic run is explicitly
  framed as a hypothesis generator. The required next step is validation against real
  participants. This is the documented mitigation for persona collapse, the failure mode
  where an LLM asked to play "a customer" flattens to the average internet idea of one.
- **Persona depth does the work.** Personas are structured artifacts grounded in specific lived
  episodes from real people the user has access to (themselves, customers, support tickets,
  sales calls), not demographic strings.
- **Local and transparent.** Interviews run inside the conversation against a readable persona
  file. No paid black-box backend. The user can see, version, and correct every persona.

## Routing

| Intent | Route |
|---|---|
| Plan a study, screener, or interview guide | [Route A: Plan](#route-a-plan) |
| Build or refine a persona | [Route B: Persona](#route-b-persona) |
| Run synthetic interviews against personas | [Route C: Simulate](#route-c-simulate) |
| Have transcripts (synthetic or real), need a report | [Route D: Synthesize](#route-d-synthesize) |

If the user's intent is ambiguous, ask one clarifying question.

### Route A: Plan
Create a research plan, screening questionnaire, interview guide, and a recruitment and
incentives plan.
**Do:** Follow `references/planner.md`. Incentive design is mandatory (Phase 3). Use a neutral
incentive, never free or early product access, for discovery.

### Route B: Persona
Build a new persona or refine an existing one.
**Do:** Follow `references/persona-builder.md`. Never hand the user the blank template;
interview them about a real person (or extract from their raw material: transcripts, tickets,
notes) and write the file for them, marking everything inferred with `[ASSUMED: confirm]`.
`personas/_TEMPLATE.md` defines the structure; `personas/example-mara-freelance-designer.md`
shows the level of specificity required (it is fictional; real personas must not be).

### Route C: Simulate
Run synthetic interviews: embody one or more personas and answer an interview guide in
character.
**Do:** Follow `run-synthetic-interview.md`.

### Route D: Synthesize
Turn transcripts into an evidence-backed report (themes, findings, opportunities).
**Do:** Follow `references/synthesis.md`. Hard rule: a theme supported only by synthetic
transcripts is a hypothesis, never a finding.

## Where artifacts live

The skill is methodology only. Write study artifacts into the user's project, not into the
skill directory. Suggested layout:

```
research/
  plan/            # Route A outputs: plan, screener, guide
  personas/        # Route B outputs: one file per persona
  synthetic-runs/  # Route C outputs: transcript + fidelity note, dated
  interviews/      # real-participant transcripts and notes (highest-grounding source)
  findings/        # Route D outputs: synthesis reports
```

If the user already has a research directory convention, follow theirs.

## Files

```
synthetic-customer-discovery/
  SKILL.md                       # this file
  run-synthetic-interview.md     # Route C, the persona interview runner
  personas/
    _TEMPLATE.md                 # persona structure (the core of the method)
    example-mara-freelance-designer.md  # fictional worked example
  references/
    planner.md                   # Route A: plan, screener, guide, recruitment, incentives
    persona-builder.md           # Route B: guided persona creation (interview / extract / draft)
    synthesis.md                 # Route D: transcripts to evidence-backed report
  examples/
    example-synthetic-run.md     # what a Route C output looks like
```
