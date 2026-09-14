---
version: alpha
name: Livspect (Hairline Editorial)
description: The Livspect corporate design language rendered as a presentation system. Paper white, deep ink, near-invisible hairlines. Inter Tight carries every headline; Zen Kaku Gothic New carries Japanese; JetBrains Mono handles numbers and structural labels. There is exactly one chromatic accent — Livspect orange — and it is never a fill. It appears only as a point: the asterisk in the wordmark, a 4px dot before an eyebrow label, a hover state. Structure comes from 1px hairline rules, vertical column divides, and two-digit index numbers. No boxes, no rounded filled cards, no shadows.

colors:
  paper-white: "#FFFFFF"
  paper-warm: "#FAFAF9"
  paper-muted: "#F6F6F5"
  ink-black: "#0A0A0A"
  ink-muted: "#6B6B68"
  ink-subtle: "#6F6F6D"
  hairline: "#E7E7E4"
  hairline-faint: "#EFEFEC"
  orange: "#FF5A00"
  orange-ink: "#F15400"
  orange-tint: "#FFF4ED"
  orange-deep: "#9A3412"

color-aliases:
  c-bg: paper-white
  c-bg-light: paper-white
  c-bg-cream: paper-warm
  c-fg: ink-black
  c-fg-light: ink-black
  c-fg-2: ink-muted
  c-fg-3: ink-subtle
  c-accent: orange
  c-border: hairline
  c-border-light: hairline-faint

typography:
  display:
    fontFamily: "Inter Tight, Zen Kaku Gothic New, system-ui, sans-serif"
    fontSize: 7.5vw
    fontWeight: 600
    lineHeight: 0.98
    letterSpacing: -0.035em
  h1:
    fontFamily: "Inter Tight, Zen Kaku Gothic New, system-ui, sans-serif"
    fontSize: 4.6vw
    fontWeight: 600
    lineHeight: 1.08
    letterSpacing: -0.03em
  h2:
    fontFamily: "Inter Tight, Zen Kaku Gothic New, system-ui, sans-serif"
    fontSize: 3vw
    fontWeight: 600
    lineHeight: 1.18
    letterSpacing: -0.02em
  h3:
    fontFamily: "Inter Tight, Zen Kaku Gothic New, system-ui, sans-serif"
    fontSize: 1.9vw
    fontWeight: 600
    lineHeight: 1.35
    letterSpacing: -0.01em
  lead:
    fontFamily: "Inter Tight, Zen Kaku Gothic New, system-ui, sans-serif"
    fontSize: 1.45vw
    fontWeight: 400
    lineHeight: 1.75
    letterSpacing: 0
  body:
    fontFamily: "Inter Tight, Zen Kaku Gothic New, system-ui, sans-serif"
    fontSize: 1.05vw
    fontWeight: 400
    lineHeight: 1.85
    letterSpacing: 0
  caption:
    fontFamily: "Inter Tight, Zen Kaku Gothic New, system-ui, sans-serif"
    fontSize: 0.82vw
    fontWeight: 400
    lineHeight: 1.7
    letterSpacing: 0
  label:
    fontFamily: "JetBrains Mono, monospace"
    fontSize: 0.7vw
    fontWeight: 500
    lineHeight: 1.4
    letterSpacing: 0.14em
    textTransform: uppercase
  quote:
    fontFamily: "Inter Tight, Zen Kaku Gothic New, system-ui, sans-serif"
    fontSize: 2.4vw
    fontWeight: 400
    lineHeight: 1.6
    letterSpacing: -0.015em
  stat-value:
    fontFamily: "Inter Tight, Zen Kaku Gothic New, system-ui, sans-serif"
    fontSize: 5.2vw
    fontWeight: 600
    lineHeight: 1.0
    letterSpacing: -0.04em
  flow-num:
    fontFamily: "JetBrains Mono, monospace"
    fontSize: 0.95vw
    fontWeight: 400
    lineHeight: 1.0
    letterSpacing: 0.06em
  wordmark:
    fontFamily: "Inter Tight, system-ui, sans-serif"
    fontSize: 1.15vw
    fontWeight: 600
    lineHeight: 1.0
    letterSpacing: -0.02em

spacing:
  pad-x: 7vw
  pad-y: 6.5vh
  gap-lg: 5.5vh
  gap-md: 3vh
  gap-sm: 1.4vh

canvas:
  width: 100vw
  height: 100vh

