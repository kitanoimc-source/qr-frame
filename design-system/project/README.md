QR Frame is a one-screen mobile camera: a live camera fills the screen, a licensed character frame sits over it, stickers can be dropped on top, and one shutter takes a photo (tap) or a short video (hold). The UI is dark, small and pushed to the edges so the picture stays the subject; one hot pink marks everything that is "on".

## Content fundamentals

- **Language: Japanese only**, plain polite form. Instructions end in 「〜してください。」; confirmations are short statements in the past tense: 「スタンプを消しました」「フレームを外しました」.
- **Labels are nouns, 2–6 characters**: カメラ切替, リセット, 閉じる, フォトフレーム, スタンプ, 撮り直す, 保存・共有. No verbs-as-buttons in English, no exclamation marks in UI chrome.
- **Errors** (`Notice`): a bold headline that states the failure — 「カメラを起動できませんでした。」 — then the cause, then the fix: 「カメラの許可を確認してください。」「LINE等のアプリ内ブラウザで開いている場合は、SafariまたはChromeで開き直してください。」
- **Numbers** use half-width digits and a full-width separator for readouts: 「1440 × 2560 px　/　812 KB」, 「● 録画中 3.4 秒」.
- **Hints teach one gesture at a time**, once: 「長押しで録画」 under the shutter, 「角の ⤢ をドラッグで拡大・回転」 after the first stamp.
- No emoji. Symbols appear only as icons (see Iconography).

## Visual foundations

**Colour.** One theme, dark, because the screen is a viewfinder. Build every surface from the neutrals: `stage` under the camera, `bg` around it, `sheet` and `sheet-bar` for the picker, `result-bg` for the result. `pink` is the only accent and means selected / primary / live: the active tab, an active tool or mode, the shutter ring, the selected frame, the resize handle, the Save button. Never use `pink` for decoration or for text on dark grounds. Red has two jobs and they stay separate: `danger` (delete, error notice) and `rec` (recording). Everything that floats over the camera is translucent black or white (`scrim-top`, `tip-bg`, `mode-idle`, `mode-on`, `shutter-fill`) so the image shows through.

**Legibility over a live image.** Text placed directly on the camera always carries a text shadow (`text-shadow-label`, `text-shadow-caption`, `text-shadow-strong`) or sits on a translucent pill. Text on solid grounds uses `text` (or `tab-ink` / `dim` for secondary) — all ≥ 9:1. Known shortfalls kept from the source: white on `danger` and on `rec` is 3.7:1, and the `line` outline is 2.7:1 on `result-bg`.

**Type.** The platform's Japanese UI face: `-apple-system` / Hiragino Sans on iOS, Noto Sans JP elsewhere (`--font-sans`); no web font is loaded. Sizes are small and exact — 14.5 / 14 / 12.5 / 12 / 11.5 / 10 / 9.5px — because chrome must not compete with the photo. Weight 500 marks interactive labels (`tab`, `action`, `label`); 700 is only for glyphs and notice headlines.

**Layout.** Three layers, fixed to the viewport, stacked by the `z-*` tokens: the stage (camera + frame + stamps, optionally locked to 9:16), the edges (`TopBar` at the top, the dock with `ModeButton` · `Shutter` · `ModeButton` at the bottom), and transient layers (`BottomSheet`, `RecBar`, `Notice`, `Tip`, then the result screen at `z-result`). Respect `env(safe-area-inset-*)` on every edge element. The dock stays above the sheet; the sheet covers `size-sheet` (52%) and its grid pads `space-96` at the bottom.

**Spacing and size.** The spacing tokens are the source's actual values (2, 3, 4, 6, 8, 10, 12, 14, 16, 18, 26, 96px) — use them as named, don't round to a grid. Touch targets are at least `size-tool` (44px); the shutter is `size-shutter` (78px).

**Shape.** Corners grow with the object: `radius-4` frame thumbs, `radius-6` stamp thumbs and media, `radius-8` tools, `radius-10` notices, `radius-12` buttons. Round things are fully round: shutter, mode discs, stamp controls (`radius-circle`), tip and REC pill (`radius-pill`).

**Depth.** No elevation system. Two small shadows lift white or coloured controls off the image (`shadow-tool`, `shadow-ctl`); the sheet and result screen are flat. No gradients except the top-bar scrim.

**Motion and states.** The sheet slides up in .22s ease-out; the shutter scales to .95 when pressed; tips fade after 3.5s. On-state = `pink` fill or border; idle mode buttons dim to `opacity-mode-idle`. The selected stamp gets a 1.5px `select-dash` outline; deselect before every capture so it never lands in the output.

## Iconography

There is no icon font or SVG icon set: icons are single Unicode symbols set in the UI face — ⟳ camera flip, ▤ frames, ☺ stamps, ◉ shutter, ⊘ reset, ✕ close, × delete, ⤢ resize/rotate, ● recording. Size them with the glyph styles (`glyph-shutter` 26px, `glyph-mode` 19px, `glyph-tool` 17px bold, `glyph-handle` 15px bold) and colour them like text. Keep one symbol per meaning; add new ones from the same geometric Unicode blocks rather than mixing in an icon library.

## Imagery

- **Frames** (asset group `Frames`): licensed character art in top/bottom pairs; used untouched, full stage width.
- **Stamps** (asset group `Stamps`): the current seven are placeholders; real stamp art replaces them 1:1.
- There is no product logo in the source; the product name 「クレヨンしんちゃん QRサブレ」 is set as plain `label` text in the top bar.

## Not synced

- Components are static renditions styled by `components/bundle.css` (the app is plain HTML/JS with no component library, so there is no `bundle.js`).
- Not tokenised: the placeholder stamp art colours (inside the SVGs), the 5px/9px vertical paddings of `RecBar`/`Tip` and the 15px of the result buttons (single uses, left literal), fixed offsets (64/70/110px + safe area) and the .22s sheet transition.
