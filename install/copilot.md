# Installation — GitHub Copilot

## Setup

1. Create the instructions directory:

```bash
mkdir -p .github
```

2. Copy the skill as Copilot instructions:

```bash
cp SKILL.md .github/copilot-instructions.md
```

3. Copy reference files:

```bash
cp -r references/ .github/copilot-instructions/references/
```

## Usage

Open Copilot Chat in VS Code (Ctrl+Shift+I / Cmd+Shift+I) or JetBrains and say "generate readme" or "write a README for this project".

## How It Works

GitHub Copilot loads `.github/copilot-instructions.md` as custom instructions. These instructions are injected into all Copilot Chat conversations. The reference files must be in the repository so Copilot can read them.

## Notes

- Copilot's custom instructions are always active — the skill content will influence all conversations, not just README ones.
- If you only want the skill active for specific sessions, remove the instructions file when not needed.
