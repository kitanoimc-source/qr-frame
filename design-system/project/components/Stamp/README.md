# Stamp

A placed sticker on the camera that the viewer drags, pinches and rotates; selected, it shows a dashed outline and two controls.

- Markup: `.qf-stamp` (absolute, width `size-stamp-base` at creation) > `img` + `.qf-ctl.del` (×) + `.qf-ctl.handle` (⤢). `.is-sel` shows the `select-dash` outline (`border-select`, inset −`space-6`, `radius-6`) and the controls.
- Controls: `size-ctl` discs on the top-left (delete, `danger`) and bottom-right (resize/rotate, `pink`) corners, `shadow-ctl`. They are counter-scaled and counter-rotated so they stay 34px and upright at any stamp scale.
- Scale is clamped 0.2–6. Tapping empty stage deselects. The first stamp shows the tip 「角の ⤢ をドラッグで拡大・回転」.
