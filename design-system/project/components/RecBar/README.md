# RecBar

The red pill under the top bar that counts recording seconds.

- Markup: `<div class="qf-recbar">● 録画中 <span>0.0</span> 秒</div>`; shown only while the shutter is `.is-rec`, updated every 100ms to one decimal.
- Ground `rec-pill`, `radius-pill`, `label` style. White on it is 3.7:1 — below AA for 12px text (kept as in source).
- Centred, top `64px` + safe area, z-index `z-recbar`.
