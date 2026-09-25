# StampThumb

A square tile in the stamp grid; tapping it drops that stamp on the camera.

- Markup: `<button class="qf-sthumb"><img src="…"></button>`; the `pink` border shows only while pressed (`:active`, or `.is-pressed` in static renditions).
- `radius-6`, `space-3` padding, image `object-fit: contain`, no well colour.
- Stamps are added, not selected — there is no persistent on-state. The consumer supplies the images (CONFIG.stampTabs).
