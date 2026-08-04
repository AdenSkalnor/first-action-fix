# Iteration 2 — concept notes, screenshot read, and build rules

Date: 2026-08-04. Andrew is working on concepts and finds it hard to link font *names* to what he *saw*. This file fixes that: it reads each first-iteration screenshot, names what's in it, and records the preferences and rules iteration 2 is built on. A future chat (or Andrew) can use §1 as a name↔look dictionary instead of re-deriving.

---

## 1. Screenshot read — name ↔ look

- **Pic 1 — "Block rhythm and sequencing — big SaaS".** Heading + body in **Space Mono** (monospace). Warm off-white ground with a soft vertical gradient; block is a rounded card, faint 1px border, solid fill. *Feel:* technical, document-like. *Note:* text small; column narrow.
- **Pic 2 — "One warning about the 2026 consensus".** **Cuprum italic** heading + body, right-hand sidenote. Greige/ecru ground. *Feel:* editorial but the all-italic body is heavy to read; the greige reads flat/gray.
- **Pic 3 — "PREMISE".** Body in **Roboto Flex** (to be dropped). Warm off-white, narrow centered column with large empty margins. *This is the "1/3-width Instagram-thread" problem.*
- **Pic 4 — "The white-main systems worth copying wholesale".** Heading in **Ubuntu Condensed** (clean condensed sans), list items with hairline rules (Linear rhythm). Coolest, cleanest **near-white** on the set. *Feel:* crisp, precise — the Attio-preferred surface.
- **Pic 5 — Mercury "Long-text handling".** **Cuprum** heading + body, vivid **indigo pill CTA** (#5266EB). *Feel:* the indigo is the one moment of real color — a good example of the "less gray, more color" direction.
- **Pic 6 — Anthropic "Long-text handling".** **Cuprum** heading + **Newsreader serif** body, **clay CTA** (#CC785C), ivory ground. *Feel:* the serif body reads best for long / educational text.

## 2. Preferences inferred (since names weren't recalled)

- **Body for educational / long text →** favor a **serif reading face** (Newsreader, and new: Spectral / Source Serif 4). Pic 6 is the one that reads.
- **Headings →** no single favorite; **alternate** across the mentioned families — Ubuntu Condensed, Cuprum, Space Mono — plus new display faces (Chakra Petch, Fraunces). Lean on the mentioned families unless a new one is deliberately chosen.
- **White →** the pic-4 **cool near-white** is the cleanest starting point; alternate whites and try gradient grounds rather than fixing one.
- **Kill:** Roboto Flex (dropped everywhere), greige flatness, skinny centered columns, tiny text.

## 3. Build rules — iteration 2

- **Type size (up again):** body **20–21px** / 1.6; lead 22–24; subhead 26–30; headline 32–46; display 48–72. Notes/captions 16–17 (still the only sub-20 register).
- **Measure (wider):** prose **72–84ch**; lists and dense blocks may go two-column or near-full-width. No more 62ch skinny columns with huge margins.
- **Fonts (no Roboto), alternate across blocks — don't repeat a pairing on consecutive blocks:**
  - Headings: Ubuntu Condensed · Cuprum · Space Mono · Oxanium · Chakra Petch (new) · Fraunces (new) · Nova Square (sparingly)
  - Body/reading: Newsreader · Spectral (new) · Source Serif 4 (new) · Cuprum · Hanken Grotesk (new humanist sans) · Space Mono (doc-excerpt/mono accents)
- **Gradients — used more, but never inside a lined/carded block.** Gradient lives on the section/page **ground, outside** the block; the block itself keeps a **solid fill**. "Solid inside, gradient outside" is an explicit pattern. Gradients may carry color (orange, blue, near-black), soft but more present than iteration 1.
- **Color — less gray, more voltage.** Use real hues: orange, dark blue, near-black, ivory. One strong accent per block minimum; avoid flat greige.
- **Headlines — vary size AND color** across blocks; a headline can take the accent color, invert, or scale up hard.
- **Editing base:** Attio (carved 1px borders, tight grid, single accent) as the default, extended with the block catalog in §4.

## 4. Block-combination catalog (explore across the 7 blocks)

- **Double-outline:** two thin borders close together (e.g. 1px + 1px, 3px apart), solid-color inside.
- **Solid-inside / gradient-outside:** solid block sitting on a gradient ground.
- **Inverse block:** dark block on a light page — and the reverse (light block on a dark page).
- **Color block:** filled with an accent tint, contrasting text.
- **Band vs card:** full-bleed color band vs contained carved card, alternated.
- **Reverses of all the above** — if a block is dark-on-light, the next comparable one can be light-on-dark.

## 5. Caption format — optimized to reflect the whole

Every block still closes with an italic muted caption in the block's own font, now with a **plain-language feel descriptor** so the name links to the perception:

> *Feel: technical/document. Space Mono 20/1.6 · 80ch · solid card on gradient ground · double-outline 2×1px · orange accent — similar to Attio.*

## 6. Pages to build (Second Iteration)

Same B1–B7 content (technical-editing.md §5). Attio editing base + the §4 catalog. Two copy-bases:

- **`/lab/dark/`** — dark palette: near-black and dark-blue grounds, orange accent, inverse blocks, double-outline blocks, solid-inside/gradient-outside, reverses.
- **`/lab/white/`** — white base with new mixes: alternating whites, gradient grounds, colored blocks, one strong accent per block — no greige, no Roboto.

Recorded on `/lab/` under a **Second Iteration** heading.
