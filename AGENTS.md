# AGENTS.md

This file is for AI coding agents (Codex, Cursor, Copilot, Gemini CLI, and others) that read `AGENTS.md`. Claude Code reads `CLAUDE.md` in this folder, which holds the same rules in full. **Read `CLAUDE.md` first**; this file only maps the layout.

## What this repository is

Source material and an onboarding procedure for building a **personalized presentation-deck skill** on the user's machine. It is not a finished plugin. The resulting skill is a *converter*: it takes prepared material (a conclusion plus supporting evidence) and turns it into 16:9 HTML slides rendered to PDF. The agent collects the user's own material (audience, past decks, personal rules, writing samples), merges it with the cited guides here, and writes a self-contained skill folder to the user's agent config directory. After that, this repository is not needed to make decks.

No executable code; markdown only.

## Read before working

1. `CLAUDE.md` — onboarding behavior, absolute rules, priority order
2. `onboarding/세팅_절차.md` — the 7-step setup procedure (collect → profile → generate skill)
3. `guides/01_PT자료_가이드.md` — slide structure (Assertion-Evidence), slide vs. handout, spoken vs. written register
4. `guides/02_디자인_가이드.md` — spacing, color, typography, tokens, anti-patterns
5. `guides/03_글쓰기_가이드.md` — sentence rules, audience layer, 71 Korean AI-writing patterns
6. `references/README.md` — links to every cited source, plus four public design-system digests (Ant Design, shadcn/ui, iOS 26, Backstage)

## What gets generated (Claude Code layout)

```
~/.claude/skills/pt-deck/
├─ SKILL.md      from blueprints/SKILL_PT제작.md, with the user's defaults filled in
├─ review.md     from blueprints/SKILL_PT검수.md
├─ profile.md    the user's profile
└─ guides/       copy of guides/
~/.claude/commands/PT제작.md · PT검수.md · PT설정.md   from blueprints/commands/
```

Other agents: place the same files wherever your tool loads reusable instructions (for example a project rules directory), and adapt the three command files to your tool's slash-command or prompt-template format. The procedures themselves are plain markdown and tool-agnostic.

## Priority when rules conflict

1. The user's direct instruction for this task
2. The user's profile (personal rules, writing baseline, audience)
3. `guides/`
4. Any external skill or plugin

## Hard rules (summary; full text in CLAUDE.md)

- Do not invent methodology. Rules not in `guides/` are neither applied nor flagged.
- Get the assertion list approved before building slides.
- Stay within the requested scope.
- Never solve a "needs more context" problem with small grey captions.
- Never show a number without its label and traceable source.
- State prohibitions before style instructions.
- Never modify or delete files the user placed in `my/`, nor `guides/` and `blueprints/` in this repository.

## Trust

See `TRUST.md` for verifiable claims (no executable code, every rule cited, private folder gitignored) and a suggested way to present them to the user.
