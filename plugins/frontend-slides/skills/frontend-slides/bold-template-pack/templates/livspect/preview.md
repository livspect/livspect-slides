# Livspect Preview Card

Use this small file for title-slide previews only. For final deck generation, read the full design doc listed below.

## Files

- Full design doc: `bold-template-pack/templates/livspect/design.md`
- Preview card: `bold-template-pack/templates/livspect/preview.md`

## Selection Metadata

- Slug: `livspect`
- Tagline: Paper-white corporate editorial with hairline rules, mono index numerals, and a single orange point of accent.
- Mood: restrained, structural, corporate, precise
- Tone: professional, quiet, engineering-adjacent, trustworthy
- Formality: high
- Density: medium
- Scheme: light
- Best for: Japanese-first business documents — client proposals, service overviews, pricing and comparison decks, project reports, consulting deliverables, internal strategy reviews. Built for mixed Japanese/English content and for any deck that has to carry the Livspect brand.
- Avoid for: Decks that need visual energy, color-led storytelling, illustration, or playfulness. Also a poor fit for anything that should not read as Livspect-branded, since the wordmark and the orange accent are structural to the system.

## Visual Snapshot

The Livspect corporate design language rendered as a presentation system. Paper white, deep ink, near-invisible hairlines. Inter Tight carries every Latin headline; Zen Kaku Gothic New carries Japanese; JetBrains Mono handles index numerals and structural labels. There is exactly one chromatic accent — Livspect orange — and it is never a fill. It appears only as a point: the asterisk in the wordmark, a 4px dot before a label, a hover underline.

Structure is carried entirely by 1px hairline rules, vertical column divides, and zero-padded two-digit index numbers. There are no cards, no rounded filled panels, no shadows, no gradients. A grid cell is a hairline on top, a numeral, a title, and a paragraph — nothing more. The default call to action is a hairline-underlined text link with a trailing arrow, not a filled button.

## Preview Ingredients

- Palette: paper-white #FFFFFF; paper-warm #FAFAF9; ink-black #0A0A0A; ink-muted #6B6B68; ink-subtle #6F6F6D; hairline #E7E7E4; orange #FF5A00; orange-tint #FFF4ED
- Typography: Inter Tight; Zen Kaku Gothic New; JetBrains Mono
- Signature move: Paper-white background on every slide. No dark variant exists.
- Signature move: Brand orange appears only as a point or a 32px hairline — the wordmark asterisk, a 4px dot, a short rule before a kicker, a hover state. Never a fill.
- Signature move: Multi-part content is numbered 01, 02, 03 in JetBrains Mono instead of bulleted, iconed, or badged.
- Signature move: Columns are separated by 1px vertical hairlines and padding alone; the last column carries no rule.
- Signature move: One 32px rule per slide — black beneath a headline, or orange to the left of a mono kicker, as in the corporate lockup.
- Signature move: An optional faint hairline grid across the title slide only.
- Signature move: The Livspect wordmark — L, dotless ı, vspect — with an orange asterisk as the i-dot, set in the chrome band.

## Logo

The title slide and every content slide carry the Livspect wordmark. Render it as HTML, not as an image:

```html
<span class="lv-wordmark" aria-label="Livspect">
  <span aria-hidden="true">L</span><span class="lv-i" aria-hidden="true">&#x131;<span class="lv-ast">*</span></span><span aria-hidden="true">vspect</span>
</span>
```

The asterisk is anchored to the dotless ı itself — `position: absolute; left: 50%; transform: translateX(-50%); top: -0.26em; font-size: 0.6em` in `#FF5A00` — so it stays centered at any size. The letters are `#0A0A0A`. See the design doc for the full CSS.

On a title slide the wordmark may run at weight 700 and up to 5vw, paired with a 32px orange rule and a mono kicker. Raster fallbacks live in `assets/logo/`.

## International / CJK Preview Note

- Japanese is the primary language of this system, not a fallback. Keep every CJK run at `letter-spacing: 0`, loosen line-height, and never apply uppercase transforms or monospace to Japanese.
- Japanese headlines use weight 500, not 600.
- Use the full `design.md` CJK section after selection for exact pairings and adjustments.

## Preview Rules

- Build exactly one title slide at 1920x1080 inside the fixed-stage model.
- Preserve the palette, type roles, hairline structure, and accent budget described above.
- Use the user's real title/subtitle/context; do not copy demo slide content.
- The rendered preview must look like a real first slide, not a template-selection card.
- Never place internal workflow text on the slide: no `preview`, `generated from`, `preview.md`, `template`, `preset`, `style option`, `Option A/B/C`, file names, paths, or source-doc labels.
- Never place the template name or slug on the slide itself; mention it only in the chat message.
