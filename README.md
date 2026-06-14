# SimplePresenter

**One idea. One file. No ballast.**

A standalone, browser-based presentation tool — a deliberately minimal replacement for "the other presentation tools". Each slide is a plain Markdown file. The whole engine is a single HTML file you open directly in your browser. No installation, no build step, no account, no cloud.

```
A folder of .md files  →  open simple-presenter.html  →  press F  →  present
```

---

## Why this exists

Classic presentation software feels like it's from another era: the same templates everywhere, a UI concept from the 2000s, and hours spent fighting layout instead of thinking about content.

The modern, developer-oriented tools don't really fix this — they overcorrect. Frameworks are powerful, but **overloaded**: dozens of features, configuration layers, plugins and conventions. You spend your energy operating the tool and reading its documentation, and the focus on what actually matters — the content — quietly slips away. Worse, all that flexibility rarely adds up to a coherent result: there is no clear line, no single, clean, minimal design language that makes a deck look considered and points attention at the facts of the presentation instead of at decoration.

SimplePresenter starts from the opposite end. **A presentation should emerge from its content — not from clicking around, and not from configuring a framework.** You write Markdown; a small, opinionated set of themes does the rest. The design is deliberately restrained, consistent across every slide, and built to keep the eye on the message. There is almost nothing to learn and almost nothing to decide — which is exactly the point. Write. Done.

## How it's different

| | Typical tools | SimplePresenter |
|---|---|---|
| **Setup** | Install / sign up / cloud | Open one HTML file |
| **Source of truth** | Opaque binary / proprietary doc | Plain text Markdown, diff-able, versionable |
| **Design** | Manual, per-slide busywork | Automatic from themes + a tiny markup |
| **Dependencies** | Heavy | One file (Mermaid/fonts via CDN) |
| **AI-friendliness** | Awkward | A slide *is* Markdown — an AI can write it directly |

That last point is the real unlock: because a slide is nothing but Markdown, an agent can generate an entire deck in seconds — "make me the review slides for this sprint" → finished files → open the folder and present.

## Why it's built this way

- **Single file** — `simple-presenter.html` is the entire app: HTML, CSS, and a custom regex-based Markdown parser in one document. Copy it anywhere and it runs.
- **No framework, no build** — nothing to compile, nothing to update, nothing to break. It will still open in ten years.
- **Plain Markdown with a light extension layer** — themes, color accents, and column grids are expressed in a few extra tokens, never in a GUI.
- **Tailor-made, not off-the-shelf** — it does exactly what's needed and nothing more. It was built in an afternoon, which is rather the point: software can now be shaped precisely around your own needs in very little time.

## Quick start

1. Open **`simple-presenter.html`** in any modern browser.
2. Click **Open Folder** and pick a folder of slides.
3. Arrow keys to navigate, **`F`** for fullscreen.

Each file in the folder is one slide, loaded in filename order (`01-…`, `02-…`). Use `.md` for Markdown slides or `.html` for fully custom ones.

## See it in action

A complete, self-documenting demo deck lives in **[`demo`](demo)** — open that folder in the tool. It walks through every feature: all themes, layouts, column grids, colors, callouts, raw-HTML blocks, Mermaid diagrams, spacing, and an interactive `.html` slide.

## Syntax reference

The full Markdown syntax — frontmatter, extended markup, colors, layouts — is documented in **[`syntax-reference.md`](syntax-reference.md)**.