# Notice

A red card over the camera for blocking errors: the camera won't start, the page isn't on HTTPS, or a frame image is missing.

- Markup: `<div class="qf-notice"><b>headline。</b><br>cause and remedy</div>`; it stays until the problem is solved (no timeout).
- Copy: a bold one-sentence headline ending in 。, then the cause, then what to do (「〜してください。」).
- Ground `notice-bg`, `radius-10`, `notice` style; inset `space-14` from both sides, top `70px` + safe area; z-index `z-notice`. White on it is 3.7:1 — below AA (kept as in source).
