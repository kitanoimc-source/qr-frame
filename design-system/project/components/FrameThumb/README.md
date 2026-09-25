# FrameThumb

A 9:16 thumbnail that previews a frame pair — the top art pinned to the top, the bottom art to the bottom.

- Markup: `<button class="qf-fthumb"><img class="t" src="…ue.png"><img class="b" src="…shita.png"></button>`; `.is-on` for the applied frame.
- Well `thumb-bg`, corners `radius-4`, a transparent `border-thumb` that turns `pink` (with `thumb-on-bg`) when selected. The pink border alone is 2.5:1 on `sheet`; the tinted well carries the state too.
- The consumer supplies both halves from the `Frames` asset group; lazy-load them.
