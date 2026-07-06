# skills

A collection of Claude Code skills — installable, zero dependencies, built for real workflows.

Skills are markdown files that Claude reads at invocation time. They give Claude specialized knowledge and step-by-step instructions for specific tasks — without burning tokens on repeated setup.

## How skills work

When you invoke a skill, Claude loads a focused instruction set (<5k tokens) instead of relying on your system prompt or project context. Skills use a three-tier model:
1. ~100 token metadata scan (name + description) — always loaded
2. Full SKILL.md — loaded on invocation
3. Referenced sub-files — loaded on demand

## Install

**Claude Code (recommended):**
```
/plugin marketplace add nischal94/skills
```

**Manual:**
```bash
git clone https://github.com/nischal94/skills.git ~/.claude/skills/skills
```

## Skills

### Understanding & workflow

These three operationalize the "finding your unknowns" way of working: map what
you don't know before implementing, and prove you understand what shipped
before merging.

| Skill | Description |
|-------|-------------|
| [blindspot](./blindspot/) | Pre-implementation unknown-unknowns pass. Codebase mode produces blindspot cards, each with a copyable prompt-fix; domain mode teaches you the vocabulary until you can specify what you want. Ends with a four-quadrant map and an assembled implementation prompt. |
| [explain-diff](./explain-diff/) | Rich HTML explainer for any diff, commit, or PR: background → intuition → literate diff → a five-question quiz. The rule that makes it matter: don't merge a load-bearing change until you pass the quiz fully. |
| [pitch](./pitch/) | One demo-led buy-in doc: the working thing first, then what/why, evidence, every reviewer objection pre-answered, and the exact ask with named sign-offs. |

### Creation & design

| Skill | Description |
|-------|-------------|
| [html-to-image](./html-to-image/) | Convert HTML files to high-resolution PNG or JPEG using Puppeteer and system Chrome. No browser download required. |
| [design-eng](./design-eng/) | UI polish, component design, animation decisions, and the invisible details that make software feel great. |
| [product-explainer](./product-explainer/) | Story-driven HTML slide deck that explains a product to a non-technical audience — grounded in the real docs and codebase, no invented features. |

## Requirements

- [Claude Code](https://claude.ai/code)
- The understanding & workflow skills are dependency-free; they publish HTML via the Artifact tool when available, or write a local HTML file otherwise
- `html-to-image` needs Node.js + npm and Google Chrome at `/Applications/Google Chrome.app` (macOS paths)

## Credits

- **explain-diff** derives from [Geoffrey Litt's explain-diff skill](https://gist.github.com/geoffreylitt/a29df1b5f9865506e8952488eac3d524) — the background → intuition → literate diff → quiz structure and the quiz-as-speed-regulator idea are his.
- **blindspot** and **pitch** implement patterns from [Thariq Shihipar's "Finding Your Unknowns"](https://thariqs.github.io/html-effectiveness/unknowns/) framework.

## License

MIT
