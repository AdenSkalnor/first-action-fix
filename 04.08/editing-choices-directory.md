# Editing Choices Directory

Date: 2026-08-04. Purpose: a persistent record of *what was harvested from which site*, so a future chat inherits the settings instead of re-scraping. This is the "five numbers + two fonts" harvest from Andrew's own brief, applied to all nine references.

**Confidence key:** ● firm (confirmed in research) · ◐ partial (design-system references, not pixel-scraped) · ○ inferred from ethos.

---

## PART A — Surfaces (one per palette page)

### Mercury ● — premium-restrained off-white
- **Type pairing:** Arcadia / Arcadia Display (proprietary), headings at weight ~480 — deliberate under-weighting. Substitute in our build: Roboto Flex.
- **Palette:** bg-primary `#F6F5F2`, bg-secondary `#EBE8E0`, ink `#2A2924`, single accent indigo `#5266EB`.
- **Border:** 1px hairline; depth comes from cream tone-shifts, not shadow.
- **Radius:** 32–40px pill on interactive controls; 4px on structural elements only.
- **Accent rule:** one filled indigo CTA per band, nowhere else.
- **Steal this:** cream-on-cream tone-shift depth, hairline borders, one voltage accent, tabular numerals on any figure.

### Anthropic ● — warm ivory, serif reading
- **Type pairing:** Styrene / Anthropic Sans (declarative headings) + Tiempos / Anthropic Serif (body + editorial display). Sans shouts, serif reads. Substitute: Cuprum body + a serif for headings.
- **Palette:** warm ivory ground (~`#FAF9F5`–`#F0EEE6`), low-saturation warm ink, clay/terracotta accent (~`#CC785C`).
- **Border:** minimal; separation by ground-tone and generous space.
- **Radius:** small, restrained.
- **Steal this:** ivory ground + serif for sustained reading + sans for the one declarative line; keep saturation very low so it reads as a default, not a pitch.

### Attio ◐ — white, precise, tight grid
- **Type pairing:** precise neutral sans (Inter-class). Substitute: Ubuntu Condensed.
- **Palette:** true/near-white, near-neutral greys, single teal-green accent.
- **Border:** 1px *inner* borders on cards and inputs — the "carved / precise" look.
- **Radius:** modest (cards ~8px).
- **Steal this:** 1px inner borders for carved precision; show how far a single accent goes when everything else is neutral; data-dense but airy.

### Notion ● — smoothed edges, warm white
- **Type pairing:** NotionInter (custom Inter cut) for UI + Lyon Text for editorial pull-quotes. Substitute: Space Mono accents on a neutral body.
- **Palette:** paper white `#FFF`; warm-grey ramp `#F9F9F8` → `#494744` (ecru tint, not cool grey).
- **Border/shadow:** warm-tinted shadows `rgba(15,15,15,…)` to stay in chromatic agreement with the warm canvas.
- **Radius:** 12px cards, 8px buttons — and *stop there*. Over-rounding is what makes a premium site read as a toy.
- **Steal this:** warm-grey neutrals over cool; the 12/8 radius ceiling; warm-tinted shadow.

---

## PART B — Editing treatments (distributed block-by-block within each page)

### Stripe Press ○ — book typography on the web
- Tight measure (~60–66ch), leading ~1.6–1.7, no chrome, headings that hold without decoration.
- **Apply to:** B1 (premise), B7 (harvest close).

### Works in Progress ○ — sustained reading + sidenotes
- Narrow main column with a margin reserved for sidenotes / footnotes; quiet sans for meta.
- **Apply to:** B6 (the 2026-consensus warning, rendered as a margin note beside the body).

### 37signals / Basecamp ○ — plain speech, one CTA, no decoration
- Large plain sans, generous size, minimal color, exactly one CTA, active refusal of ornament.
- **Apply to:** B3 (long-text list) + the CTA block.

### Linear ● — structural whitespace, tight display tracking
- Inter Variable, body 16px/1.5 weight 400; emphasis 17px+ weight 590; display weight 600 (resists 700+).
- Letter-spacing `-0.022em` at ≥48px; eyebrows get *positive* tracking (+0.4px) to mark taxonomy.
- Radius: card 12px, button 6px, pill 9999px.
- **Apply to:** B2 (palette list gets vertical rhythm + tracked eyebrow).

### Stripe ○ — dense info sequenced so it reads light
- Stat + source + caveat composed into one calm block; component grid tight; accents sparing.
- **Apply to:** B4 (rhythm list), B5 (bare imagery note).

---

## PART C — Andrew's six fonts: role recommendation

| Font | Character | Best role in the set |
|---|---|---|
| Roboto Flex | Neutral variable workhorse | Body / UI; the through-line on neutral blocks |
| Cuprum | Condensed humanist sans, warm | Body or subheads on the warm (Anthropic-ish) blocks |
| Ubuntu Condensed | Tight condensed | Grid-dense list blocks (Attio ethos) |
| Space Mono | Monospace | Captions, doc/teardown excerpt, Notion-style accents |
| Oxanium | Techno display | Section headers / eyebrows; the friction-test block |
| Nova Square | Squared techno display | One big statement headline only, used sparingly |

**Flagged tension:** Oxanium and Nova Square are techno/display faces that pull against the calm-premium surfaces. That's intentional in the specimen — you find out which survive a serious surface. On the palette pages they appear only where a statement headline earns them.

---

## Sources

- [Styrene in use: Anthropic — type.today](https://type.today/en/journal/anthropic)
- [Anthropic — Design Tokens & System, Design Extractor](https://www.design-extractor.com/gallery/anthropic)
- [Linear design tokens & typography — DesignMD](https://designmd.cc/benchmarks/linear)
- [Fonts in use on linear.app — Typ.io](https://typ.io/s/2jmp)
- [Mercury — Banking Editorial Warmth, awesome-claude-design](https://github.com/rohitg00/awesome-claude-design/blob/main/design-md/warm/mercury.md)
- [Mercury design breakdown — 925studios](https://www.925studios.co/blog/mercury-design-breakdown)
- [Notion Design Tokens & CSS Variables — DesignMD](https://designmd.cc/benchmarks/notion)
- [Attio — DESIGN.md, explainx.ai](https://explainx.ai/designs/whyashthakker-design-md-templates-skills/attio/design-md)
- [Works in Progress — And—Now case study](https://and-now.co.uk/work/works-in-progress)

*Numeric tokens for Attio, Stripe Press, Works in Progress, 37signals, and Stripe are design-informed (◐/○) rather than pixel-scraped; nudge against the live site if pixel-exactness is needed for any one block.*
