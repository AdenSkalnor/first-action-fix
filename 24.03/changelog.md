# Change Log — March 24, 2026

## Global Changes

1. **En-dashes replaced with hyphens** across all three pages (index, eec, behavioral-emails). All `–` characters converted to `-` for consistency.

2. **Alt-background color updated** on About/Main page. Changed `--bg-alt` from `#F0EFEB` to `#F5F4F0` — a lighter, warmer grey.

## Behavioral Emails Page (`/behavioral-emails/`)

3. **"3-5" changed to "4-6"** in Trial Rescue Campaign description.

4. **Trial Rescue Campaign** — added "Reclaim lost revenue from users who already showed intent." to the description.

5. **Activation Path** — rewrote description: "Connects trial signup to paid conversion through behavioral triggers at every stage. Each email responds to what the user actually did, not what day it is."

6. **Infrastructure section rewritten** — heading changed from "This Only Works With Real Infrastructure" to **"I Can't Automate Magic"**. Copy rewritten to be more conversational and direct.

7. **"When Behavioral Beats Calendar" rewritten** — heading changed to **"Why Linear Drips Fail AI Products"**. Entirely new copy explaining why Day 1/3/7 drips break for AI SaaS.

8. **Service tiers merged into Build With Me section** — Trial Rescue and Activation Path cards moved into the same section (same background). Removed separate `section--alt` wrapper. Card text centered.

9. **3-Day Tracking Course restyled** — converted from plain TextBlock to a styled card with accent left-border and "Free Course" badge. Matches EEC card presentation.

10. **DIY section updated** — "LinkedIn" text converted to a hyperlink (accent-colored, underlined). Numbered labels changed from "1 — Diagnostic" text style to numbered box design with accent-colored square containers.

## EEC Page (`/eec/`)

11. **CTA section rewritten** — heading changed from "Want a Custom EEC for Your AI SaaS?" to **"Automate Your 'Aha!' Moment"**. New copy about engineering the aha moment before the trial starts.

12. **"how to tell if AI output is reliable"** styled as an inline badge (accent background, small caps) in the Closes the Trust Gap section.

13. **Pipeline comparison card redesigned** — replaced monospace single-line flows with a step-by-step layout using individual styled spans for each funnel step. "Blog / Ad" split from the arrow chain. EEC signup step highlighted with accent background.

## Components

14. **LinkCard component** — added optional `badge` prop. When provided, displays an inline badge (styled like Nav badge) inside the card. Applied to:
    - EEC course cards: "Coming Soon"
    - Index page EEC courses: "Coming Soon"
    - Index page articles: "Coming Soon"
    - Index page Behavioral card: "In Development"

15. **Nav mobile reorder** — About link moved first in DOM order. On desktop, CSS `order` keeps Lead Magnet first visually. On mobile, About appears at top. "In Development" badge repositioned below "Behavioral Emails" text on mobile (flex-column).

## Files Modified

- `src/styles/global.css` — bg-alt color
- `src/pages/index.astro` — en-dash fix, badge props
- `src/pages/eec.astro` — CTA rewrite, badge styling, pipeline card redesign, inline badge
- `src/pages/behavioral-emails.astro` — multiple section rewrites, layout changes, styling
- `src/components/LinkCard.astro` — badge prop and styling
- `src/components/Nav.astro` — link order, mobile badge positioning
