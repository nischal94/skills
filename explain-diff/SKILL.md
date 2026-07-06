---
name: explain-diff
description: Use when the user asks for a rich explanation of a code change, diff, branch, commit, or PR — in any project. Produces a self-contained HTML explainer published as a Claude Code Artifact, ending in a five-question interactive quiz. Derived from Geoffrey Litt's explain-diff skill.
---

# Explain Diff

Produce a rich, interactive explanation of the specified code change and
publish it as an Artifact. The purpose is paying down cognitive debt:
the human must be able to hold the theory of this change, not just see
that checks went green. The quiz at the end is a speed regulator — for
load-bearing changes, the human should pass it before merging.

## Ground truth first

Read the actual diff (`git show <sha>` / `gh pr diff <n>`) and the real
surrounding files before writing anything. Never explain from memory.
If the project has a spec, design doc, ADRs, or a decision/invariants
ledger, quote the relevant passages verbatim and name them; if not,
derive background from the surrounding code and README.

## Sections, in this order

1. **Background** — Teach the existing system relevant to this change
   before touching the diff. Explore the surrounding code and any
   project contract documents. Write a deep background a newcomer could
   follow (mark it skippable for experts), then a narrow background
   specific to this change.
2. **Intuition** — The essence before any code. State the goal in one
   sentence. Use concrete toy examples with realistic data. Use figures
   liberally: pick a SMALL number of diagram families and reuse them
   across cases (e.g., one data-flow diagram with example values, one
   before/after). HTML/CSS diagrams only — never ASCII art.
3. **Code walkthrough (the literate diff)** — Walk the changes in a
   sensible narrative order, never alphabetical file order. Embed the
   important hunks as snippets with surrounding prose. For tests,
   explain what failure each key assertion rules out — and when a test
   has a positive control, say why it exists.
4. **Quiz** — Five interactive multiple-choice questions, medium
   difficulty: answerable only by someone who actually understood the
   change; no gotchas, no variable-name trivia. Clicking an option
   reveals correct/incorrect plus a short explanation. Keep a running
   score. State the rule beneath the quiz: don't merge a load-bearing
   change until you can pass.

## Format rules

- One self-contained HTML file: inline CSS + JS, zero external
  resources (the Artifact CSP blocks them anyway). Table of contents at
  the top; one long page with section headers, no tabs. Responsive
  enough to read on a phone.
- Write the file to the session scratchpad as
  `YYYY-MM-DD-explain-<slug>.html`, then publish with the Artifact tool
  (favicon 🔍, keep it stable across redeploys of the same explainer). If the Artifact tool is unavailable in your environment, write the HTML file locally and open it in a browser instead.
- Prose standard: the clarity and flow of Martin Kleppmann; classic
  style; smooth transitions between sections.
- Code blocks use `<pre>`; any custom-styled block MUST have
  `white-space: pre-wrap`. Before publishing, scan every code block in
  the source and confirm it.
- Use callouts for key definitions, invariants, and edge cases.

## Credit

Derived from Geoffrey Litt's `explain-diff` skill
(gist `a29df1b5f9865506e8952488eac3d524`); the Background → Intuition →
Literate diff → Quiz structure and the quiz-as-speed-regulator idea are
his. Adapted: Artifact output instead of local files/Notion, contract-
document grounding, and the merge-gate framing.
