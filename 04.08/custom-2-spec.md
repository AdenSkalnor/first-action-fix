# Custom 2 — spec (ready to build next session)

Date: 2026-08-04. A second custom iteration-2 page (`/lab/custom-2/`), new body + block combinations, built like the others (own shell, shared `<LabMenu active="custom-2" />`, iteration-2 rules in `iteration-2-notes.md`, content B1–B7 from `technical-editing.md` §5, B3 CTA → `/varpage/teardown/`). Previous pages unchanged. Add a `custom-2` link to the menu component and the index iter2 list when built.

## Font constraint (the whole point of this page)

Use **only** fonts that are either (a) in Andrew's favored list, or (b) belong to the Google Fonts categories **Appearance/Theme = Techno**, **Technology = Variable**, or **Feeling = Business**. The aesthetic is technical / screen / business — distinct from Custom 1's warm serifs. Applies **especially to text bodies.**

### Favored named fonts (from Andrew's notes)
Space Mono · Cuprum · Ubuntu Condensed · Roboto Flex (Business, Variable) · Iceland · Electrolize · Geo · Oxanium (Techno, Variable) · Nova Square.
(Iceland / Electrolize / Geo are the "Screens" set Andrew listed. Roboto Flex is re-listed here by Andrew as the Business/Variable exemplar — allowed on this page despite the earlier "no Roboto"; keep it to one block, not the default.)

### Priority rule (Andrew, on resume)
Use the **favored in-notes fonts first**. New category families may be used **only after** the favored options have been utilized. The nine favored fonts cover seven blocks, so **this page uses favored fonts only** — no category-fill needed. Feature as many of the nine as possible. Roboto Flex exception stays (one block).

### Category fill — only if a favored option is genuinely unworkable (not expected here)
- **Techno:** Chakra Petch · Orbitron · Michroma · Rajdhani · Syncopate · Aldrich · Quantico · Audiowide · Zen Dots · Turret Road · Unica One.
- **Variable:** Recursive.
- **Business feeling:** Inter · IBM Plex Sans.

All on Google Fonts; one `<link>` must include every family actually used (bodies + headings) — this was the earlier failure mode.

## Proposed assignment (distinct per block, no consecutive repeat)

Bodies favor the more *readable* technos so long text survives; the squared/display faces carry headings.

| Block | Body font | Heading font |
|---|---|---|
| B1 | Electrolize (even screen sans) | Nova Square |
| B2 | Chakra Petch | Ubuntu Condensed |
| B3 | Cuprum | Geo |
| B4 | Rajdhani (stat text) + Space Mono (figures) | Chakra Petch |
| B5 | Oxanium | Iceland |
| B6 | Roboto Flex (the one Business/Variable block) | Michroma |
| B7 | Aldrich | Nova Square |

Headlines vary size (32–46) and color; some take the accent. Bodies 20–21/1.6, measure 74–84ch. Each body element gets an explicit `font-family`; caption names the actual body font.

## Block combinations (from iteration-2-notes §4)
Reuse the catalog: double-outline, solid-inside/gradient-outside, one inverse block, accent-tint band, card vs band. Gradients on grounds only, never inside a lined block. Real color per block (orange/blue/teal/clay), no gray flatness. Surface: clean near-white base with alternating/gradient grounds (a "screen"-tinted cool white suits the techno register).

## Note on readability
Iceland, Geo, Nova Square are display-grade — expect them to strain as body; they're placed as headings on purpose, but if Andrew wants to *see* them fail as body (like the Nova Square stress-test on custom 1), swap one body block to a display face and let the caption flag it.

## Build status
NOT built — deferred at session usage limit. Everything else (`iteration-2-notes.md`, `technical-editing.md`, `LabMenu.astro`) is in place; this page is a single-agent build when we resume.
