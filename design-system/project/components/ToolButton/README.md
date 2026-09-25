# ToolButton

A 44px white square with a one-glyph icon and a tiny caption, floating over the camera in the top bar.

- Markup: `<button class="qf-tool"><i>⟳</i><span>カメラ切替</span></button>`; add `.is-on` for a toggled tool (square turns `pink`, glyph `text`).
- The consumer supplies one glyph (a Unicode symbol, not an icon font) and a caption of at most two short lines (`caption-xs`, 9.5px).
- Only lives inside `TopBar`'s `.qf-tools` row, right-aligned, `space-8` apart. Today the app ships one: camera flip (カメラ切替).
- The caption relies on `text-shadow-caption` to read on the live image — never drop it.
