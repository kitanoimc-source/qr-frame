# TopBar

The transparent strip across the top of the camera: product label on the left, tool buttons on the right.

- Markup: `.qf-topbar` > `.qf-label` + `.qf-tools` (holding `ToolButton`s).
- Background is a gradient from `scrim-top` to transparent so the label (`label` style, `text-shadow-label`) reads on any image; the bar itself ignores pointer events, its children take them.
- Padding: `space-8` + safe-area-inset-top, `space-12` sides, `space-26` bottom (the gradient tail). z-index `z-topbar`.
- The consumer supplies the label text (CONFIG.label) and the tools.
