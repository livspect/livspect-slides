# Livspect Logo Assets

| File | What it is | Use |
|---|---|---|
| `livspect-mark.png` | The calligraphic *Liv* monogram with the asterisk above the i. 1080×1080, black on white. | Favicon-scale mark. Closing slides, watermarks, a corner mark where the full wordmark is too wide. |
| `livspect-mark-256.png` | The same monogram at 256×256. | Small-scale placements. |
| `livspect-lockup.png` | The full brand lockup: the **Lıvspect** wordmark with the orange asterisk as the i-dot, over a faint hairline grid, with the mono kicker `THE OS FOR LOCAL INNOVATION` preceded by a short orange rule. 1200×630. | Reference for the brand's proportions and accent budget. Not for dropping directly onto a slide.

## Prefer the HTML lockup

For decks, build the wordmark in HTML rather than placing a raster file. It stays crisp at any stage scale, needs no asset loading, inherits the slide's ink color, and matches the corporate site exactly. The markup and CSS are in `bold-template-pack/templates/livspect/design.md` under **Logo**.

Use the raster files only where the calligraphic monogram is wanted as a mark, or when a deck has to be exported to a format that cannot carry the live type.

## Constraints

- The asterisk is the only orange element in the lockup. The letters are always `#0A0A0A` on light surfaces.
- Never letter-space the wordmark open, never uppercase it, never place it inside a box or on an orange field.
- Never recolor the monogram. If it has to sit on a dark ground, use the deck's own ink/paper inversion rather than an orange or tinted variant.
