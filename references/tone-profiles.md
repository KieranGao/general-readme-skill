# Tone Profiles

Choose one profile at generation time. Every piece of generated text follows the chosen profile's rules.

---

## Profile A: Energetic

Inspired by FastAPI, shadcn/ui.

### Voice
Direct, confident, slightly opinionated. Write like you're excited about what the project does but not overselling it. Contractions are welcome ("it's", "you'll", "won't").

### Sentence Rules
- Short sentences. If a sentence has more than two commas, split it.
- Start sections with the benefit, not the feature.
- Use active voice: "Handles 10k requests/sec" not "10k requests/sec can be handled"

**Do:**
- "Get up and running in 30 seconds."
- "Type-safe from end to end — no `any` anywhere."
- "Drops into any Express app. Zero config."

**Don't:**
- "This is a powerful and robust framework that leverages cutting-edge technology."
- "It seamlessly integrates with your existing workflow."
- "In the ever-evolving landscape of web development..."

### Section Intros
One sentence max. Optional. Skip if the section title is self-explanatory.

**Good:** "Everything you need, nothing you don't."
**Bad:** "The following section describes the features and capabilities of this project."

### Feature Format
Emoji-prefixed benefit statements:

```
- ⚡ **Blazing fast** — Sub-millisecond response times
- 🔒 **Secure by default** — JWT auth, CORS, rate limiting out of the box
- 🎯 **Type-safe** — Full TypeScript inference, zero `any`
```

### Banned Phrases
"powerful", "robust", "versatile", "leverages", "seamlessly", "cutting-edge", "comprehensive", "state-of-the-art", "game-changing", "revolutionary", "next-generation", "best-in-class", "enterprise-grade", "production-ready" (unless citing actual production usage)

### Preferred Vocabulary
"fast" over "high-performance", "simple" over "streamlined", "build" over "architect", "use" over "leverage", "works with" over "seamlessly integrates with"

---

## Profile B: Minimal

Inspired by Tailwind CSS, shadcn/ui, esbuild.

### Voice
Confident, quiet. Let the code speak. If a section can be shorter, make it shorter. Every word earns its place.

### Sentence Rules
- One-line descriptions. No paragraphs unless absolutely necessary.
- No section intros. Jump straight to content.
- No explanatory text around code blocks — just the code.

**Do:**
- "Type-safe API with full inference."
- "npm install my-package"
- (just the command, no "Run the following to install:")

**Don't:**
- "To get started, simply run the following command to install the package:"
- "This section will guide you through the installation process."
- Any sentence that restates what's obvious from the code.

### Section Intros
Never. The section heading is the intro.

### Feature Format
Plain list. No emoji. No bold. No em dash.

```
- Type-safe API with full inference
- Zero-config TypeScript support
- Built-in authentication and rate limiting
```

### Banned Phrases
All phrases banned in Profile A, plus: "simply", "just", "easy", "straightforward", "obviously", "of course", "as you can see", "note that", "it's worth mentioning"

### Preferred Vocabulary
Shortest word that conveys the meaning. "Use" not "utilize". "Make" not "implement". "Add" not "integrate".

---

## Profile C: Professional

Inspired by Kubernetes, Node.js, Django, Rust.

### Voice
Neutral, thorough, structured. Write like a senior engineer documenting something for their team. Clear over clever. Complete sentences, not fragments.

### Sentence Rules
- Complete sentences with subject and verb.
- Define terms on first use if they're domain-specific.
- Use parallel structure in lists (all items start with verb, or all with noun — don't mix).

**Do:**
- "The server validates incoming requests against the JSON schema before processing."
- "Prerequisites: Node.js 18+, PostgreSQL 14+"
- "This section covers configuration options for the authentication module."

**Don't:**
- "Super fast validation! 🚀"
- "Just install Node and you're good to go."
- Emoji in section content (emoji in badges is fine).

### Section Intros
One sentence stating what the section covers. Neutral tone.

**Good:** "The following steps describe how to set up the development environment."
**Acceptable:** Skip if the heading is clear enough.

### Feature Format
Structured table:

```
| Feature | Description |
|---|---|
| Type Safety | Full TypeScript inference with zero configuration |
| Authentication | JWT-based auth with role-based access control |
```

Or a structured list with consistent formatting:

```
- **Type Safety** — Full TypeScript inference with zero configuration.
- **Authentication** — JWT-based auth with role-based access control.
```

### Banned Phrases
All phrases banned in Profile A, plus: emoji in prose, exclamation marks in descriptions, "awesome", "cool", "amazing", "love", "hate"

### Preferred Vocabulary
Precise technical terms. "Authenticate" not "log in". "Configure" not "set up". "Initialize" not "create". "Validate" not "check".
