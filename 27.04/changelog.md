# Change Log — April 27, 2026

## New Page

1. **`/newview/` route added** — `src/pages/newview.astro`. A four-section landing page review built around the v3 logic chain. Hosted at `/newview/`, the original `/` is untouched. Uses theme `main`, `activePage="about"`. Same `BaseLayout`, same `Hero`, `TextBlock`, `Footer` components — composed differently.
    - Section 1 — **Hero** (no CTA): "Sales SaaS trial users quit before they activate." / "They quit because the next step inside the product is unclear."
    - Section 2 — **What I Do** (alt background): "I build the email systems that tell trial users what to do next." Two named offers as a bordered list — Educational Email Course / Behavioral Emails.
    - Section 3 — **Why Email**: two short lines on stall + channel.
    - Section 4 — **Next Step** (alt background): heading + two short lines + Calendly inline embed (`https://calendly.com/follow_action/30min`). Falls back to a button via `<noscript>` if the widget script is blocked.

2. **Calendly inline embed** added on `/newview/` — async external script tag at page level, doesn't block render. First page in the repo to use the embed instead of a button-out link. The other pages (`/`, `/eec/`, `/behavioral-emails/`) keep their existing button-out pattern.

## Project Hygiene

3. **`.gitattributes` added** — `* text=auto eol=lf` plus binary rules. Stops Windows checkouts generating phantom CRLF/LF diffs in `git status`. Six files were showing as "modified" with zero content changes before this; root cause is line-ending mismatch between checked-in LF and Windows-checked-out CRLF. No build impact.

4. **`check` script added** to `package.json` — `"check": "astro check"`. Opt-in only. Doesn't run automatically and isn't wired into the deploy workflow. Lets `npm run check` flag TypeScript errors before commit.

## Build Verification

5. **Build runs clean.** `npm run build` (Node 22) generates 5 routes:
    - `/index.html`
    - `/eec/index.html`
    - `/behavioral-emails/index.html`
    - `/newview/index.html` ← new
    - `/testtesttest/index.html`
    Total `dist/` size ≈ 116 KB. Single CSS bundle. One upstream Vite warning unrelated to this repo.

## Decisions Made (and Why)

6. **`activePage="about"`** on `/newview/` — semantically this is a redesigned homepage variant, so the "About" nav item highlights. Avoids touching the `Nav.astro` activePage union for a single experimental route.

7. **No new theme.** Brief is austere; the existing `main` theme (light, orange accent) suits the logic-chain framing without modification.

8. **Embed instead of button** in Section 4 — the brief explicitly specifies a calendar embed, and the reader who reached Section 4 of a four-section page is ready (asking for a calendar pick is asking less than they were prepared to give).

9. **No founder photo, logo grid, testimonials, or comparison framing** — per the brief. The logic chain does the trust work.

## Suggestions Discarded (per "no heavier build / no changed user interaction")

These were on the table but skipped to keep the deploy lean:

- `og-default.png` social image (asset weight)
- `404.astro` (extra route)
- `@astrojs/sitemap` integration + `robots.txt` (added dependency)
- `prefetch` in `astro.config.mjs` (alters how users navigate the site)

## Files Modified

- `package.json` — added `check` script
- `.gitattributes` — created
- `src/pages/newview.astro` — created
- `27.04/changelog.md` — this file
- `27.04/newview-context.md` — outline for downstream chats
