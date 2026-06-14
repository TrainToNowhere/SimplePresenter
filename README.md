# SimplePresenter

A standalone, browser-based presentation tool - a minimal replacement for "the other presentation tools". Each slide is a plain Markdown file. The whole engine is a single HTML file you open directly in your browser. No installation, no build step, no account, no cloud.

```
A folder of .md files  →  open simple-presenter.html  →  press F  →  present
```

---

## Why this exists

As a developer who just wants to present facts - with minimal configuration, a minimalist design, minimal effort and, above all, little time - I spent a long time looking for a simple tool. I never found one, so I built it myself.

## Quick start

1. Open **`simple-presenter.html`** in any modern browser.
2. Click **Open Folder** and pick a folder of slides.
3. Arrow keys to navigate, **`F`** for fullscreen.

Each file in the folder is one slide, loaded in filename order (`01-…`, `02-…`). Use `.md` for Markdown slides or `.html` for fully custom ones.

## See it in action

A complete, self-documenting demo deck lives in **[`demo`](demo)** - open that folder in the tool. It walks through every feature: all themes, layouts, column grids, colors, callouts, raw-HTML blocks, Mermaid diagrams, spacing, and an interactive `.html` slide.

## Syntax reference

The full Markdown syntax - frontmatter, extended markup, colors, layouts - is documented in **[`syntax-reference.md`](syntax-reference.md)**.