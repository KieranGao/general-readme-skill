# Installation — Cursor

## Setup

1. Create the rules directory:

```bash
mkdir -p .cursor/rules
```

2. Copy the skill file:

```bash
cp SKILL.md .cursor/rules/general-readme.mdc
```

3. Copy reference files:

```bash
cp -r references/ .cursor/rules/references/
```

## Usage

Open Cursor's AI chat (Cmd+L / Ctrl+L) and say "generate readme" or "write a README for this project".

## How It Works

Cursor loads `.mdc` files from `.cursor/rules/` as context for the AI. The reference files must be in the project so Cursor can read them when needed. The skill content is injected into the AI's context for README-related conversations.
