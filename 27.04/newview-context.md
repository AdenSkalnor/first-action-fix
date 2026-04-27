# /newview/ — Context Outline

This file exists so a future chat can pick up where this one left off without re-reading the whole repo. It captures what was seen, what was decided, and what's left open.

## What I Saw (Repo Snapshot)

- **Stack.** Astro 6.0.8, Node 22, static output. No integrations. `astro.config.mjs` only sets `site: 'https://firstactionfix.com'`.
- **Hosting.** GitHub Pages via `.github/workflows/deploy.yml`. Push to `master` → build → deploy. CNAME in `public/` resolves to `firstactionfix.com`.
- **Repo on GitHub.** `AdenSkalnor/first-action-fix` (master branch).
- **Routes pre-existing.** `/`, `/eec/`, `/behavioral-emails/`, `/testtesttest/`. (The last is a font-comparison scratch page that ships to prod; deliberately left in place.)
- **Layout.** Single `BaseLayout.astro` switches a `data-theme` attribute on `<html>`. Themes: `main` (light, orange), `eec` (warm light, soft orange), `behavioral` (dark, blue/purple).
- **Components.** `Nav`, `Hero`, `TextBlock`, `LinkCard`, `Footer`. Each is small and uses scoped `<style>` blocks. Global tokens live in `src/styles/global.css`.
- **Animations.** `.reveal` / `.reveal-stagger` + IntersectionObserver script in `BaseLayout`. Honors `prefers-reduced-motion`.
- **Changelog convention.** `<dd.mm>/changelog.md` at repo root. Existing example: `24.03/changelog.md`. New page session = new dated folder. This session = `27.04/`.
- **Commit style.** Short, informal subjects (`Redesign`, `Change`, `Text next`). Match the register; don't impose conventional-commits.

## What `/newview/` Is

A landing page review built to the v3 brief's four-section logic chain. Each section answers exactly one question; the next question only matters if the previous was answered cleanly.

| # | Section    | Question answered             | Has CTA |
|---|------------|--------------------------------|---------|
| 1 | Hero       | Am I in the right place?       | No      |
| 2 | What I Do  | What does this person do?      | No      |
| 3 | Why Email  | Why does this work?            | No      |
| 4 | Next Step  | What do I do next?             | Yes — Calendly inline embed |

The page lives at `/newview/` so the original `/` (homepage) is preserved. URL is all-lowercase and matches the file (`src/pages/newview.astro`) — chosen to dodge the lowercasing some referrers do to incoming URLs.

## Copy as Shipped

**Hero**
- H1: "Sales SaaS trial users quit before they activate."
- Sub: "They quit because the next step inside the product is unclear."

**What I Do** (alt background)
- "I build the email systems that tell trial users what to do next."
- Two kinds:
  - Educational Email Course — a sequence sent during the trial that teaches users how to reach value.
  - Behavioral Emails — triggered by what users do or fail to do inside the trial.

**Why Email**
- "When a trial user stalls, they leave the product."
- "Email is the channel that reaches them where they actually are."

**Next Step** (alt background)
- "30-minute diagnostic call."
- "We look at where your trial breaks down."
- Inline Calendly embed → `https://calendly.com/follow_action/30min`.

## Structural Choices and Rationale

- **No CTA in the hero.** Above the fold asks the reader to act before they know what they'd be agreeing to.
- **Two offers, no third.** Two is the most a reader holds in mind. A third forces evaluation mode and kills the diagnostic frame.
- **Mechanical "why," not promotional.** The reader can verify "stall → leave" from their own behavior. No persuasion language needed.
- **Calendar embed over opt-in form.** A reader who reached Section 4 of a four-section page is ready. Asking for an email is asking less than they were prepared to give.
- **What's deliberately absent:** founder photo, logo grid, testimonials, comparison framing, archetype routing, qualifications/disqualifications. Each would ask the reader to evaluate trust before they've accepted the problem; the logic chain is doing the trust work.

## Reference Material Available (Not Used on the Page)

The user provided a long brief covering broader strategic thinking. None of this is on `/newview/` itself; it's here so a future chat can pull from it when generating expansion text:

- **Customer Acquisition Cost framing.** EEC reduces CAC waste by capturing traffic that would otherwise leave without paying. Behavioral Emails reduce churn-in-trial by replacing user friction with structural momentum.
- **The 3-step map.** Lead Gen (EEC) → Nurture (Behavioral) → Math (napkin numbers tying conversion improvements to long-term results). Each step has its own CTA.
- **Operating principles.** Average user is oblivious; average founder is confused; sales process is closed-or-walk-away rather than objection-handling; outreach starts with genuine value.
- **Asset logic.**
  - **EEC:** lower commitment than a trial → easier to opt in. Acts as an anchor: the first frame the user receives shapes how they interpret every later moment in the product. Self-selecting filter raises trial-cohort quality.
  - **Behavioral Emails:** conditional, not calendar-linked. Every send fires on an observed event or non-event. Friction interception — catches the user at the moment of stall, before exit.
- **Pricing tiers.** Free teardown (30–60 min) → Audit ($4k, 2 weeks) → Full build ($12k–$28k, 6–10 weeks; milestone-gated; 20% relative lift guaranteed).
- **Buyer's Journey.** Awareness → Consideration → Decision. Nurture must be behavioral and segmented to be "competent" (not blasting a list).
- **Industry context (2026).** B2B trial-to-paid median 18.5%. Activation rate ~37.5%. ~70% of buyers are self-serve before vendor contact. Open positioning slot: category owner for teaching *why*, outside the product, for Sales SaaS at Seed–Series A.

## Hooks for Future Iteration

Things the page is set up to grow into without rewrites:

- **Replace `activePage="about"`** with a dedicated `'newview'` value if `/newview/` becomes its own nav entry. Requires extending the union in `BaseLayout.astro` and `Nav.astro`.
- **A/B test variants.** Duplicate `newview.astro` as `newview-b.astro` for a second route. The logic chain stays; copy varies. Compare via Calendly attribution or external analytics.
- **SEO + articles.** When the user adds article hosting (mentioned as a later concern), Astro content collections + `@astrojs/sitemap` would slot in cleanly under `src/content/`. No structural change to the existing pages.
- **Calendar embed cost.** Inline Calendly loads ~30 KB of external JS. If page-weight matters more than embed convenience, swap the embed for a button-out link matching the rest of the site.

## Files Touched This Session

```
.gitattributes                       (new — line-ending normalization)
package.json                         (added "check": "astro check")
src/pages/newview.astro              (new — the four-section page)
27.04/changelog.md                   (new — session changelog, follows 24.03/ pattern)
27.04/newview-context.md             (this file)
```

## Build Status at End of Session

`npm run build` is green. 5 routes generated. `/newview/index.html` ≈ 7.7 KB. Single CSS bundle. No errors. Calendly script loads async and falls back to a button via `<noscript>` if blocked.

## Note on URL Casing

The page was first created as `NewView.astro` → `/NewView/` and renamed to `newview.astro` → `/newview/` before any commit. This matters because the working filesystem (Windows / case-insensitive) would have made later case-only renames awkward. Future rename trick on this filesystem if needed: rename via a temp name first (`mv A.astro __tmp.astro && mv __tmp.astro a.astro`).
