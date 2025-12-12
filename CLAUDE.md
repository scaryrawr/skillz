# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository contains Claude Code skills - configuration files that extend Claude's capabilities by teaching it how to interact with specific tools and services. Skills are stored in `~/.claude/skills/` and automatically loaded by Claude Code.

## Skill Structure

Each skill lives in its own directory and contains a `SKILL.md` file with:
- YAML frontmatter defining `name` and `description`
- Markdown body with instructions, examples, and commands for Claude to use

Example structure:
```
skill-name/
  SKILL.md
```

## Writing Skills

When creating or modifying skills:
1. Use descriptive names and descriptions in the frontmatter - these help Claude decide when to invoke the skill
2. Include concrete command examples with placeholders (e.g., `{project}`, `{prId}`)
3. Document workarounds for tools that lack first-class CLI support (e.g., using `az devops invoke` for REST APIs)