components:
  rule-full:
    width: "100%"
    height: 1px
    background: "{colors.hairline}"
    description: "The system's primary structural element. A near-invisible full-width hairline. Used for section divides, chrome bands, table rows, and the top edge of every indexed cell. Never thicker than 1px, never darker than {colors.hairline}."
  rule-ink:
    width: 32px
    height: 1px
    background: "{colors.ink-black}"
    description: "A short 32px black rule. The only high-contrast rule in the system. Used once per slide at most, as punctuation beneath a display headline or above a stat block."
  vrule:
    width: 1px
    height: "100%"
    background: "{colors.hairline}"
    description: "Vertical hairline that divides a multi-column grid. Columns are separated by this rule and padding alone — never by a background fill or a border box. The last column carries no right rule."
  eyebrow:
    fontFamily: "{typography.label.fontFamily}"
    fontSize: "{typography.label.fontSize}"
    letterSpacing: 0.14em
    textTransform: uppercase
    color: "{colors.ink-subtle}"
    description: "Mono uppercase label above a headline, optionally preceded by {components.orange-dot}. Latin only — never set Japanese in this component (see Typography Principles)."
  eyebrow-ja:
    fontFamily: "{typography.caption.fontFamily}"
    fontSize: "{typography.caption.fontSize}"
    letterSpacing: 0
    color: "{colors.ink-subtle}"
    description: "The Japanese counterpart to {components.eyebrow}. Sans, not mono; no uppercase transform; letter-spacing strictly 0."
  orange-dot:
    width: 4px
    height: 4px
    borderRadius: 50%
    background: "{colors.orange}"
    description: "A 4px orange point. The system's signature accent and, together with the wordmark asterisk, one of only two places the brand orange is allowed to appear at full saturation."
  rule-accent:
    width: 32px
    height: 1px
    background: "{colors.orange}"
    description: "A 32px orange hairline sitting immediately to the left of an eyebrow label, separated by about 1.2em. Taken directly from the corporate lockup. This and {components.orange-dot} are alternatives, not companions — a slide uses one or the other, never both."
  grid-field:
    background: "transparent"
    description: "An optional faint hairline grid across the title slide, drawn in {colors.hairline} at roughly 160px pitch via two repeating-linear-gradients. Title and section-break slides only; never behind body copy or a table. It is an absolutely-positioned first child at z-index 0, with the slide's other children raised to z-index 1 — if a later rule sets those children to position: relative, make sure it does not also catch the grid layer and collapse it."
  asterisk:
    content: "*"
    color: "{colors.orange}"
    fontFamily: "{typography.wordmark.fontFamily}"
    description: "The Livspect asterisk. Sits as the i-dot above the dotless ı in the wordmark, and may stand alone as a slide-corner mark or a footnote reference. Always {colors.orange}, never any other color."
  wordmark:
    fontFamily: "{typography.wordmark.fontFamily}"
    fontWeight: 600
    letterSpacing: -0.02em
    description: "The Livspect lockup: the letters L, ı (U+0131 dotless i), v, s, p, e, c, t set in Inter Tight semibold, with {components.asterisk} positioned absolutely above the ı as its dot. See the Logo section for exact markup and offsets."
  index-num:
    fontFamily: "{typography.flow-num.fontFamily}"
    fontSize: "{typography.flow-num.fontSize}"
    color: "{colors.ink-subtle}"
    description: "A zero-padded two-digit index (01, 02, 03) in JetBrains Mono. Sits at the top-left of a grid cell, directly under that cell's {components.rule-full}. The system's counting voice — it replaces bullets, icons, and badges."
  indexed-cell:
    borderTop: "1px solid {colors.hairline}"
    padding: "{spacing.gap-md} 2.2vw {spacing.gap-md} 0"
    description: "The workhorse layout unit. A hairline-topped column with an {components.index-num} at the top, an h3 title, and a body paragraph. Cells sit side by side separated by {components.vrule}. No background, no border box, no radius."
  bullet-marker:
    content: "—"
    color: "{colors.ink-subtle}"
    fontFamily: "{typography.label.fontFamily}"
    description: "An em-dash in muted ink via JetBrains Mono. The standard list mark. Never a dot, never a check, never an arrow, never an emoji."
  stat-cell:
    borderTop: "1px solid {colors.hairline}"
    padding: "{spacing.gap-md} 2vw {spacing.gap-md} 0"
    description: "Hairline-topped cell holding a 5.2vw semibold numeral, a sans label beneath it, and an optional mono source note. The numeral is always {colors.ink-black} — a stat is never orange."
  link-rule:
    borderBottom: "1px solid {colors.hairline}"
    color: "{colors.ink-black}"
    description: "The system's link and CTA form: label text plus a trailing arrow glyph, sitting on a hairline underline. On hover the underline becomes {colors.orange} and the arrow shifts 4px right. This is the default call to action."
  btn-solid:
    background: "{colors.ink-black}"
    color: "{colors.paper-white}"
    borderRadius: 2px
    padding: "0.9em 1.8em"
    description: "The single permitted filled button: black on white, 2px radius. Use at most once per deck, on a closing or contact slide. An orange filled button does not exist in this system."
  table-row:
    borderBottom: "1px solid {colors.hairline}"
    padding: "{spacing.gap-sm} 0"
    description: "A hairline-separated table row. The final row drops its bottom border. Column headers are set in {components.eyebrow} or {components.eyebrow-ja}; there is no header fill and no zebra striping."
  img-frame:
    border: "1px solid {colors.hairline}"
    background: "{colors.paper-muted}"
    color: "{colors.ink-subtle}"
    borderRadius: 0
    description: "Hairline-bordered image region with a centered mono label while empty. Square corners. Images are never rounded and never shadowed."
  accent-band:
    background: "{colors.orange-tint}"
    color: "{colors.orange-deep}"
    description: "The one permitted orange surface: a very pale tint used behind a short callout or a single emphasized table row. Text on it must be {colors.orange-deep}, never {colors.orange}. Use at most once per deck."
