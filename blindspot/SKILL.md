---
name: blindspot
description: Use when starting work in an unfamiliar area of a codebase or an unfamiliar domain, or when the user says "blindspot pass", "unknown unknowns", or "teach me X so I can prompt better". Produces an HTML artifact that maps the user's unknowns, with copyable prompt-fixes. From Thariq Shihipar's Finding Your Unknowns framework.
---

# Blindspot pass

Surface the user's unknown unknowns BEFORE work begins, so they can
prompt well instead of discovering potholes mid-implementation. The map
is not the territory; this skill charts the gap.

## Starting point first — always

Before anything else, establish (ask ONE question if not provided):
who the user is, what they already know about this problem/codebase/
domain, and what they're trying to achieve. The whole output calibrates
on this — a blindspot pass for a newcomer and an expert are different
documents.

## Two modes — pick by what is unfamiliar

### Mode A — codebase blindspot pass
The user must work in code they don't know.
1. Explore the target area for real: the modules, their seams, the
   contract docs (spec, ADRs, invariants ledger, README), git history
   for recent churn and past incidents.
2. Produce **blindspot cards** — one per unknown-unknown. Each card:
   - the blindspot, named plainly
   - why it bites (the concrete pothole: what goes wrong if unaware)
   - evidence (file paths, spec sections, commits)
   - a **copyable prompt-fix**: the sentence(s) to add to the
     implementation prompt that neutralize this blindspot
3. End with the **four-quadrant map** of the task as it now stands:
   known knowns (goes in the prompt), known unknowns (questions to
   answer next — route to an interview), unknown knowns (things the
   user will only recognize on sight — route to prototypes/variants),
   and residual risk.
4. Finish with an **assembled improved prompt** combining all
   prompt-fixes, behind one copy button.

### Mode B — teach me my unknowns (domain)
The user lacks the vocabulary to specify what they want (color grading,
auth flows, typography, backpressure...).
1. Build a **vocabulary ladder**: from the vague words the user has
   toward the precise terms of the domain. Each rung: the term, a
   plain-language definition, what varying it looks like (before/after
   examples — interactive sliders/toggles where the concept is visual),
   and how to use it in a prompt.
2. Exit criterion, stated on the page: the user can now describe what
   they want precisely enough to react to and direct the work.

## Format

- Self-contained HTML (inline CSS/JS, no external resources), written
  to the session scratchpad as `YYYY-MM-DD-blindspot-<slug>.html`,
  published with the Artifact tool (favicon 🧭, stable per pass). If the Artifact tool is unavailable in your environment, write the HTML file locally and open it in a browser instead.
- Cards and ladders over prose walls; every copyable element gets a
  copy button. HTML/CSS diagrams, never ASCII.
- Ground everything in real exploration done this session — no
  blindspots from memory.

## Credit

From Thariq Shihipar's "A Field Guide to Fable: Finding Your Unknowns"
(blindspot pass + teach-me-my-unknowns artifacts), adapted for Artifact
output and contract-document grounding.
