---
theme: professional
layout: full
---

# Syntax Cheatsheet

::: cols-2
### Text & Structure
- `# H1` · `## H2` · `### H3`
- `**bold**` · `*italic*` · `~~strike~~`
- `> Quote` · `---` Rule
- `- List` · `1. numbered`
- `code` inline · Code blocks · `| Table |`
- `[Link](url)` · hard break: `<br>`

### Accents & Colors
- `^Accent word^` (H1 only)
- `==Highlight==`
- `{#0af: Text}` · `{tomato: Text}`
- `[Text]{color= bg= border=}`
- `[[Badge|green]]` · `[[Badge|#0af]]`
- `# Title {color=#f00}`
+++
### Layout
- `::: cols-2 … +++ … :::`
- `cols-2/3/4`, `cols-2-1`, `cols-1-3`
- `::: rows` (stacked boxes)
- Block color: first line `{bg= color= border=}`
- `{.ghost}` = without box
- full width = text outside the block

### Spacing & HTML
- multiple spaces are preserved
- `\t` Tabulator · `[sp=2em]` space
- `::: html … :::` Raw HTML
- `mermaid` block for diagrams

### Frontmatter
- `theme:` · `layout:` · `accent:`
- `bg:` · `gradient:` · `image:` · `overlay:`
:::
