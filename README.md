# Synthetic Customer Discovery

A Claude skill for customer discovery: plan real interview studies, build grounded synthetic
personas, interview them, and synthesize what you learn into evidence-backed reports.

Built to be honest about what synthetic research can and cannot tell you.

**No API keys. No backend. No accounts.** Plain markdown files that run inside Claude. You can
read, version, and correct every persona, and nothing leaves your Claude session.

## The problem with synthetic users

Ask an LLM to "act like one of my customers" and it collapses to the average internet idea of
one: agreeable, articulate, and suspiciously enthusiastic about your product. Teams run twenty
of these "interviews," hear what they hoped to hear, and call it validation.

That isn't research. It's confident fiction.

The fix isn't better prompting. It's structure: personas deep enough that the model has
something real to draw on, interview rules that force friction instead of flattery, and outputs
that tell you exactly which answers to trust and which to verify with a human.

## How this skill keeps you honest

1. **Personas are grounded artifacts, not prompt strings.** Each one is a structured file built
   from real episodes from real people you have access to: yourself, your customers, support
   tickets, sales calls. Every unverified claim is marked `[ASSUMED: confirm]`.
2. **Hypothesis, never verdict.** Every synthetic output is labeled as a hypothesis. The
   synthesis route hard-codes it: a theme supported only by synthetic transcripts can never be
   a finding, no matter how many runs agree.
3. **Anti-collapse interview rules.** Specificity over archetype. No composite wisdom. Friction,
   not gratitude. If the persona wouldn't trust your product, the interview has to show it.
4. **A mandatory fidelity note on every run.** Which answers trace to real grounded material,
   which are speculation, and the 3-5 specific things a real interview should confirm or kill.
5. **A validation ledger in every persona.** What's real, what's assumed, and what to confirm
   next, so the skill keeps pushing you toward real interviews instead of away from them.

## Install

Claude Code, personal (available in all projects):

```bash
git clone https://github.com/kdykes/synthetic-customer-discovery.git ~/.claude/skills/synthetic-customer-discovery
```

Or per-project: clone into `.claude/skills/` inside your repo.

Built for Claude Code (CLI, desktop, or web). The files are plain markdown, so the method
ports anywhere an LLM can read a file.

To see it work right now, before you've built anything:

> Run a synthetic interview against the Mara example persona, asking about chasing overdue invoices.

That first run works out of the box (Mara ships with the skill, clearly labeled as fiction).
Your second run should be against a persona you've grounded in someone real.

## Use

Four routes. Just describe what you need; the skill routes itself.

| You say something like | Route | What you get |
|---|---|---|
| "Plan a discovery study on [topic]" | **Plan** | Research plan, screener, interview guide, recruitment & incentives plan |
| "Build a persona for my ICP" | **Persona** | A ten-minute guided interview about a real customer; the skill writes the grounded persona file |
| "Run a synthetic interview round against persona 01" | **Simulate** | In-character transcript + fidelity note |
| "Synthesize these transcripts" | **Synthesize** | Report: findings (real evidence), hypotheses (synthetic), opportunities |

Your study artifacts live in your project (suggested: a `research/` directory), not in the
skill. The skill is methodology only.

You never fill in the persona template by hand. Say "build a persona" and the skill
interviews you about a real customer, one question at a time, for about ten minutes. Or paste
raw material (sales calls, support tickets, interview notes) and it extracts. Either way it
writes the file, marks everything it had to assume with `[ASSUMED: confirm]`, and tells you
the two or three thinnest sections. No real customer yet? It will still build you a draft
from your hunches, with every claim flagged, so you can see exactly what you don't know.

## What a run looks like

A taste, from the demo persona:

> **Q: You said the money isn't the worst part. Oh?**
>
> I mean, it matters, rent matters. But the silence is the thing. You send the invoice and
> it's just... nothing. I check my banking app like it's a slot machine. The work part of
> freelancing I can do. It's the part where I become a collections agency with no leverage
> that nobody warned me about.

And from the fidelity note that every run must end with:

> **Speculative responses:** the "day 15 / day 30 / day 45" cadence; the persona file says
> nothing about what schedule she'd accept.

The full run is at [`examples/example-synthetic-run.md`](examples/example-synthetic-run.md):
an abridged transcript, followed by the fidelity note that tells you what to trust. The demo
persona itself
([`personas/example-mara-freelance-designer.md`](personas/example-mara-freelance-designer.md))
shows the level of specificity a grounded persona needs: episodes with amounts, dates, and
emotional beats, not "millennial who values convenience."

## Where this fits, and where it doesn't

Good uses:

- Pressure-testing an interview guide before you spend real participants on it
- Sharpening hypotheses so your real interviews start smarter
- Comparative rounds across segments to decide who to recruit first
- Forcing yourself to write down what you actually know about your customer versus what you
  assume

Not what this is for:

- Validating anything. Synthetic agreement is not evidence.
- Pricing decisions. Synthetic willingness-to-pay is fiction with a number in it.
- Replacing real interviews. The skill's own output keeps telling you this; listen to it.

The workflow this skill wants you to run: synthetic round → sharper guide and hypotheses →
real interviews (8-12 per segment) → synthesis where only real data can become findings.

## Why this exists

We built this to run discovery for a new product of our own. The structure worked, so we
stripped out everything specific to us and published the method. The persona-grounding layer,
anti-collapse rules, and evidence-class separation are the parts we'd want every team using
synthetic research to have.

The planning and synthesis methodology adapts the excellent open-source
[user-research skill by Cookiy AI](https://github.com/cookiy-ai/user-research-skill) (MIT). The grounded-persona
engine and honesty guardrails are what this repo adds.

## License

MIT. See [LICENSE](LICENSE).
