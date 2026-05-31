<div align="right">

English · [中文](README-zh.md) · [日本語](README-ja.md) · [한국어](README-ko.md) · [Русский](README-ru.md)

</div>

# general-readme-skill

> Generate professional README files for any project using AI coding assistants

![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-blue?style=flat)

## Features

| Feature | Description |
|---|---|
| Multi-Tone Support | Three writing profiles: Energetic, Minimal, and Professional |
| Badge System | Automatic shields.io badge generation with three visual styles |
| Multi-Language | Generate README files in English, Chinese, Japanese, Korean, Russian, and more |
| Zero Dependencies | No external CLI, runtime, or network service required |
| Multi-Platform | Works with Claude Code, GitHub Copilot, and Cursor |
| Privacy-First | Automatic masking of sensitive keys, passwords, and private information |

## Quick Start

### Claude Code

```bash
mkdir -p .claude/skills/general-readme
cp SKILL.md .claude/skills/general-readme/
cp -r references/ .claude/skills/general-readme/
```

### GitHub Copilot

```bash
mkdir -p .github
cp SKILL.md .github/copilot-instructions.md
cp -r references/ .github/copilot-instructions/references/
```

### Cursor

```bash
mkdir -p .cursor/rules
cp SKILL.md .cursor/rules/general-readme.mdc
cp -r references/ .cursor/rules/references/
```

## Usage

Type `/readme` or say "generate readme" in your AI coding assistant. The skill will guide you through:

1. **Configuration** — Select tone profile, badge style, and languages
2. **Project Scan** — Automatic detection of project type, tech stack, and structure
3. **Generation** — Create README following the inverted pyramid structure
4. **Output** — Generate primary and translated README files

### Supported Commands

| Command | Description |
|---|---|
| `/readme` | Trigger README generation |
| `generate readme` | Natural language trigger |
| `write readme` | Natural language trigger |
| `帮我写 README` | Chinese language trigger |
| `更新README` | Update existing README |

## Project Structure

```
general-readme-skill/
├── SKILL.md                # Main skill definition
├── examples/               # Example README files
│   ├── app-readme.md       # Full-stack application example
│   ├── cli-readme.md       # CLI tool example
│   └── library-readme.md   # Library/package example
├── install/                # Installation guides
│   ├── claude-code.md      # Claude Code setup
│   ├── copilot.md          # GitHub Copilot setup
│   └── cursor.md           # Cursor setup
└── references/             # Reference files
    ├── badges.md           # Technology badge mapping
    ├── badge-styles.md     # Badge layout rules
    ├── diagram-templates.md # Mermaid/SVG templates
    ├── language-guide.md   # Multi-language rules
    ├── section-guidelines.md # Section writing rules
    └── tone-profiles.md    # Writing tone definitions
```

## Tech Stack

### Documentation

| Technology | Purpose |
|---|---|
| Markdown | Primary content format |
| shields.io | Badge generation |
| Mermaid | Architecture diagrams |

### Supported Platforms

| Platform | Integration Method |
|---|---|
| Claude Code | `.claude/skills/` directory |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Cursor | `.cursor/rules/` directory |

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing`)
5. Open a Pull Request

## License

No LICENSE file detected. Add a LICENSE to clarify project licensing.
