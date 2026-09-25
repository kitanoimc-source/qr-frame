# BottomSheet

The picker that slides up over the lower 52% of the camera: a tab row, then a scrolling grid of thumbnails.

- Markup: `.qf-sheet` > `.qf-tabrow` (`.qf-sheet-btn` Reset · `.qf-tabs` of `.qf-tab` · `.qf-sheet-btn` Close) + `.qf-grid.is-frames` (4 columns) or `.qf-grid.is-stamps` (5 columns).
- Ground `sheet`; tab row `sheet-bar` with a `tabrow-border` rule. Active tab fills `pink`; idle tabs are `tab-ink`. Tabs scroll horizontally with no scrollbar.
- Opens with `transform: translateY(100%) → 0` over .22s ease-out. Height `size-sheet`; z-index `z-sheet`, always under the dock (`z-dock`).
- The grid keeps `space-96` bottom padding so its last row clears the dock.
- Reset (リセット) clears the current mode (remove frame / all stamps) and confirms with a `Tip`. The consumer supplies the tab names and the items (CONFIG.frameTabs / stampTabs).
