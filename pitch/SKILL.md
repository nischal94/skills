---
name: pitch
description: Use when the user needs a buy-in or approval document for proposed or shipped work — "package this for review", "make the pitch", "one doc I can share for sign-off". Assembles prototype + spec/plan + implementation notes + diff into a single demo-led HTML artifact with objections pre-answered. From Thariq Shihipar's Finding Your Unknowns framework.
---

# Pitch (the buy-in doc)

One document that gets the work approved. The governing insight:
reviewers start with the same unknowns the author did — answer them up
front, before they're asked.

## Gather what exists

Collect this session's (or the named work's) real materials: prototype
artifacts, the spec or plan, the implementation-notes deviations log,
the diff or PR, test/CI evidence, the explainer if one exists. The
pitch assembles; it does not invent.

## Structure, in this order

1. **The demo, first.** Lead with the thing itself working — an
   animated or interactive rendition of the flow (CSS/JS animation,
   a stepped walkthrough with real data, an embedded live mock).
   Nobody reads paragraph one of a pitch; everybody watches the demo.
2. **What & why, one screen.** The problem, the change, the outcome —
   tight enough to read while deciding whether to keep reading.
3. **Evidence.** What was verified and how: tests, checks, invariants
   pinned, incidents handled. Claims link to their proof.
4. **Objections, pre-answered.** Anticipate every question a reviewer
   or expert would raise — including the unknowns the author started
   with and the common failure points of this kind of change. Each
   objection gets a direct answer with evidence. This section is what
   converts "looks nice" into approval.
5. **The ask.** Exactly what decision is requested, and from whom —
   named sign-offs, not "thoughts?".

## Format

- Self-contained HTML → scratchpad as `YYYY-MM-DD-pitch-<slug>.html` →
  published with the Artifact tool (favicon 📣, stable per pitch). If the Artifact tool is unavailable in your environment, write the HTML file locally and open it in a browser instead.
- Include copy-ready exports where useful: a short blurb for chat/PR
  comment, the decision summary — each behind a copy button.
- Mobile-readable; demo degrades gracefully.

## Credit

From Thariq Shihipar's "Finding Your Unknowns" (the buy-in doc) and
"The Unreasonable Effectiveness of HTML" (demo-led one-doc, copy-back
exports), adapted for Artifact output.
