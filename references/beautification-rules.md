# Beautification Rules

Detailed rules for Phase 4: Beautification. These rules determine when and how to replace Markdown syntax with HTML for improved visual presentation.

---

## General Principles

1. **Only beautify when HTML produces clearly better visual results.** If Markdown looks fine, keep it.
2. **Preserve readability.** HTML should be well-formatted and easy to read in raw form.
3. **Maintain GitHub compatibility.** All HTML must render correctly on GitHub.
4. **Keep content intact.** Never change the meaning or content of the README.

---

## Beautifiable Elements

### Hero Region

| Element | Markdown | HTML | When to Apply |
|---|---|---|---|
| Title | `# Title` | `<h1 align="center">Title</h1>` | Always |
| Description | `> Description` | `<p align="center"><strong>Description</strong></p>` | Always |
| Subtitle | `keywords` | `<p align="center"><em>keywords</em></p>` | Always |
| CTA Buttons | `[Quick Start](#)` | `<a href="#"><img src="badge?style=for-the-badge"></a>` | Always |
| Platform Badges | `![Badge](url)` | `<p align="center"><img src="url"></p>` | Always |
| Language Switcher | `[EN](README.md) · [中文](README-zh.md)` | `<p align="center"><a href="README.md">EN</a> · <a href="README-zh.md">中文</a></p>` | Always |

### Content Region

| Element | Markdown | HTML | When to Apply |
|---|---|---|---|
| Tables | `\| col1 \| col2 \|` | Keep Markdown | Never (easier to maintain) |
| Lists | `- item` | Keep Markdown | Never (easier to maintain) |
| Collapsible Panels | `<details><summary>` | Keep HTML | Already formatted |
| Blockquotes | `> text` | Keep Markdown | Never (GitHub styling sufficient) |

### Code Region

| Element | Markdown | HTML | When to Apply |
|---|---|---|---|
| Code Blocks | ` ```code``` ` | Keep Markdown | Never (has syntax highlighting) |
| Mermaid Diagrams | ` ```mermaid ``` ` | Keep Markdown | Never (GitHub native support) |
| Inline Code | `` `code` `` | Keep Markdown | Never (GitHub styling sufficient) |

### Structure Region

| Element | Markdown | HTML | When to Apply |
|---|---|---|---|
| Dividers | `---` | Keep Markdown | Never (GitHub styling sufficient) |
| Anchor Links | `[text](#anchor)` | Keep Markdown | Never (GitHub styling sufficient) |
| Section Headers | `## Title` | Keep Markdown | Never (GitHub styling consistent) |

---

## HTML Templates

### Hero Title

```html
<h1 align="center">{PROJECT_NAME}</h1>
```

### Hero Description

```html
<p align="center">
  <strong>{ONE_LINE_DESCRIPTION}</strong>
</p>
```

### Hero Subtitle

```html
<p align="center">
  <em>{KEYWORDS}</em>
</p>
```

### CTA Buttons

```html
<p align="center">
  <a href="#quick-start"><img src="https://img.shields.io/badge/Quick_Start-{COLOR}?style=for-the-badge" alt="Quick Start" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-{LICENSE_TYPE}-{COLOR}?style=for-the-badge" alt="License" /></a>
</p>
```

### Platform Badges

```html
<p align="center">
  <a href="https://docs.anthropic.com/en/docs/claude-code"><img src="https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white" alt="Claude Code" /></a>
  <a href="https://github.com/features/copilot"><img src="https://img.shields.io/badge/GitHub_Copilot-000000?style=flat&logo=github&logoColor=white" alt="GitHub Copilot" /></a>
  <a href="https://cursor.sh"><img src="https://img.shields.io/badge/Cursor-000000?style=flat&logo=cursor&logoColor=white" alt="Cursor" /></a>
</p>
```

### Language Switcher

```html
<p align="center">
  <a href="README.md">English</a> · <a href="README-zh.md">中文</a> · <a href="README-ja.md">日本語</a> · <a href="README-ko.md">한국어</a> · <a href="README-ru.md">Русский</a>
</p>
```

### Combined Hero Section

```html
<h1 align="center">{PROJECT_NAME}</h1>
<p align="center">
  <strong>{ONE_LINE_DESCRIPTION}</strong>
  <br />
  <em>{KEYWORDS}</em>
</p>

<p align="center">
  <a href="#quick-start"><img src="https://img.shields.io/badge/Quick_Start-4CAF50?style=for-the-badge" alt="Quick Start" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="License" /></a>
</p>

<p align="center">
  {PLATFORM_BADGES}
</p>

<p align="center">
  {LANGUAGE_SWITCHER}
</p>
```

---

## Transformation Examples

### Before (Markdown)

```markdown
# My Project

> A fast, type-safe HTTP server for Node.js

![Build](https://img.shields.io/github/actions/workflow/status/user/repo/ci.yml)
![Version](https://img.shields.io/npm/v/package)
![License](https://img.shields.io/badge/license-MIT-green)

[English](README.md) · [中文](README-zh.md)
```

### After (HTML)

```html
<h1 align="center">My Project</h1>
<p align="center">
  <strong>A fast, type-safe HTTP server for Node.js</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/github/actions/workflow/status/user/repo/ci.yml" alt="Build" />
  <img src="https://img.shields.io/npm/v/package" alt="Version" />
  <img src="https://img.shields.io/badge/license-MIT-green" alt="License" />
</p>

<p align="center">
  <a href="README.md">English</a> · <a href="README-zh.md">中文</a>
</p>
```

---

## User Interaction Format

When presenting beautification suggestions to the user, use this format:

```
AI: README generation complete! Analyzing beautification opportunities...

Found the following beautification suggestions:

1. ✅ [Hero] Title centered → <h1 align="center">
2. ✅ [Hero] Description centered and bold → <p align="center"><strong>
3. ✅ [Hero] Add CTA buttons
4. ✅ [Hero] Platform badges centered
5. ⚪ [Content] Tables keep Markdown (easier to maintain)
6. ⚪ [Code] Code blocks keep Markdown (has syntax highlighting)

Accept these suggestions?
[Accept All] [Confirm Each] [Reject All]
```

**Legend:**
- ✅ = Will be beautified (HTML)
- ⚪ = Will remain as Markdown (no change needed)

---

## Exception Handling

1. **Transformation fails:** Keep original Markdown, log error
2. **User rejects all:** Skip beautification entirely
3. **Partial acceptance:** Apply only accepted transformations
4. **Already beautified:** Check for `<!-- BEAUTIFIED -->` marker, skip if present

---

## Quality Checks

After beautification, verify:

1. **GitHub rendering:** All HTML renders correctly
2. **Content preservation:** No content was lost or changed
3. **Link integrity:** All links still work
4. **Badge visibility:** All badges display correctly
5. **Language switcher:** All language links work
