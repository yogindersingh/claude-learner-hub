# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**claude-learner-hub** is a personal learning repository for exploring Claude Code capabilities. It contains comparative projects that demonstrate Claude's output with and without skills, serving as documentation and reference for learning Claude Code.

### Key Projects

- **SugarAndBloomProject**: A bakery landing page built twice using the same prompt:
  - `WithoutSkill/`: Version v1 built without skills
  - `WithFrontEndDesignSkill/`: Version v2 built with `frontend-design` skill from `anthropics/skills`
  - Purpose: Compare visual polish and output quality differences when using skills

## Repository Structure

```
.
├── README.md                          # Project documentation
├── SugarAndBloomProject/
│   ├── WithoutSkill/
│   │   └── sugar_and_bloom.html       # Bakery landing page (no skill)
│   └── WithFrontEndDesignSkill/
│       ├── sugar_and_bloom_v2.html    # Bakery landing page (with skill)
│       └── skills-lock.json           # Skill dependency manifest
```

## Common Development Tasks

### Viewing Projects

Both projects are single-file HTML pages with embedded CSS and are ready to open directly in a browser:

```bash
# Open version without skill
open SugarAndBloomProject/WithoutSkill/sugar_and_bloom.html

# Open version with frontend-design skill
open SugarAndBloomProject/WithFrontEndDesignSkill/sugar_and_bloom_v2.html
```

### Skills

When working with the `WithFrontEndDesignSkill` version:
- The `frontend-design` skill is locked in `skills-lock.json`
- This is sourced from `anthropics/skills` GitHub repository
- Use the skill when regenerating or modifying the frontend to maintain visual polish

## Key Learning Points

This repository demonstrates:
1. **Skills impact on output**: The frontend-design skill produces noticeably more polished visual output from identical prompts
2. **Reproducibility**: Both versions were built from the same prompt to enable direct comparison
3. **Claude Code capabilities**: Shows real-world HTML/CSS generation in a bakery landing page context

## Notes for Future Work

- These projects are learning demonstrations—treat them as reference implementations
- When comparing or regenerating these projects, maintain the same prompt to preserve the comparison value
- The project structure (no build system, plain HTML) is intentional for simplicity and learning
