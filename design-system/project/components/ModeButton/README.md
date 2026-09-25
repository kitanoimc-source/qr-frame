# ModeButton

A frosted 48px disc with a caption that opens (or closes) the bottom sheet for one mode: frames or stamps.

- Markup: `<button class="qf-mode"><i>▤</i><span>フォトフレーム</span></button>`; `.is-on` while its sheet is open.
- Idle: whole button at `opacity-mode-idle`, disc `mode-idle`. On: full opacity, disc `mode-on`, glyph `tool-ink`.
- Sits in the dock either side of the `Shutter`. Tapping the active mode again closes the sheet.
