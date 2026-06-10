# Frontend Design Power Skill

A comprehensive frontend design skill for AI coding agents (OpenCode, Claude Code, Codex, etc.).

## What it does

Instead of "build me a landing page" producing the same generic AI template every time, this skill gives the agent:

- **30 visual styles** to choose from (Brutalist, Swiss Modern, Deep Tech, Editorial Luxury...)
- **Page architecture variation** — 7 hero types, 6 nav types, forced section shuffling
- **WCAG contrast enforcement** — specific hex values that fail, color role matrix
- **20 banned AI patterns** — cream backgrounds, purple gradients, glassmorphism defaults, tiny uppercase eyebrows...
- **Button quality checklist** — no line-height:1 text shift
- **Card grid consistency rules** — 4 cards = 2×2, never 3+1
- **Animation decision framework** — frequency-based, spring physics, custom cubic-bezier curves
- **Dark mode contrast traps** — no brown/beige text on dark
- **Responsive design** — mobile-first breakpoints, dvh units, 4-resolution test checklist

## Origin

Built by analyzing 109 skills from [ui-skills.com](https://www.ui-skills.com/skills/), reading 9 of them line by line from their GitHub repos (baseline-ui, impeccable, make-interfaces-feel-better, fixing-accessibility, fixing-motion-performance, taste-skill, soft-skill, brutalist-skill, emil-design-eng). The remaining 100 were framework-specific or redundant.

Runs on **DeepSeek V4 Pro** inside **OpenCode CLI**.

## Install

```bash
# OpenCode
cp SKILL.md ~/.opencode/skills/frontend-design-power/SKILL.md

# Claude Code
cp SKILL.md ~/.claude/skills/frontend-design-power/SKILL.md
```

## Results

Three consecutive subagent tests with clean context, same skill, different briefs:

| Project | Style | Hero | Nav | Motion |
|---------|-------|------|-----|--------|
| Electronic components supplier | Clean SaaS #8 | Centered text | Top fixed | 3 |
| Vinyl record shop | Brutalist #12 | Type-only | Hamburger | 3 |
| Dance academy | Deep Tech OLED #2 | Animated blobs | Floating pill | 8-9 |

All three completely different page architectures. Before the skill they would have been identical templates.

## License

MIT
