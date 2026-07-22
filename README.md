# claude-learner-hub

A personal learning repository for exploring Claude Code — each project isolates one capability so the effect is easy to see.


## Projects

### SugarAndBloomProject — Skills comparison

A bakery landing page built twice using the same prompt to compare Claude Code output with and without a skill.

| Version | Folder | Skill Used |
|---|---|---|
| v1 — No skill | `SugarAndBloomProject/WithoutSkill/` | None |
| v2 — With skill | `SugarAndBloomProject/WithFrontEndDesignSkill/` | `frontend-design` (anthropics/skills) |

Key takeaway: the `frontend-design` skill produced noticeably more polished visual output from an identical prompt, demonstrating how skills extend Claude Code's defaults without changing the underlying request.

Open in a browser:

```bash
# SugarAndBloomProject comparison
open SugarAndBloomProject/WithoutSkill/sugar_and_bloom.html
open SugarAndBloomProject/WithFrontEndDesignSkill/sugar_and_bloom_v2.html

# CalorieTracker application
open CalorieTracker/index.html
```

### BrandedAssets — Custom slash command for brand consistency

Demonstrates a project-scoped custom command that pins brand guidelines so every generated asset stays on-brand without repeating the spec in each prompt.

- `BrandedAssets/.claude/commands/brand-identity.md` — the `/brand-identity` command definition (colors, typography, tone, vocabulary, closing phrases) for the fictional *Kai Lens Studio* brand.
- `BrandedAssets/priya-james-followup-email.html` — a follow-up email generated against those guidelines, showing Deep Navy / Warm Sand / Antique Gold palette and Cormorant Garamond + Nunito Sans typography applied consistently.

Key takeaway: putting brand rules in a slash command turns "please remember our brand" into a repeatable, single-invocation instruction — useful for teams producing repeated marketing collateral.

### CalorieTracker — Interactive web application

A full-featured calorie tracking web application built with HTML, CSS, and JavaScript. Demonstrates building functional, stateful applications with Claude Code.

- `CalorieTracker/index.html` — single-file interactive app with meal logging, daily tracking, and calorie calculations
- Features: add/remove meals, persistent session data, responsive design

Key takeaway: Claude can generate complete interactive applications as single HTML files with embedded logic and styling, ready to use immediately.


## Claude Code Plugins & Skills — Quick Primer

Claude Code can be extended in two main ways:

- **Skills** — packaged instructions (and optionally scripts/assets) that teach Claude how to do a specific kind of task well. Loaded on demand when the task matches. Example: `frontend-design` improves visual polish for HTML/CSS work. Sourced from repos like [anthropics/skills](https://github.com/anthropics/skills) and pinned via a `skills-lock.json` in the project.
- **Plugins** — bundles that ship one or more of: skills, slash commands, hooks, agents, and MCP servers. Installed once, they add reusable capabilities across projects. Slash commands (e.g. `/brand-identity` in this repo) are the lightest form and can live directly under `.claude/commands/` without a full plugin.

Rule of thumb: reach for a **slash command** for a repeatable prompt, a **skill** to change *how* Claude approaches a category of work, and a **plugin** to distribute a set of these together.


## Claude's Context Window

Claude models process text within a **context window**—the maximum amount of text Claude can consider at once. Within Claude Code, your conversation history is automatically compressed as it grows, enabling unlimited-length sessions. However, for API applications, keep context limits in mind when designing prompts and managing conversation history.


## Repository Layout

```
.
├── README.md
├── CLAUDE.md                                    # Guidance for Claude Code in this repo
├── SugarAndBloomProject/
│   ├── WithoutSkill/sugar_and_bloom.html
│   └── WithFrontEndDesignSkill/
│       ├── sugar_and_bloom_v2.html
│       └── skills-lock.json
├── BrandedAssets/
│   ├── .claude/commands/brand-identity.md       # /brand-identity slash command
│   └── priya-james-followup-email.html          # Output produced with the command
└── CalorieTracker/
    └── index.html                               # Interactive calorie tracking application
```
