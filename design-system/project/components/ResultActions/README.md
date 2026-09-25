# ResultActions

The hint line and the two equal buttons under a captured photo or video: retake, or save/share.

- Markup: `.qf-rhint` then `.qf-ract` holding `button.qf-btn-secondary` (撮り直す, left) and `button.qf-btn-primary` (保存・共有, right).
- Buttons split the row equally, `radius-12`, `action` style, 15px vertical padding, `space-10` apart. Primary: `pink` fill; secondary: `border-hair` in `line` (2.7:1 on `result-bg`, kept as in source).
- Hint in `hint` style and `dim`: size · KB after capture, then a save instruction if sharing falls back to download.
- Save uses the Web Share API with the file when available, otherwise a download link named `qr-sable.jpg|mp4|webm`.
