# Synthesize Research Report

Turn raw transcripts (real, synthetic, or mixed) into an evidence-backed report: themes,
findings, and prioritized opportunities. Adapted and simplified from professional thematic
analysis practice for discovery-scale studies (roughly 3-20 transcripts inline; batch with
sub-agents beyond that).

## The evidence rule (non-negotiable)

Transcripts carry an evidence class, and the classes never blend:

| Class | Source | Can support a Finding? |
|---|---|---|
| **Real** | A real participant interview | Yes |
| **Synthetic-grounded** | Synthetic run against a `grounded` persona | No. Hypothesis only, but high-priority to test |
| **Synthetic-assumed** | Synthetic run against a `draft` or `partly-grounded` persona | No. Hypothesis only, low confidence |

A theme supported only by synthetic transcripts is a **hypothesis**, never a finding, no matter
how many synthetic runs agree. Synthetic agreement usually means the personas share assumptions,
not that the assumption is true. Label every claim in the report with its evidence class.

## Prerequisites

Gather before starting; ask the user for anything missing:

1. **Research objective.** The Big Q, and which decisions the research informs (from Route A
   if it exists).
2. **The interview guide** used, for deductive start-list codes and coverage checks.
3. **The transcripts**, each labeled real or synthetic (and for synthetic: which persona and
   its grounding status).

## Pipeline

### 1. Familiarize
Read every transcript fully. For each, write a short memo: who this is, the 3-5 strongest
moments (verbatim quotes), surprises, contradictions with other transcripts, emotional
high-water marks. No interpretation yet.

### 2. Code (hybrid)
- Build a start list of 10-25 provisional codes from the interview guide and objective.
- Sweep the transcripts; tag excerpts. Let new in-vivo codes emerge from the participants' own
  language and add them to the codebook as you go.
- Keep a light codebook: code, one-line definition, best exemplar quote.

### 3. Theme development
- Group codes into candidate themes. A theme answers part of the Big Q; a topic merely labels
  content. "Chasing feels like a relationship risk" is a theme; "invoicing" is a topic.
- Build a small frequency matrix (theme × participant) so prevalence claims are honest.
- Hunt for contradictions and outliers explicitly; the participant who breaks the pattern is
  signal, not noise.

### 4. Findings & opportunities
- **Findings:** claims supported by at least 2 *real* participants, each with verbatim evidence
  and a who-count ("4 of 6 participants"). State disconfirming evidence where it exists.
- **Hypotheses:** everything supported only by synthetic transcripts, ranked by how cheap they
  are to test in the next real interview round.
- **Opportunities:** outcome-oriented statements ("help [segment] [make progress] when
  [situation]"), not feature specs. Tie each to its findings.
- Pick a prioritization frame to fit the goal: severity × frequency for usability-type issues;
  importance vs. satisfaction for market gaps; impact/effort for sprint scoping.

### 5. Report
```markdown
# [Study]: Findings Report
## Objective & method
[Big Q, decisions informed, N real + N synthetic, dates, evidence rule stated]
## Themes
[Per theme: definition, prevalence, 2-3 verbatim quotes with participant id + evidence class]
## Findings (real-participant evidence only)
[Numbered, each with evidence, count, disconfirming notes]
## Hypotheses (synthetic-only, to validate)
[Numbered, each with which persona produced it and what would confirm or kill it]
## Opportunities
[Outcome-oriented, prioritized, tied to findings]
## Gaps & next round
[What the data can't answer; who to recruit next; guide changes]
```

## Quality gates (self-check before delivering)

- **Groundedness:** every claim traces to quoted data; findings have ≥2 real participants.
- **Heterogeneity:** variation and outliers are reported, not flattened into the dominant story.
- **Palpability:** evidence is concrete and specific; if a section has no verbatim quote, it's
  opinion, not analysis.
- **Class separation:** no synthetic quote appears under Findings; every quote is labeled.
- **Reflexivity:** analytic choices (codebook decisions, what got merged, what got dropped) are
  stated, not silent.