---

## Frontend Slides Fixed-Stage Policy

When this design system is used by the `frontend-slides` skill, generate the final deck as a **fixed 1920×1080 stage** that scales uniformly to the browser viewport. The deck should preserve a 16:9 slide canvas on every screen, including phones; it may letterbox or pillarbox, but it should not reflow slide content for mobile.

This policy has higher priority than any responsive behavior described later in this file. The `vw` and `vh` values in the token block are design proportions to translate into 1920×1080 stage coordinates, not live responsive rules in the generated deck.

Use `deck-stage.js` or an equivalent inline stage scaler for final output: render each slide at 1920×1080, scale the whole stage with one transform, and verify rendered screenshots for both text overflow and panel overlap.

## Overview

Livspect (Hairline Editorial) is the presentation form of the Livspect corporate design language. It is a **structural** system rather than a decorative one: every piece of visual organization is carried by a 1px hairline, a vertical column divide, a two-digit index number, or whitespace. Nothing is carried by a fill, a shadow, a gradient, or a border box.

The system has exactly one chromatic accent, **Livspect orange** (`{colors.orange}`), and the rule governing it is the single most important constraint in this document: **orange is a point, never a fill.** It appears as the asterisk in the wordmark, as a 4px dot before a label, as a hover underline, and — at most once in a deck — as a very pale tint band. An orange headline, an orange filled button, an orange panel, or an orange chart series at full saturation all break the system.

The typeface stack is three voices. **Inter Tight** at weights 400, 500, and 600 carries every Latin display, headline, and body. **Zen Kaku Gothic New** at weights 400 and 500 carries every Japanese run; it is the second family in the same stack, so mixed Japanese/English lines resolve automatically. **JetBrains Mono** at weights 400 and 500 carries index numbers, Latin eyebrow labels, axis labels, dates, and footer chrome — never Japanese.

The palette is paper and ink. **Paper white** (`{colors.paper-white}`) is the default surface; **paper warm** (`{colors.paper-warm}`) is a barely-perceptible alternate used to tonally group a run of slides. **Ink black** (`{colors.ink-black}`) is every headline and every piece of primary copy. Two muted inks handle secondary and tertiary text. Two hairline tones handle every divider. That is the entire system apart from the four orange tokens.

**Density philosophy: sparse to medium.** The horizontal padding is 7vw and content typically occupies the middle 70% of the canvas. The system tolerates a dense slide — a five-column comparison, a ten-row table — because the rules are so thin and the type so evenly weighted that density still reads as orderly. But its best register is a single semibold headline against a large empty field, with one short black rule beneath it.

**Key Characteristics:**
- Paper-white background on every slide. Never a dark deck, never a colored slide.
- Structure is hairline rules and vertical column divides. There are no cards, no boxes, no rounded filled panels, no shadows.
- Grid cells are indexed with zero-padded mono numerals (01, 02, 03) instead of bullets, icons, or badges.
- Brand orange appears only as a point or a 32px hairline: the wordmark asterisk, a 4px dot, a short rule before an eyebrow, a hover underline, one pale tint band per deck.
- The default call to action is a hairline-underlined text link with a trailing arrow, not a filled button.
- Japanese text is never given wide letter-spacing, never uppercased, and never set in mono.
- The bullet marker is an em-dash in muted ink. No emoji appears anywhere in the deck, ever.
- Border radius is effectively zero: 2px on the single solid button, 0 everywhere else.

