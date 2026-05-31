# Design Spec: Beautification Stage

**Date:** 2026-05-31
**Status:** Approved
**Author:** OxyTheCrack

## Problem Statement

The current skill generates README files using pure Markdown syntax. While functional, the visual output is less polished than HTML-enhanced versions. A dedicated beautification stage is needed to automatically enhance the generated README with HTML where appropriate.

## Solution

Add a **Phase 4: Beautification** stage between Generation and Output. This stage reviews the generated README and suggests HTML replacements for Markdown elements where HTML produces better visual results.

## Design Decisions

### 1. Architecture: Post-Processing Stage

**Decision:** Add beautification as a separate phase after generation.

**Rationale:**
- Separation of concerns: Generation focuses on content, beautification focuses on presentation
- Easier maintenance: Beautification rules are independent and can be updated separately
- Flexibility: Can selectively beautify based on project characteristics
- Debuggability: Clear before/after differences

### 2. Trigger: Automatic

**Decision:** Beautification phase triggers automatically after generation completes.

**Rationale:**
- Consistent user experience
- No additional commands needed
- Always produces polished output

### 3. Strategy: Semi-Automatic with Confirmation

**Decision:** AI suggests beautification points, user confirms before execution.

**Rationale:**
- User maintains control over final output
- Prevents unwanted changes
- Educational: user learns what can be beautified

### 4. Scope: Comprehensive

**Decision:** Beautification covers Hero, content, code/diagrams, and structure.

**Rationale:**
- Consistent visual style throughout
- Maximum aesthetic improvement
- Single pass for all enhancements

## New Workflow

```mermaid
graph LR
    A[User Trigger] --> B[Phase 1<br/>Configure]
    B --> C[Phase 2<br/>Scan]
    C --> D[Phase 3<br/>Generate]
    D --> E[Phase 4<br/>Beautify]
    E --> F[Phase 5<br/>Output]
    style A fill:#E6A23C,color:#fff
    style B fill:#409EFF,color:#fff
    style C fill:#67C23A,color:#fff
    style D fill:#F56C6C,color:#fff
    style E fill:#9B59B6,color:#fff
    style F fill:#909399,color:#fff
```

## Phase 4: Beautification (Detailed Design)

### Execution Flow

1. **Analysis** (Automatic)
   - Scan generated README.md
   - Identify beautifiable Markdown elements
   - Generate beautification suggestion list

2. **Confirmation** (User Interaction)
   - Display suggestion list
   - User accepts/rejects each suggestion
   - Or select "Accept All" / "Reject All"

3. **Execution** (Automatic)
   - Apply selected beautifications
   - Keep unselected Markdown as-is

### Beautifiable Elements

| Element | Markdown Original | HTML Beautification | Effect |
|---|---|---|---|
| Centered Title | `# Title` | `<h1 align="center">` | Title centered |
| Centered Description | `> Description` | `<p align="center"><strong>` | Description centered and bold |
| CTA Buttons | `[Quick Start](#)` | `<img src="badge">` | Button-style badges |
| Platform Badges | `![Badge](url)` | `<p align="center"><img>` | Centered badges |
| Language Switcher | `[EN](README.md) · [中文](README-zh.md)` | `<p align="center">` | Centered links |
| Collapsible Panels | `<details><summary>` | Keep as-is | Already HTML |
| Tables | `\| col1 \| col2 \|` | Keep as-is | Markdown tables sufficient |
| Code Blocks | ` ```code``` ` | Keep as-is | Has syntax highlighting |
| Mermaid Diagrams | ` ```mermaid ``` ` | Keep as-is | GitHub native support |

### Beautification Rules

#### 1. Hero Region (Mandatory Beautification)

- Title: `<h1 align="center">`
- Description: `<p align="center"><strong>`
- Subtitle: `<em>`
- CTA Buttons: `for-the-badge` style badges
- Platform Badges: Centered layout
- Language Switcher: Centered layout

#### 2. Content Region (Optional)

- Section titles: Keep Markdown `##` (consistent GitHub styling)
- Tables: Keep Markdown (easier to maintain)
- Lists: Keep Markdown (easier to maintain)
- Collapsible panels: Already HTML, keep as-is

#### 3. Code/Diagram Region (Keep As-Is)

- Code blocks: Keep Markdown (has syntax highlighting)
- Mermaid diagrams: Keep Markdown (GitHub native support)

#### 4. Structure Region (Optional)

- Dividers: Keep `---`
- Anchor links: Keep Markdown

### User Interaction Example

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

User: Accept All

AI: Applying beautifications...
    ✅ Beautification complete!
```

### Reference File Updates

#### New File: `references/beautification-rules.md`

Contains:
- List of beautifiable elements
- HTML templates for each element
- Rules for when to apply beautification
- Examples of before/after transformations

#### Updated File: `SKILL.md`

Add Phase 4 section with:
- Trigger conditions
- Execution flow
- User interaction format
- Beautification rules reference

#### Updated File: `references/section-guidelines.md`

Add beautification notes to each section:
- Which elements can be beautified
- HTML templates for beautification
- When to keep Markdown vs use HTML

## Testing

After implementation, verify:
1. Beautification triggers automatically after generation
2. Suggestion list displays correctly
3. User can accept/reject individual suggestions
4. Beautified README renders correctly on GitHub
5. Unselected elements remain as Markdown
6. All existing content is preserved
