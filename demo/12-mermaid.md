---
theme: dark
---

# Diagrams with Mermaid

A code block marked as `mermaid` is automatically rendered as a diagram.

```mermaid
flowchart LR
  A[Markdown File] --> B[Regex Parser]
  B --> C{File type?}
  C -->|.md| D[Theme Rendering]
  C -->|.html| E[iframe]
  D --> F[Slide]
  E --> F[Slide]
```