## Logo

The Livspect wordmark is the letters **L ı v s p e c t** — with U+0131 LATIN SMALL LETTER DOTLESS I in the second position — set in Inter Tight semibold at `letter-spacing: -0.02em`, with an orange asterisk placed as the i-dot above the ı.

```html
<span class="lv-wordmark" aria-label="Livspect">
  <span aria-hidden="true">L</span><span class="lv-i" aria-hidden="true">&#x131;<span class="lv-ast">*</span></span><span aria-hidden="true">vspect</span>
</span>
```

```css
.lv-wordmark {
  position: relative;
  display: inline-flex;
  align-items: baseline;
  font-family: var(--font-wordmark);
  font-weight: 600;
  letter-spacing: -0.02em;
  line-height: 1;
  color: var(--c-fg);
}
/* Anchor the asterisk to the dotless i itself, not to the whole wordmark,
   so it stays centered at any font size or weight. */
.lv-i   { position: relative; display: inline-block; }
.lv-ast {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  top: -0.26em;          /* ink sits just above the cap line */
  font-size: 0.6em;
  line-height: 1;
  color: var(--c-accent);
}
```

These offsets are measured against the corporate lockup in Inter Tight at weights 600 and 700 and hold across the whole size range used in a deck. Do not swap them for a hardcoded `left` on the wordmark — anchoring to the `ı` is what keeps the asterisk centered when the size or weight changes.

Placement rules:
- The wordmark sits in the **bottom-left or top-left chrome band** of content slides at `{typography.wordmark.fontSize}`, paired with a slide number or a date on the opposite side.
- On the title slide it may appear larger, in the upper-left, at up to 2vw. It never appears centered and never appears more than once on a slide.
- The asterisk is the **only** part of the lockup that is orange. The letters are always `{colors.ink-black}` on light surfaces.
- The asterisk is centered by `left: 50%; transform: translateX(-50%)` on the `ı` wrapper, so it needs no per-size tuning. If a different face is ever substituted, re-check `top` — an asterisk floating clear of the cap line, or colliding with the line above, reads as a typo rather than a mark.
- Never letter-space the wordmark open, never uppercase it, never place it inside a box or on an orange field.

### Raster assets

`assets/logo/` in this repository carries the brand files: `livspect-mark.png` (the calligraphic *Liv* monogram with its asterisk, 1080×1080 black on white), `livspect-mark-256.png` (the same at small scale), and `livspect-lockup.png` (the full reference lockup). Use the monogram where a compact mark is wanted — a closing slide, a corner watermark. Prefer the HTML wordmark everywhere else, since it stays crisp at any stage scale, inherits the slide's ink color, and needs no asset loading.

### Title-slide lockup

On a title slide the wordmark may run at weight 700 and up to 5vw, paired with `{components.rule-accent}` and a mono kicker set in `{components.eyebrow}`, over an optional `{components.grid-field}`. This reproduces the corporate lockup and is the strongest opening the system has. Keep the asterisk orange and everything else ink.

## Colors

### Palette

