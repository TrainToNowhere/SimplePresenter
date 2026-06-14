# SimplePresenter — Syntax Reference

The complete Markdown syntax for SimplePresenter. For an overview of the project, see the [README](README.md).

**Core Principles:** No installation, maximum simplicity, content driven by simple Markdown files with extended syntax. One `.md`/`.html` file = one slide. The entire presentation consists of a single file (`app/simple-presenter.html`) plus a folder containing slides — easily populated even by AI with minimal effort.

## Usage

1. Open `simple-presenter.html` in your browser.
2. Slides are located as numbered files in the same directory (`01-title.md`, `02-…` etc.) and are loaded in alphabetical order.
3. Each file represents exactly one slide. Supported extensions are `.md` (Markdown) or `.html` (raw).

The Markdown parser is custom-built (regex-based, no external libraries except [Mermaid](https://mermaid.js.org/) for diagrams via CDN).

---

## Markdown Syntax Reference

> One file = one slide, `.md` extension

### Frontmatter (optional, at the very top between `---`)

| Key        | Values / Example                                                           | Meaning                                                                                |
|------------|----------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| `theme`    | `dark` \| `light` \| `accent` \| `midnight` \| `warm` \| `professional`    | Slide color scheme (Default: `dark`); `professional` = clean/light with subtle accents |
| `layout`   | `center` \| `full`                                                         | `center` = center content; `full` = use full slide area instead of centered column     |
| `accent`   | `#ff6b6b`  or  `#ff6b6b, #ffa06b`                                          | Accent color(s) for the slide                                                          |
| `bg`       | `#101018`                                                                  | Solid background color                                                                 |
| `gradient` | `135deg, #1a0a2e, #0a1628`  (or full CSS gradient)                         | Gradient background                                                                    |
| `image`    | `image.jpg`                                                                | Full-screen background image from the folder                                           |
| `overlay`  | `rgba(0,0,0,.5)`                                                           | Darkening overlay on top of the image                                                  |

### Standard Markdown

- `# Heading`
- `**bold**`, `*italic*`, `~~strikethrough~~`
- `- Lists` / `1. numbered` (indent items to create nested sub-lists)
- `> Quote`
- `` `code` `` and ` ```codeblock``` `
- `| Tables |`
- `[Link](url)`, `![Image](file.png)`
- `---` (Horizontal rule)

### Extended Syntax

| Syntax                       | Effect                                                          |
|------------------------------|-----------------------------------------------------------------|
| `^Word^`                     | Accent word in H1 (Gradient from `--md-accent`)                 |
| `==Text==`                   | Highlight                                                       |
| `[[Text\|green]]`            | Badge (Presets: `purple` / `green` / `red` / `blue`)            |
| `::: cols-2 … +++ … :::`     | Column/Grid layout (see below; `+++` separates blocks)          |
| `::: html … :::`             | Raw HTML block: Content is passed through unchanged (see below) |
| Multiple spaces              | Preserved **within a line** (not collapsed)                     |
| `\t`                         | Tabulator (fixed horizontal space, repeatable: `\t\t`)          |
| `[sp=2em]`                   | Custom horizontal space with width (`px`/`em`/`rem`/`%`/`vw`)   |

**Layout Containers** (`:::`): Side-by-side columns.
`cols-2` / `cols-3` / `cols-4` (equal width), asymmetrical `cols-2-1` / `cols-1-2`
/ `cols-3-1` / `cols-1-3`, and `rows` (stacked boxes). `+++` separates the blocks.

Full width doesn't require a modifier — simply write content as **normal Markdown above/below** the `:::` block. Mixed layouts (e.g., a full heading with two columns below) are created by sequencing blocks, not by nesting them.

**Raw HTML** (`::: html … :::`): The entire content is inserted **without** Markdown parsing and without `<p>` wrapping — ideal for custom layouts, SVGs, timelines, or CSS animations. Example:

```
::: html
<div style="display:flex;gap:1rem">
  <div style="animation:pulse 2s infinite">Step 1</div>
</div>
<style>@keyframes pulse { 50% { opacity:.3 } }</style>
:::
```

⚠️ `<script>` tags will **not** be executed via `innerHTML`. For real JavaScript (interactive animations), use a dedicated `.html` file as a slide.

**Colored Info Box** = a single `::: rows` block with block attributes in the first line, e.g., `{bg=#13241f color=#86efac border=#22c55e}` + an emoji as an icon.

### Colors — Styling Individual Elements

|  Syntax                         | Effect                                                                          |
|---------------------------------|---------------------------------------------------------------------------------|
| `{#0af: Text}`                  | Custom **text** color inline (Hex or CSS name: `{tomato: …}`)                   |
| `==Text==`                      | Highlight (Accent background)                                                   |
| `[Text]{color=#fff bg=#7c6dfa}` | Inline span with text **and** background color (use `bg=` for a rounded pill)   |
| `[[Text\|#0af]]`                | Badge with custom color                                                         |
| `# Title {color=#ff6b6b}`       | Colorize heading (attributes at the end of the line)                            |

Colorizing a column block — add attributes to the **first line** of the block:

```
::: cols-2
  {bg=#1a1a2e color=#fff border=#333}
  Content …
:::
```

**Attribute Tokens** (space-separated): `.class`  `#hex`  `color=`  `bg=`
`border=`  `size=`

**Color Values:** Hex or single-word CSS names. For `rgb()` or values with spaces, please use Hex.
