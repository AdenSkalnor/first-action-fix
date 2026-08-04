# /lab/ — Editing Map

Date: 2026-08-04. Purpose: fix what *"editing"* means before any page is built, per your instruction ("map 'what editing' first"). Nothing here is committed or deployed — this is the spec the build agents will follow once you approve sections 6 and 7.

---

## 1. The two things being held apart

- **Surface** = palette + border weight + corner radius + shadow + spacing scale. Borrowed from **Mercury / Anthropic / Attio / Notion**. One surface per page.
- **Editing treatment** = how a block is typeset and sequenced: measure, headline handling, alignment, block type, decoration. Borrowed from **Stripe Press / Works in Progress / 37signals-Basecamp / Linear / Stripe**. Distributed block-by-block *within* a page.

A page = one surface. Each block inside it = one editing treatment. So almost every block is its own variation — which is what you asked for on the palette question.

---

## 2. "What editing" — the full dimension set (more than fonts)

Per block, any of these can change:

1. Font family (your six + one neutral)
2. Size / scale step
3. Weight
4. Alignment — left / center / justified
5. Measure — line length in characters (ch)
6. Block type — hero / body / list / stat-source-caveat / pull-quote / sidenote / doc-excerpt / CTA
7. Accent usage — none / link-only / full
8. Border weight + color
9. Corner radius
10. Section-padding : paragraph-spacing ratio
11. Headline treatment — bare vs decorated
12. Editorial ethos — which long-text / rhythm reference the block emulates

The "five numbers + two fonts" harvest from your own text maps to dimensions **5, 8, 9, 10 + the font pairing**. Each block's caption reports exactly those.

---

## 3. Block caption convention (your end-of-block note)

Every block closes with a small caption: *italic, muted (~55% opacity), set in the same font as the block itself.* It states two things:

- **Setting used** — font · size/leading · measure · alignment · border · radius · padding:spacing
- **Similar to** — the reference site the block emulates

Example rendering:

> *Space Mono · 15/24 · 62ch · left · 1px #E8E8E6 · radius 6 · 5rem : 1.5rem — similar to Stripe Press.*

---

## 4. Content, broken into blocks

Your pasted passage ("Your premise holds…") splits into seven blocks:

- **B1** — Premise + the six reskin variables
- **B2** — Palette + surface (Mercury / Anthropic / Attio / Notion list)
- **B3** — Long-text handling (Stripe Press / WiP / 37signals list)
- **B4** — Block rhythm & sequencing (Linear / Stripe list)
- **B5** — Bare imagery (Mercury / Ramp / Arc)
- **B6** — The 2026-consensus warning + teardown-excerpt-as-hero
- **B7** — What to actually harvest (five numbers, two fonts)

---

## 5. Pages & routes

- `/lab/` — index; links all pages + a short version of this map
- `/lab/specimen/` — your six fonts, one per block, each block also a different size / alignment / type. The font tester.
- `/lab/mercury/` — Mercury surface; blocks cycle the editing treatments
- `/lab/anthropic/` — Anthropic surface; the serif-heading option lives here
- `/lab/attio/` — Attio surface
- `/lab/notion/` — Notion surface

Six pages. No shared layout, no global nav — consistent with `/variants/` and `/varpage/`.

---

## 6. The fixed combination set — CONFIRMED (your revision)

The font + size + editing-block combinations are a **fixed set, identical across all four surfaces, reordered per page.** The surface (palette) and the order are the only cross-page variables. This makes it a controlled comparison: the same combo read on Mercury vs Anthropic vs Attio vs Notion. Fonts bind to **blocks**, not surfaces.

The seven fixed blocks (font · size/leading · block-type · borrowed treatment). **Size rule: body starts at 18 (medium-small); 16 and below is reserved for notes/captions only; headlines step up from there.**

| Block | Content | Font | Size | Treatment (§7) |
|---|---|---|---|---|
| K1 | B1 premise | Roboto Flex | 18 / 1.65, 62ch | Stripe Press |
| K2 | B2 palette list | Ubuntu Condensed head + Roboto Flex items | head 32, items 18 | Linear |
| K3 | B3 long-text list | Cuprum | 19 / 1.6 | 37signals/Basecamp |
| K4 | B4 rhythm list | Space Mono | figure 28, source/caveat 16 (note) | Stripe (stat+source+caveat) |
| K5 | B5 bare imagery | Oxanium head + neutral body | head 28, body 18 | Stripe |
| K6 | B6 warning | Cuprum italic + margin note | 18 / 1.6, note 16 | Works in Progress (sidenote) |
| K7 | B7 harvest close | Nova Square head + Roboto Flex body | head 36, body 18 | Stripe Press |

Where a block needs a presentable beyond the six fonts, agents may pull from **adjacent families** (technical-editing.md §2) — normal operation. Soft focus-directing gradients per technical-editing.md §3.

**Reorder scheme (so no two pages read the same top-down):**
- Mercury: K1 K2 K3 K4 K5 K6 K7
- Anthropic: K7 K1 K6 K2 K5 K3 K4
- Attio: K2 K4 K1 K5 K3 K7 K6
- Notion: K4 K6 K2 K7 K1 K5 K3

Surface tokens (palette, border, radius, shadow) for each page come from **PART A of the editing-choices directory** — not reinvented here.

Specimen page (`/lab/specimen/`) exercises all six fonts in isolation, one per block, each at a different size/alignment/type — including Oxanium and Nova Square, which are otherwise reserved to statement headlines on the palette pages.

---

## 7. Editing treatments — PROPOSAL, needs your sign-off

The five borrowed ethos, defined, with a first-pass block assignment:

- **Stripe Press** — tight measure (~62ch), no chrome, undecorated headings → B1, B7
- **Works in Progress** — sidenote / footnote in the margin, sustained reading → B6 (the warning as a margin note)
- **37signals / Basecamp** — plain speech, one CTA, zero decoration → B3 + the CTA block
- **Linear** — structural whitespace, strong vertical rhythm → B2 (the list gets rhythm)
- **Stripe** — dense info sequenced so it reads light: stat + source + caveat in one block → B4, B5

---

## 8. Build mechanics (my side)

Once you approve: one subagent per page (six pages) dispatched in parallel. Each writes its `.astro` file, loads fonts via Google Fonts, self-verifies syntax, and adds the per-block captions from §3. Files land in your repo folder on disk; nothing commits until you push — and the stale `.git/index.lock` still needs clearing first.

---

## 9. What I need from you

Approve or edit **§6 (font placement)** and **§7 (treatment → block assignment)** — those are the only judgment calls. Everything else follows your instructions directly. Once those two are settled, I dispatch the build.
