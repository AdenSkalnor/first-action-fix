# Technical Editing — templates, type scale, fonts, gradients, content

Date: 2026-08-04. Supplements `lab-editing-map.md` (the plan) and `editing-choices-directory.md` (the harvested tokens). This file is what a build agent reads to actually compose a page: the block templates, the type scale, the font roster, the gradient rule, and the verbatim content split into blocks.

---

## 1. Type scale (revised)

- **Note / caption:** 13–16px. *Only* register allowed below 18. Muted, ~55% opacity.
- **Body base:** 18px (medium-small starting point). Leading 1.6–1.65.
- **Body lead / emphasis:** 20–22px.
- **Subhead:** 24–28px.
- **Headline:** 30–40px.
- **Statement / display:** 40–64px (specimen + K7 statement close).

16 and below is reserved for notes/captions. Never set body copy at 16 or 15.

---

## 2. Font roster — the six + adjacent families

Originals (Andrew's picks): **Space Mono, Cuprum, Ubuntu Condensed, Roboto Flex, Oxanium, Nova Square.**

When a page has more presentable blocks than originals, pull from the adjacent family — this is expected, not a workaround:

- **Mono** (adjacent to Space Mono): JetBrains Mono, IBM Plex Mono, Martian Mono
- **Condensed** (adjacent to Cuprum / Ubuntu Condensed): Oswald, Barlow Condensed, Saira Condensed, Fjalla One
- **Techno / squared** (adjacent to Oxanium / Nova Square): Chakra Petch, Rajdhani, Orbitron, Michroma, Exo 2, Syncopate
- **Business / expressive** (adjacent to Roboto Flex): Inter, Manrope, Hanken Grotesk, Instrument Sans

All are on Google Fonts; load via `<link>`. When an adjacent font is used, name it in the block caption so the choice is recorded.

---

## 3. Soft gradient rule — focus by darkness

Apply low-contrast gradients to direct the eye. **Lightness delta kept small (≤ ~8%), never harsh.**

- **Focal elements** (the block meant to be read first, CTAs, statement headlines): shift the surface toward its **darker** end — focus is *amplified in darkness*. Text sits on a subtly deeper ground.
- **Peripheral / secondary elements:** shift toward **brighter / white** — receding.
- **Hues:** stay inside the page's surface palette, with **white and brand-orange** permitted on the light end and **near-black** at the dark end. Alternate warm-white and orange-tinted softness between sections.
- **Keep it a whisper.** If the gradient is obvious at a glance, it's too strong. Think 3–8% steps, large soft stops, no banding.

Utility pattern:

```css
/* peripheral: recede toward light */
.grad-recede { background: linear-gradient(180deg, var(--surface) 0%, var(--surface-lift) 100%); }
/* focal: amplify toward dark */
.grad-focus  { background: linear-gradient(180deg, var(--surface) 0%, var(--surface-deep) 100%); }
/* --surface-deep is the surface base nudged ~6–8% toward near-black (or brand-orange-shadow for warm surfaces) */
```

Each surface defines `--surface`, `--surface-lift` (lighter), `--surface-deep` (darker) from its directory tokens.

---

## 4. Block template library

Surface-agnostic skeletons. Each agent copies the pattern and paints it with the surface's tokens + gradient. **Record which template each block used** in an HTML comment above the block (`<!-- template: rhythm-list · treatment: Linear -->`).

**Prose (K1 / K3 / K6 body) — Stripe Press measure**
```html
<!-- template: prose -->
<section class="blk"><div class="col"><p>…</p></div></section>
```
```css
.col{max-width:62ch;margin-inline:auto} p{font-size:18px;line-height:1.65}
```

**Rhythm list (K2) — Linear**
```html
<!-- template: rhythm-list · treatment: Linear -->
<section class="blk"><div class="col">
  <p class="eyebrow">Palette + surface</p>
  <h2 class="display">…</h2>
  <ul class="rhythm"><li><b>Mercury</b> — …</li> …</ul>
</div></section>
```
```css
.eyebrow{font-size:13px;letter-spacing:.4px;text-transform:uppercase}
.display{letter-spacing:-.022em}
.rhythm{list-style:none;padding:0} .rhythm li{padding-block:.9rem;border-top:1px solid var(--rule)}
```

**Stat / dense (K4) — Stripe (stat + source + caveat)**
```html
<!-- template: stat-dense · treatment: Stripe -->
<div class="stat"><div class="fig">…</div><p class="src">…</p><p class="cav note">…</p></div>
```
```css
.fig{font-size:28px} .src{font-size:18px} .cav{font-size:16px;opacity:.6}
```

**Sidenote (K6) — Works in Progress**
```html
<!-- template: sidenote · treatment: Works in Progress -->
<section class="blk"><div class="wrap">
  <div class="body"><p>…</p></div>
  <aside class="side note">margin note…</aside>
</div></section>
```
```css
.wrap{display:grid;grid-template-columns:minmax(0,62ch) 15rem;gap:2.5rem}
.side{font-size:16px;opacity:.6}
@media(max-width:820px){.wrap{grid-template-columns:1fr}.side{border-left:2px solid var(--rule);padding-left:1rem}}
```

**Bare frame (K5) — bare imagery / doc-excerpt**
```html
<!-- template: bare-frame · treatment: Stripe -->
<figure class="bare"><div class="doc-excerpt">…monospace annotations…</div>
  <figcaption class="note">…</figcaption></figure>
```
```css
.bare{margin:0} .doc-excerpt{border:1px solid var(--rule);padding:1.5rem;font-family:'Space Mono',monospace;font-size:16px}
```

**Statement close (K7)**
```html
<!-- template: statement -->
<section class="blk grad-focus"><div class="col">
  <h2 class="display">…</h2><p>…</p></div></section>
```

**Plain CTA — 37signals/Basecamp**
```html
<!-- template: plain-cta · treatment: Basecamp -->
<div class="cta"><a class="btn" href="/varpage/teardown/">Request a free teardown →</a></div>
```

**Caption (every block closes with one)** — italic, in the block's own font, ≤16, muted:
```html
<p class="note cap"><em>Roboto Flex · 18/1.65 · 62ch · left · 1px #E8E8E6 · r6 · 5rem:1.5rem — similar to Stripe Press.</em></p>
```

---

## 5. Content — verbatim, split into blocks

**B1**
> Your premise holds. A live site is a better template source than a template marketplace, because you can read the decisions rather than inherit someone's content model. And the reskin is only about six variables: neutral ramp, one accent, radius scale, spacing scale, text measure, border weight. Fix those six and any layout you admire becomes yours.

**B2 — Palette + surface — the white-main systems worth copying wholesale**
> - Mercury — the reference for premium-restrained off-white. Near-invisible borders, almost no shadow, one accent used sparingly. Serious without being cold, which is your construction-buyer problem exactly.
> - Anthropic — warm ivory ground, serif headings, very low saturation. Closest live example of your §1 brief: calm enough to read as a default rather than a pitch.
> - Attio — white, precise, tight grid. Shows how far a single accent goes when everything else is neutral.
> - Notion — the smoothed-edges reference. Radius scale, soft card fills, warm white. Study it for where rounding stops; over-rounding is what makes a premium site read as a toy.

**B3 — Long-text handling — you have a wordy site, so this matters more than palette**
> - Stripe Press — book typography on the web. Measure control, no chrome, headings that hold their own without decoration.
> - Works in Progress — sidenotes, footnotes, sustained reading. Relevant to your Notion-docs layer and the sample teardowns.
> - 37signals / Basecamp — plain speech, opinionated blocks, one CTA, active refusal of decoration. The nearest ethos match to your §6 and §9.

**B4 — Block rhythm and sequencing — big SaaS**
> - Linear — take the spacing rhythm and the restraint, invert the palette. The lesson is vertical rhythm, and whitespace used structurally.
> - Stripe — how to sequence dense information so density stops feeling heavy. Useful for your §5, where you have a statistic plus a source plus a caveat in one block.

**B5 — Bare imagery**
> Mercury, Ramp, and Arc all show images without device frames, drop shadows, or perspective tilt. That is the current premium signal, and it happens to be the only image treatment that fits you.

**B6 — One warning about the 2026 consensus**
> Every roundup this year says the same three things: put the product in motion at the top, add micro-interactions, consider dark mode. Two of those are wrong for you. You have no product UI to demo, and dark mode fights the calm-default frame you decided to install. Your equivalent of the interactive product moment is a real teardown excerpt rendered as a document — styled like a page from the artifact the client would receive, monospace annotations and all. That is your hero image and your §7 proof in one object.

**B7 — What to actually harvest**
> Open each of these, then write down only: the radius value, the body measure in characters, the border color and weight, the ratio between section padding and paragraph spacing, the type pairing. Five numbers and two fonts. That set, applied to any block library, gets you closer to a coherent site than any theme purchase will.
