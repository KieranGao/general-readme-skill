# Section Guidelines

How to write each README section. These rules apply regardless of tone profile — the profile controls *voice*, these rules control *structure*.

---

## General Rules (All Sections)

1. **No filler phrases.** Banned across all profiles: "powerful", "robust", "versatile", "leverages", "seamlessly", "cutting-edge", "comprehensive", "state-of-the-art", "ever-evolving landscape", "game-changing", "revolutionary", "next-generation", "best-in-class", "enterprise-grade"
2. **Vary sentence length.** Mix one-liners with two-sentence explanations. No uniform paragraph density.
3. **Be specific.** "Handles 10k req/sec" beats "high performance". "Uses JWT with RS256" beats "secure authentication".
4. **Only include sections with real data.** If the project has no API, skip the API section entirely. Don't write "N/A" or "Coming soon".
5. **Section intros are optional.** Check the tone profile — Minimal never uses them, Professional uses one sentence, Energetic uses one sentence max.

---

## Hero (Title + Description + Badges)

**Structure (HTML Centered Layout — Recommended):**
```html
<h1 align="center">Project Name</h1>
<p align="center">
  <strong>One-line description of what the project does</strong>
  <br />
  <em>Keywords · Features · Platform support</em>
</p>

<p align="center">
  <a href="#quick-start"><img src="https://img.shields.io/badge/Quick_Start-4CAF50?style=for-the-badge" alt="Quick Start" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="License" /></a>
</p>

<p align="center">
  <a href="https://docs.anthropic.com/en/docs/claude-code"><img src="https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white" alt="Claude Code" /></a>
  <a href="https://github.com/features/copilot"><img src="https://img.shields.io/badge/GitHub_Copilot-000000?style=flat&logo=github&logoColor=white" alt="GitHub Copilot" /></a>
  <a href="https://cursor.sh"><img src="https://img.shields.io/badge/Cursor-000000?style=flat&logo=cursor&logoColor=white" alt="Cursor" /></a>
</p>

<p align="center">
  <a href="README.md">English</a> · <a href="README-zh.md">中文</a> · <a href="README-ja.md">日本語</a>
</p>
```

**Structure (Markdown Legacy — For Reference):**
```markdown
<div align="right">

[English](README.md) · [中文](README-zh.md)

</div>

# Project Name

> One-line description of what the project does

![badge1](url)
![badge2](url)
```

**Rules:**
- Title: Use `<h1 align="center">` for HTML layout. Project name from `package.json`/`name`, `pyproject.toml`/`name`, directory name, or existing README. No prefix ("My Project" not "Project: My Project").
- Description: Use `<p align="center">` with `<strong>` for main description. One sentence, 10-25 words. States what it *does*, not what it *is*.
  - ✓ "Fast, type-safe HTTP server for Node.js"
  - ✗ "A powerful and robust HTTP server framework"
  - ✗ "This project is an HTTP server"
- Subtitle: Use `<em>` for keywords/features/platform support line.
- CTA Buttons: Use `for-the-badge` style badges for "Quick Start" and "License" links.
- Platform Badges: Add AI IDE platform badges (Claude Code, Copilot, Cursor, etc.) in a separate `<p align="center">`.
- Language switcher: Use `<p align="center">` with anchor tags. See language-guide.md.
- Tech Stack Badges: Follow badge-styles.md grouping rules for project-specific badges.

---

## Features / Why

**Structure (Energetic):**
```markdown
## Features

- ⚡ **Blazing fast** — Sub-millisecond response times
- 🔒 **Secure by default** — JWT auth, CORS, rate limiting out of the box
- 🎯 **Type-safe** — Full TypeScript inference, zero `any`
```

**Structure (Minimal):**
```markdown
## Features

- Type-safe API with full inference
- Zero-config TypeScript support
- Built-in authentication and rate limiting
```

**Structure (Professional):**
```markdown
## Features

| Feature | Description |
|---|---|
| Type Safety | Full TypeScript inference with zero configuration |
| Authentication | JWT-based auth with role-based access control |
```