- **Paper White** (`{colors.paper-white}` — #FFFFFF): The default slide surface. Pure white, deliberately — this system is not warm-paper, it is clean-sheet.
- **Paper Warm** (`{colors.paper-warm}` — #FAFAF9): A near-imperceptible warm off-white. Used to tonally identify a group of slides (a case-study run, an appendix) without introducing a second visual language.
- **Paper Muted** (`{colors.paper-muted}` — #F6F6F5): Slightly deeper neutral. The fill for empty image frames and, rarely, an inset region. Never used as a card background behind text.
- **Ink Black** (`{colors.ink-black}` — #0A0A0A): Every headline, every piece of primary body copy, the short accent rule, and the single solid button. Near-black rather than pure black.
- **Ink Muted** (`{colors.ink-muted}` — #6B6B68): Secondary copy. Lead paragraphs beneath a headline, supporting text inside an indexed cell.
- **Ink Subtle** (`{colors.ink-subtle}` — #6F6F6D): Tertiary text. Eyebrow labels, index numerals, bullet markers, axis labels, footer chrome, source notes. Both muted inks clear WCAG AA 4.5:1 on white and on paper-warm.
- **Hairline** (`{colors.hairline}` — #E7E7E4): The default divider. Section rules, column divides, table rows, cell tops.
- **Hairline Faint** (`{colors.hairline-faint}` — #EFEFEC): An even quieter divider for dense interiors — the rows of a ten-row table, the gridlines behind a chart.
- **Orange** (`{colors.orange}` — #FF5A00): The brand accent. Permitted uses are exhaustively: the wordmark asterisk, a 4px dot, a 32px `{components.rule-accent}` before an eyebrow, a hover underline or hover arrow, a single emphasized data point in a chart. Nothing else.
- **Orange Ink** (`{colors.orange-ink}` — #F15400): A hair deeper, for the rare run of orange *text*. Inline emphasis at large sizes uses this token so it clears 3:1 contrast; `{colors.orange}` itself is for graphic marks only.
- **Orange Tint** (`{colors.orange-tint}` — #FFF4ED): The one permitted orange surface. A pale wash behind one short callout or one emphasized table row, once per deck.
- **Orange Deep** (`{colors.orange-deep}` — #9A3412): The required text color on `{colors.orange-tint}`. Never set orange-tint text in `{colors.orange}`.

### Defaults

- **Default surface background**: `{colors.paper-white}`. The system is single-surface by default and has no dark mode.
- **Default headline color**: `{colors.ink-black}`. Headlines are never orange and never muted.
- **Default body text color**: `{colors.ink-black}` for primary copy; `{colors.ink-muted}` for lead and supporting paragraphs.
- **Default eyebrow / label color**: `{colors.ink-subtle}`.
- **Default border / divider color**: `{colors.hairline}`, at 1px. `{colors.hairline-faint}` for dense interiors.
- **Default accent**: `{colors.orange}`, used as a point only.
- **Default chart palette**: `{colors.ink-black}` for the primary series, `{colors.ink-subtle}` at reduced opacity for comparison series, and `{colors.orange}` for exactly one highlighted value. A chart with three ink tones and one orange point is correct; a chart with four colored series is not.

There is no semantic color in this system — no red for warning, no green for success. Emphasis comes from weight, size, position, and the orange point.

## Typography

### Font Family

The deck loads three families from Google Fonts: **Inter Tight** (400, 500, 600), **Zen Kaku Gothic New** (400, 500), and **JetBrains Mono** (400, 500).

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter+Tight:wght@400;500;600&family=Zen+Kaku+Gothic+New:wght@400;500&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

Set `display=swap` and do not preload individual font files — the deck must render readable text before the webfonts arrive.

The emotional register:
- **Inter Tight** reads as *precise, current, engineering-adjacent*. Tightly spaced at negative tracking, it gives headlines density without shouting.
- **Zen Kaku Gothic New** reads as *clean and even*. It is a modern Japanese gothic with generous counters that holds up at both display and body size, and it sits comfortably next to Inter Tight without a weight mismatch.
- **JetBrains Mono** reads as *indexical*. It is the counting and labeling voice: 01, 02, 03, dates, axis ticks, slide numbers.

### Type Scale

| Token | Size | Family | Weight | Use |
|---|---|---|---|---|
| `{typography.display}` | 7.5vw | Inter Tight | 600 | Title-slide display line |
| `{typography.h1}` | 4.6vw | Inter Tight | 600 | Section-break headline |
| `{typography.h2}` | 3vw | Inter Tight | 600 | Content-slide headline |
| `{typography.stat-value}` | 5.2vw | Inter Tight | 600 | Large numeral in a stat cell |
| `{typography.quote}` | 2.4vw | Inter Tight | 400 | Pull-quote body |
| `{typography.h3}` | 1.9vw | Inter Tight | 600 | Cell title, sub-headline |
| `{typography.lead}` | 1.45vw | Inter Tight | 400 | Lead paragraph beneath a headline |
| `{typography.wordmark}` | 1.15vw | Inter Tight | 600 | The Livspect lockup in chrome |
| `{typography.body}` | 1.05vw | Inter Tight | 400 | Body copy, list items, table cells |
| `{typography.flow-num}` | 0.95vw | JetBrains Mono | 400 | Index numerals (01, 02, 03) |
| `{typography.caption}` | 0.82vw | Inter Tight | 400 | Captions, Japanese eyebrow labels, source notes |
| `{typography.label}` | 0.7vw | JetBrains Mono | 500 | Latin eyebrow labels, axis labels, chrome |

### Defaults

- **Default headline token**: `{typography.h2}`. Reserve `{typography.h1}` for section breaks and `{typography.display}` for the title slide.
- **Default body token**: `{typography.body}` at `{colors.ink-black}`; `{typography.lead}` at `{colors.ink-muted}` for the paragraph directly under a headline.
- **Default eyebrow**: `{components.eyebrow}` for Latin, `{components.eyebrow-ja}` for Japanese. Choosing the wrong one is the most common way to break this system.
- **Default line length**: 32–44 Latin characters, or 24–34 Japanese characters, per line in body copy. Wider than that and the 1.85 line-height stops doing its job.
- **Weight range**: 400, 500, 600. There is no 300 in this system, and 700 appears in exactly one place — the wordmark when set large on a title or closing slide, where the corporate lockup runs heavier than the chrome-band version. Body and headline type never reaches 700.

### Signature Treatments

- **Negative tracking on large Latin type.** Display and h1 sit at −0.03em and −0.035em. This is what makes the headlines read as Livspect rather than as default Inter.
- **Zero tracking on Japanese, always.** See Typography Principles below. This is a hard rule, not a preference.
- **Mono uppercase for Latin structure.** `{components.eyebrow}` at 0.14em tracking is the only place uppercase appears.
- **Two-digit index numerals.** Every multi-part grid, list, or flow is numbered 01, 02, 03 in mono. The numbering is the ornament.
- **One short rule per slide.** Either `{components.rule-ink}` in black beneath a display headline, or `{components.rule-accent}` in orange to the left of an eyebrow label. Both are 32px and 1px. A slide gets one, not two.
- **The orange rule is the lockup's own gesture.** The corporate lockup pairs a 32px orange rule with a mono kicker; reproducing that pairing on a title slide is the most recognizably Livspect move available.

### Typography Principles

1. **Never apply wide letter-spacing to Japanese text.** Japanese set at `letter-spacing: 0.1em` or wider looks unfinished, not elegant. Every Japanese run — headline, body, label, caption — sits at `letter-spacing: 0`. The negative tracking on the Latin display tokens applies to Latin runs; when a headline is Japanese, set its tracking to 0 and let the h2 size carry it.
2. **Never uppercase Japanese and never set it in mono.** `text-transform: uppercase` is a no-op on kana and kanji but will wreck any Latin words mixed into the line. JetBrains Mono has no Japanese coverage, so a mono Japanese label silently falls back to a system font and breaks the page.
3. **Never use an emoji.** Not in headlines, not in bullets, not in chrome, not as an icon substitute. The bullet marker is `{components.bullet-marker}`.
4. **Set numerals in mono when they are structure, in Inter Tight when they are content.** An index (01) or a date (2026.09) is mono. A statistic (¥1.2億) is Inter Tight semibold at `{typography.stat-value}`.

## Layout

### Canvas System

Every slide is a 1920×1080 stage with `{spacing.pad-x}` horizontal padding and `{spacing.pad-y}` vertical padding. Inside that, content is organized on a 12-column implicit grid with vertical hairline divides between column groups.

The three recurring layouts:
- **Anchored headline.** Eyebrow, headline, short black rule, lead paragraph — all left-aligned, occupying roughly the left 60% of the canvas, with the right 40% deliberately empty or holding a single image frame. The system's default and best slide.
- **Indexed grid.** Two to five `{components.indexed-cell}` units side by side, separated by `{components.vrule}`, each hairline-topped, each opening with an index numeral. This carries services, principles, phases, and comparison content.
- **Hairline table.** A header row in `{components.eyebrow}` / `{components.eyebrow-ja}`, then `{components.table-row}` rows. The last row drops its bottom border. Used for pricing, comparisons, and specifications.

### Padding and Gap Scale

| Token | Value | Use |
|---|---|---|
| `{spacing.pad-x}` | 7vw | Slide left/right padding |
| `{spacing.pad-y}` | 6.5vh | Slide top/bottom padding |
| `{spacing.gap-lg}` | 5.5vh | Between major slide regions |
| `{spacing.gap-md}` | 3vh | Between a headline and its lead, cell internal padding |
| `{spacing.gap-sm}` | 1.4vh | Between list items, table row padding |

Content is left-aligned by default. Centered layouts are reserved for the title slide and a single closing slide; a centered content slide reads as a different template.

### Chrome Frame

Content slides carry a bottom chrome band: a `{components.rule-full}` across the content width, and beneath it the `{components.wordmark}` on the left and a mono slide number and section name on the right, both at `{typography.label}` in `{colors.ink-subtle}`. The title slide and section breaks carry no chrome.

### Disabled Sidebar

This system has no persistent sidebar or side navigation rail. Section orientation comes from the section-break slide and the chrome band. Do not add a left navigation column.

## Depth and Elevation

### No Shadows, Hairline Rules Only

There are no `box-shadow` values anywhere in this system. When two regions need separation, a 1px `{colors.hairline}` rule divides them. When a region needs weight, it gets more padding — not a fill, not elevation.

**There are no cards.** A bordered, rounded, filled rectangle containing text is the single most out-of-system element you can add to a Livspect deck. What looks like a "card" in this system is a `{components.indexed-cell}`: hairline on top, index numeral, title, body, and nothing else — no side borders, no bottom border, no background, no radius.

### No Atmospheric Effects

No gradients, no blurs, no glows, no noise textures, no blend modes, no large decorative background shapes. The one permitted tinted surface is `{components.accent-band}`, used once per deck at most.

## Shapes and Treatment

### Border Radius

Effectively zero. `{components.btn-solid}` uses 2px; `{components.orange-dot}` is a circle. Everything else — image frames, tint bands, chart bars, table cells — is square-cornered.

### Border Weights

1px, always, in `{colors.hairline}` or `{colors.hairline-faint}`. The only exception is `{components.rule-ink}`, which is 1px in `{colors.ink-black}`. There is no 2px border, no 3px accent bar, no thick underline.

### Decorative Element Types

- `{components.rule-full}` — the default divider.
- `{components.rule-ink}` — the 32px black punctuation rule, once per slide.
- `{components.vrule}` — vertical column divide.
- `{components.orange-dot}` — the 4px orange point, before an eyebrow or beside a highlighted value.
- `{components.rule-accent}` — the 32px orange hairline before an eyebrow label.
- `{components.grid-field}` — the optional faint hairline grid, title and section-break slides only.
- `{components.asterisk}` — the Livspect asterisk, as the wordmark i-dot or a standalone corner mark.
- `{components.index-num}` — zero-padded mono numerals.
- `{components.img-frame}` — square hairline-bordered image region.
- `{components.accent-band}` — the single pale orange callout per deck.

That is the complete decorative vocabulary. There are no icons, no badges, no pills, no chips, no arrows other than the one trailing `{components.link-rule}`.

## Do's and Don'ts

### Do

- Leave the right third of a content slide empty. Whitespace is the system's main gesture.
- Number everything that comes in parts: 01, 02, 03 in JetBrains Mono.
- Separate columns with `{components.vrule}` and let the last column carry no rule.
- Drop the bottom border on the final row of any hairline table.
- Keep Japanese at `letter-spacing: 0` in every context.
- Use `{components.link-rule}` as the call to action, with `{colors.orange}` appearing only on hover.
- Put the wordmark in the chrome band of every content slide, once.
- Let one orange mark per slide do all the accent work — a dot, a 32px rule, or the asterisk.
- Pair a 32px orange rule with a mono kicker on the title slide, the way the corporate lockup does.

### Don't

- **Don't build cards.** No rounded, filled, bordered rectangle around text. Use `{components.indexed-cell}`.
- **Don't fill anything orange.** No orange button, no orange panel, no orange headline, no orange chart fill. Orange is a 4px dot, a 32px hairline, an asterisk, a hover state, or one pale tint band.
- **Don't add a second filled button.** `{components.btn-solid}` in black, once per deck, is the entire button system.
- **Don't letter-space Japanese.** This is the fastest way to make a Livspect deck look wrong.
- **Don't use emoji, icons, badges, or pills.** The em-dash and the index numeral replace all of them.
- **Don't add shadows, gradients, glows, or blurs.**
- **Don't go dark.** There is no dark variant of this system; a dark slide is a different brand.
- **Don't center content slides.** Left-aligned by default; centering is for the title and closing slides only.
- **Don't round images or add thick borders to them.** Square corners, 1px hairline.
- **Don't use weight 700.** The scale stops at 600.

## Responsive Behavior

Per the Fixed-Stage Policy above, the generated deck does not reflow. The `vw`/`vh` proportions in this document map to a 1920×1080 stage that scales as one transform. Hairlines must be authored so they survive scaling — use `1px` and verify at both 50% and 150% stage scale that rules remain visible and do not disappear into a sub-pixel.

### Presenter Behavior

- Slide transitions are opacity and a 12–16px translate, 320ms, `cubic-bezier(0.22, 1, 0.36, 1)`. Nothing rotates, scales, or flies.
- Within a slide, stagger the reveal of indexed cells by 60ms each. The hairline rule draws first (scaleX from 0), then the numeral, then the text.
- Respect `prefers-reduced-motion: reduce` by disabling all transforms and transitions and rendering every element in its final state.

### Print Behavior

The palette is already print-safe: white ground, near-black ink, light-gray rules. Set `-webkit-print-color-adjust: exact` so the hairlines and the orange points survive. Hairlines at `{colors.hairline}` can vanish on some printers — if a print deck is required, substitute `#D4D4D1` for rule colors in the print stylesheet only.

## CJK & International Content

Japanese is the **primary** language of this system, not a fallback. Every token in this document is designed to hold Japanese first.

### Recommended Japanese Pairing

- **Display / headline / body**: Zen Kaku Gothic New, weights 400 and 500. It is already the second family in every sans stack, so no per-run family switching is needed.
- **Japanese headlines**: use `{typography.h2}` at weight 500 (not 600 — Zen Kaku's 500 reads heavier against Inter Tight's 600) and `letter-spacing: 0`.
- **Structural labels in Japanese**: use `{components.eyebrow-ja}`, which is sans at caption size, not mono.
- **Mono is Latin-only.** Index numerals, dates, and axis ticks stay mono; their Japanese labels sit beside them in sans.

### Mixed-Content Strategy

A line that mixes Japanese and English resolves through the shared stack: Latin glyphs come from Inter Tight, Japanese glyphs from Zen Kaku Gothic New. Do not wrap the Latin words in a separate span with different tracking — the negative tracking that flatters an all-Latin headline makes a mixed line look pinched. For mixed headlines, use `letter-spacing: 0` and let the two families sit at their natural widths.

### Loading

Both Japanese and Latin faces load from the same Google Fonts request shown in the Typography section. Zen Kaku Gothic New is served as a subsetted `unicode-range` set, so the Japanese payload only downloads for the glyph ranges actually used. Keep `display=swap`.

### Universal CJK Adjustments

- `letter-spacing: 0` on every CJK run, without exception.
- Loosen line-height: body at 1.85, lead at 1.75, headlines at 1.18–1.35. CJK needs more leading than Latin at the same size.
- No `text-transform` on any run that may contain CJK.
- Line-break with `word-break: normal; overflow-wrap: anywhere; line-break: strict` so that small kana and closing brackets do not start a line.
- Avoid hyphenation entirely.

### Aesthetic Notes for This System

The hairline-and-index vocabulary was designed for Japanese business documents and works better in Japanese than in English — the even color of Zen Kaku Gothic New against thin gray rules is exactly the register of a well-set Japanese report. Japanese copy in this system should avoid heavy use of parenthetical asides and quotation brackets; keep sentences in a consistent polite register and let the hairline structure carry the organization that punctuation would otherwise have to.

### Known CJK Gap

JetBrains Mono covers no CJK. Any label that must be Japanese has to move to `{components.eyebrow-ja}`; there is no monospaced Japanese option in this system, and substituting a CJK mono font would introduce a fourth typographic voice.

## Iteration Guide

When a generated deck feels off, check in this order:

1. **Is there a box?** Search the output for `border-radius` values above 2px, for `background` on a text container, and for four-sided `border`. Each one is a card that should be an `{components.indexed-cell}`.
2. **Is orange doing too much?** Count the orange elements per slide. More than one mark — a dot, a 32px rule, or the asterisk — or any orange fill other than a single `{components.accent-band}`, is over budget.
3. **Is Japanese letter-spaced?** Search for `letter-spacing` on any element containing CJK. It must be 0.
4. **Are the hairlines the right gray?** `{colors.hairline}` for structure, `{colors.hairline-faint}` for dense interiors. A `#CCC` or `#DDD` rule reads as a different system.
5. **Is anything numbered with bullets instead of index numerals?** Multi-part content should be 01, 02, 03.
6. **Is the slide too full?** If content occupies more than 80% of the canvas, cut copy rather than shrinking type.
7. **Is the wordmark asterisk centered over the ı?** Adjust `.lv-ast { left }` until it is.

## Known Gaps

- **No dark variant.** This system is light-only by design. A dark deck should use a different template rather than an inverted Livspect.
- **No icon set.** Deliberate — but it means diagram-heavy content (architecture diagrams, system flows) must be built from hairline rules, labeled boxes with 1px borders, and index numerals, which is slower than an icon-based system.
- **Charts are austere.** Three ink tones plus one orange point covers most business charts but cannot express a five-series comparison. For those, use a table.
- **Hairlines at very small stage scale.** Below roughly 40% stage scale, `{colors.hairline}` rules approach invisibility. Decks intended for thumbnail display should use `{colors.hairline}` at minimum, never `{colors.hairline-faint}`.
