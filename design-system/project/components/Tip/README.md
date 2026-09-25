# Tip

A one-line dark toast above the dock that confirms an action or teaches a gesture, gone after 3.5s.

- Markup: `<div class="qf-tip">…</div>`; one line, no wrap, no action button.
- Ground `tip-bg`, `radius-pill`, `tip` style. Bottom `110px` + safe area, centred; ignores pointer events; z-index `z-tip`.
- Copy is a plain statement: 「フレームを外しました」, 「この端末は動画撮影に対応していません」.