**Rules:**
- Max 6 items. If the project has more, pick the 6 most differentiating.
- Don't pad — if the project only has 2 real features, list 2.
- Extract from: directory structure, API routes, code comments, package.json description.
- Each item states a benefit, not just a feature name.

---

## Quick Start

**Structure:**
```markdown
## Quick Start

### Prerequisites

- Node.js 18+
- PostgreSQL 14+

### Install

\`\`\`bash
npm install my-package
\`\`\`

### Configure

\`\`\`bash
cp .env.example .env
# Edit .env with your database credentials
\`\`\`

### Run

\`\`\`bash
npm run dev
\`\`\`
```

**Rules:**
- Max 4 steps: prerequisites → install → configure → run.
- Each step is a single copy-pasteable command block.
- No "Step 1:", "Step 2:" prefixes — use H3 headings or just the commands.
- If Docker is available, offer it as the first option (fastest path to running).
- Include minimum runtime version only if specified in the project (engines field, .python-version, .tool-versions, etc.).
- For CLI tools: show installation methods (npm, brew, cargo, go install) then a usage example.

---

## Usage

**Structure:**
```markdown
## Usage

### Basic Request

\`\`\`typescript
import { createClient } from 'my-package'

const client = createClient({ apiKey: 'xxx' })
const result = await client.users.get('123')
console.log(result)
\`\`\`

### With Error Handling

\`\`\`typescript
try {
  const result = await client.users.get('123')
} catch (error) {
  if (error.code === 'NOT_FOUND') {
    // handle
  }
}
\`\`\`
```

**Rules:**
- Real code examples from the project — not invented ones.
- One example per core feature, max 4 examples.
- Code blocks with language hints (`typescript`, `python`, `go`, etc.).
- Minimal comments — the code should be self-explanatory.
- Use H3 headings to label each example.

---

## Architecture Diagram

**Structure:**
```markdown
## Architecture

\`\`\`mermaid
graph LR
    A[Client] --> B[API] --> C[DB]
\`\`\`
```

**Rules:**
- One-liner intro before the diagram (optional, skip for Minimal tone).
- Mermaid block per diagram-templates.md.
- No "The following diagram illustrates..." — just put the diagram.
- No `<details>` wrapper — diagrams should be immediately visible.

---

## Configuration

**Structure:**
```markdown
## Configuration

### Environment Variables

| Variable | Description | Default |
|---|---|---|
| \`DATABASE_URL\` | PostgreSQL connection string | — |
| \`PORT\` | Server port | \`3000\` |
| \`LOG_LEVEL\` | Logging level | \`info\` |
```

**Rules:**
- Only include if config files are detected (.env, config.yaml, etc.).
- Table format: key | description | default.
- Group by file if multiple config files exist.
- Include `.env.example` values if the file exists.
- Use inline code for variable names.

---

## API

**Structure:**
```markdown
## API

### Endpoints

| Method | Path | Description | Auth |
|---|---|---|---|
| GET | \`/users\` | List all users | Bearer |
| POST | \`/users\` | Create a user | Bearer |
| GET | \`/users/:id\` | Get user by ID | Bearer |
```

**Rules:**
- Only include if API routes are detected.
- Table format: method | path | description | auth.
- Group by resource/module (Users, Posts, Auth, etc.).
- For REST APIs: include HTTP method + path.
- For GraphQL: include query/mutation name + return type.
- For gRPC: include service + method + request/response types.

---

## Directory Structure

**Structure:**
```markdown
## Project Structure

\`\`\`
src/
├── api/              # API route handlers
│   ├── users.ts      # User endpoints
│   └── posts.ts      # Post endpoints
├── models/           # Database models
├── services/         # Business logic
├── utils/            # Shared utilities
└── index.ts          # Entry point
config/               # Configuration files
tests/                # Test files
\`\`\`
```

