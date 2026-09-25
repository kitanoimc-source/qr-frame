# Shutter

The 78px ring that takes a photo on tap and records video while held (450ms long-press, max 15s).

- Markup: `<button class="qf-shutter">◉</button>` plus the caption `.qf-shutter-cap` (長押しで録画) pinned under the dock.
- Idle: `shutter-fill` glass inside a `border-shutter` ring in `pink`. Recording: `.is-rec` — ring `rec`, fill `rec-fill`; show `RecBar` at the same time.
- Presses scale to .95. Deselect any stamp before capturing so the selection outline never lands in the output.
- One per screen, centred in the dock between two `ModeButton`s.
