# Language Guide

Multi-language README support. English is the default primary language.

---

## File Naming

Use ISO 639-1 codes. BCP 47 for regional variants.

| Language | File | Code |
|---|---|---|
| English (primary) | `README.md` | — |
| Chinese (Simplified) | `README-zh.md` | zh |
| Chinese (Traditional) | `README-zh-TW.md` | zh-TW |
| Japanese | `README-ja.md` | ja |
| Korean | `README-ko.md` | ko |
| French | `README-fr.md` | fr |
| German | `README-de.md` | de |
| Spanish | `README-es.md` | es |
| Portuguese (Brazil) | `README-pt-br.md` | pt-br |
| Russian | `README-ru.md` | ru |
| Arabic | `README-ar.md` | ar |

---

## Language Switcher

Every README starts with a language switcher. Choose the style based on tone profile:

### Default (Energetic / Professional)

Right-aligned at the top:

```markdown
<div align="right">

[English](README.md) · [中文](README-zh.md) · [日本語](README-ja.md)

</div>
```

### Minimal

Plain links with separator:

```markdown
[English](README.md) | [中文](README-zh.md) | [日本語](README-ja.md)

---
```

### Rules

- The current language is **not linked** (it's plain text, not a link).
- Languages are listed in the order they were created.
- The separator is ` · ` (middle dot with spaces) for the default style, ` | ` (pipe with spaces) for minimal.

---

## Generation Flow

1. Ask the developer for primary language (default: English)
2. Ask for secondary languages (default: none)
3. Generate primary `README.md` first
4. For each secondary language, generate `README-{lang}.md`
5. Add language switcher to all files

---

## Suggested Language Sets

| Use Case | Primary | Secondaries |
|---|---|---|
| Global open source | English | — |
| Chinese community | English | Chinese |
| Japanese community | English | Japanese |
| East Asian | English | Chinese, Japanese, Korean |
| Full international | English | Chinese, Japanese, Korean, Spanish, French |

---

## Translation Rules

1. **Structure mirrors exactly.** Same sections, same order, same headings.
2. **Natural translation.** Not word-for-word. Each language should read naturally to native speakers.
3. **Code blocks never translate.** Commands, variable names, file paths, API endpoints stay in English.
4. **Technical terms stay English** where the community uses the English term (e.g., "API", "REST", "Docker", "npm"). Translate only terms that have established native equivalents.
5. **Headings translate.** "Features" → "功能" (Chinese) → "機能" (Japanese).
6. **Badge alt text stays English.** Badge images are visual — alt text doesn't need translation.

---

## Common Heading Translations

| English | Chinese | Japanese | Korean | Spanish |
|---|---|---|---|---|
| Features | 功能特性 | 機能 | 기능 | Características |
| Quick Start | 快速开始 | クイックスタート | 빠른 시작 | Inicio rápido |
| Installation | 安装 | インストール | 설치 | Instalación |
| Usage | 使用方法 | 使い方 | 사용법 | Uso |
| Configuration | 配置 | 設定 | 설정 | Configuración |
| API | API | API | API | API |
| Architecture | 架构 | アーキテクチャ | 아키텍처 | Arquitectura |
| Contributing | 贡献 | コントリビュート | 기여 | Contribuir |
| License | 许可证 | ライセンス | 라이선스 | Licencia |