**Rules:**
- Exclude: `node_modules`, `.git`, `build`, `dist`, `__pycache__`, `.venv`, `.next`, `coverage`, `.DS_Store`
- Each top-level directory gets a one-line comment.
- Max depth: 3 levels.
- Use `├──`, `│`, `└──` tree characters.
- Include key files at root level (package.json, tsconfig.json, Dockerfile, etc.).

---

## Tech Stack

**Structure:**
```markdown
## Tech Stack

### Frontend

| Technology | Purpose |
|---|---|
| Vue 3 | UI framework |
| Pinia | State management |

### Backend

| Technology | Purpose |
|---|---|
| Express | HTTP server |
| Prisma | ORM |

### Infrastructure

| Technology | Purpose |
|---|---|
| Docker | Containerization |
| PostgreSQL | Database |
```

**Rules:**
- Group by layer: Frontend / Backend / Database / Infrastructure / Testing.
- Only include technologies actually used (not devDependencies unless significant like test frameworks).
- No "Other Tools" catch-all category.
- Use the technology name, not the package name (e.g., "Vue 3" not "vue@3").

---

## Deployment

**Structure:**
```markdown
## Deployment

### Docker

\`\`\`bash
docker build -t my-app .
docker run -p 3000:3000 my-app
\`\`\`

### Docker Compose

\`\`\`bash
docker-compose up -d
\`\`\`

### CI/CD

This project uses GitHub Actions for CI/CD. See \`.github/workflows/\` for configuration.
```

**Rules:**
- Only include if Dockerfile, docker-compose.yml, or CI config is detected.
- Docker commands first (most common deployment method).
- Include actual commands from the project, not generic examples.
- If CI/CD is configured, mention it and link to the config.

---

## Contributing

**Structure:**
```markdown
## Contributing

1. Fork the repository
2. Create a feature branch (\`git checkout -b feature/amazing\`)
3. Commit your changes (\`git commit -m 'feat: add amazing feature'\`)
4. Push to the branch (\`git push origin feature/amazing\`)
5. Open a Pull Request
```

**Rules:**
- Short. Fork → Branch → Commit → PR.
- Link to CONTRIBUTING.md if it exists, otherwise inline the basics.
- Include commit convention if the project uses one (conventional commits, etc.).
- No "We welcome contributions!" opener — just the steps.

---

## License

**Structure:**
```markdown
## License

[MIT](LICENSE)
```

**Rules:**
- Name + link to LICENSE file. One line.
- Read the LICENSE file to determine the license type.
- No "This project is licensed under the MIT License — see the LICENSE file for details" boilerplate.

---

## Beautification Summary

This section summarizes which elements can be beautified with HTML during Phase 4.

### Always Beautify (HTML)

| Section | Element | Markdown → HTML |
|---|---|---|
| Hero | Title | `# Title` → `<h1 align="center">` |
| Hero | Description | `> desc` → `<p align="center"><strong>` |
| Hero | Subtitle | keywords → `<p align="center"><em>` |
| Hero | CTA Buttons | `[text](url)` → `<img src="badge?style=for-the-badge">` |
| Hero | Badges | `![alt](url)` → `<p align="center"><img>` |
| Hero | Language Switcher | `[EN](url) · [中文](url)` → `<p align="center"><a>` |

### Keep as Markdown

| Section | Element | Reason |
|---|---|---|
| Features | Lists | Easier to maintain |
| Quick Start | Code blocks | Has syntax highlighting |
| Usage | Code blocks | Has syntax highlighting |
| Architecture | Mermaid diagrams | GitHub native support |
| Configuration | Tables | Easier to maintain |
| API | Tables | Easier to maintain |
| Directory Structure | Code blocks | Has syntax highlighting |
| Tech Stack | Tables | Easier to maintain |
| Deployment | Code blocks | Has syntax highlighting |
| Contributing | Lists | Easier to maintain |
| License | Link | GitHub styling sufficient |

### Detailed Rules

For complete beautification rules, HTML templates, and transformation examples, see `references/beautification-rules.md`.
