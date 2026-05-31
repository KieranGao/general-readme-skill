<!--
  Example: CLI Tool README
  Tone: Minimal
  Badge style: Flat
  Project type: CLI tool (filelint)
  Sections: Hero, Features, Quick Start, Usage, Configuration, Contributing, License
  This example demonstrates a minimal, confident README for a command-line tool.
-->

[English](README.md) | [中文](README-zh.md)

---

# filelint

> Fast file and directory naming convention linter

![Version](https://img.shields.io/crates/v/filelint)
![License](https://img.shields.io/badge/license-MIT-green)

![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white)

## Features

- Enforces kebab-case, snake_case, camelCase, or custom patterns
- Ignores patterns via `.filelintignore`
- JSON output for CI integration
- Zero dependencies, single binary

## Quick Start

### Cargo

```bash
cargo install filelint
```

### Homebrew

```bash
brew install user/tap/filelint
```

### Binary

Download from [releases](https://github.com/user/filelint/releases).

## Usage

### Check current directory

```bash
filelint
```

```
src/
  MyComponent.tsx → my-component.tsx
  utils/helpers.ts → utils/helpers.ts  ✓
tests/
  My_Test.spec.ts → my-test.spec.ts

3 files checked, 2 violations found
```

### Check specific directory

```bash
filelint src/ tests/
```

### Fix violations

```bash
filelint --fix
```

### JSON output

```bash
filelint --format json
```

```json
{
  "violations": [
    {
      "path": "src/MyComponent.tsx",
      "expected": "my-component.tsx",
      "pattern": "kebab-case"
    }
  ],
  "checked": 3,
  "violations_count": 1
}
```

## Configuration

### `.filelintrc`

```json
{
  "pattern": "kebab-case",
  "ignore": [
    "node_modules",
    ".git",
    "target"
  ]
}
```

### Patterns

| Pattern | Example |
|---|---|
| `kebab-case` | `my-component.tsx` |
| `snake_case` | `my_component.tsx` |
| `camelCase` | `myComponent.tsx` |
| `PascalCase` | `MyComponent.tsx` |

### Flags

| Flag | Description |
|---|---|
| `--fix` | Rename files to match pattern |
| `--format json` | Output as JSON |
| `--pattern <p>` | Override config pattern |
| `--ignore <p>` | Add ignore pattern |

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing`)
5. Open a Pull Request

## License

[MIT](LICENSE)
