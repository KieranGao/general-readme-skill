# Installation — Claude Code

## Quick Setup

Copy the skill files to your project:

```bash
mkdir -p .claude/skills/general-readme
cp SKILL.md .claude/skills/general-readme/
cp -r references/ .claude/skills/general-readme/
```

## Global Installation

To make the skill available across all your projects:

```bash
mkdir -p ~/.claude/skills/general-readme
cp SKILL.md ~/.claude/skills/general-readme/
cp -r references/ ~/.claude/skills/general-readme/
```

## Usage

Type `/readme` or say "generate readme" in any Claude Code session.

## How It Works

Claude Code automatically loads skills from `.claude/skills/`. The skill triggers when you type `/readme` or say something that matches the trigger phrases in the skill description. It will ask you about tone, badge style, and language preferences before generating.
