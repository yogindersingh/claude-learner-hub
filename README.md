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
open SugarAndBloomProject/WithoutSkill/sugar_and_bloom.html
open SugarAndBloomProject/WithFrontEndDesignSkill/sugar_and_bloom_v2.html
```

### BrandedAssets — Custom slash command for brand consistency

Demonstrates a project-scoped custom command that pins brand guidelines so every generated asset stays on-brand without repeating the spec in each prompt.

- `BrandedAssets/.claude/commands/brand-identity.md` — the `/brand-identity` command definition (colors, typography, tone, vocabulary, closing phrases) for the fictional *Kai Lens Studio* brand.
- `BrandedAssets/priya-james-followup-email.html` — a follow-up email generated against those guidelines, showing Deep Navy / Warm Sand / Antique Gold palette and Cormorant Garamond + Nunito Sans typography applied consistently.

Key takeaway: putting brand rules in a slash command turns "please remember our brand" into a repeatable, single-invocation instruction — useful for teams producing repeated marketing collateral.


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
└── BrandedAssets/
    ├── .claude/commands/brand-identity.md       # /brand-identity slash command
    └── priya-james-followup-email.html          # Output produced with the command
```
