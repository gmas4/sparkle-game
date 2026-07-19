# SparklePop — Design System Audit

Site: sparklespop.com · Pages reviewed: `index.html`, `play-hub.html`, `play.html`, `pet.html`

## Summary

**Pages reviewed:** 4 | **Issues found:** 7 | **Score:** 52/100

There's no shared stylesheet or token file — each page is a fully self-contained HTML file that redeclares its own fonts, colors, gradients, and component styles. That's fine for four static pages, but it means every visual tweak (like the font change we just made) has to be repeated by hand on each page, and small drifts have already crept in.

## Naming consistency

| Issue | Where | Recommendation |
|---|---|---|
| Brand name differs per page | `index.html` = "SparklePop", `play-hub.html` = "Sparkle Magic", `play.html` = "Sparkle Unicorn Magic Garden", `pet.html` = untitled ("My Magical Unicorn Pet") | Pick one name — "SparklePop" is the domain and the one a parent reads first — and use it in every `<title>`, `<h1>`, and `og:title`. |
| Instagram handle drifted | `index.html` links to `@sparklespop4`; `play.html`'s shared-painting caption still says `@sparklespop` (no "4") | Confirm the real handle and make it identical everywhere it's printed. |

## Token coverage

| Category | Shared? | Findings |
|---|---|---|
| Color | No | 3 different full-page background gradients across 4 pages (pink/purple aurora on `index`+`play-hub`, a night-sky purple/gold on `play`, a slightly different pink/blue mix on `pet`). Several near-duplicate hex values only differ by case (`#FFD700` vs `#ffd700`, `#B06AFF` vs `#b06aff`) — a sign colors were retyped rather than reused from one source. |
| Typography | Partially | All 4 pages load Baloo 2 + Fredoka from Google Fonts, but `pet.html` requests a different weight subset (400/600/700/800 + 400/500/600/700) than the other three (500/700/800 + 400/600/700) — extra font weight downloaded for no visual reason. `pet.html` also falls back to `cursive` on Baloo 2 where every other page falls back to `sans-serif`. |
| Spacing / radius | No | Heavy, appropriate use of `clamp()` for responsive sizing (good pattern) but no consistent radius scale — corner radii jump between 8px, 12px, 16px, 20px, 24px, 40px and 999px pills with no clear rule for which value maps to which component type. |

## Component completeness

| Component | Consistent across pages? | Notes |
|---|---|---|
| Primary CTA button | ⚠️ | `index.html`'s `.cta` (white pill, pulsing glow) has no equivalent on `play-hub.html` or the in-game pages — each page invented its own button look instead of reusing one. |
| Card (`.card`, `.card-section`) | ⚠️ | `play-hub.html`'s game-picker `.card` and `index.html`'s `.card-section` share a visual language (white bg, thick white border, pink glow shadow) but are two separate, unlinked CSS definitions. |
| Badge / pill (trust badges, story badge) | ✅ | Only defined once, in `index.html` — no conflicts because nothing else has tried to replicate it yet. |
| Footer / social link | ❌ | Only `index.html` has a "Follow us" link. `play-hub.html`, `play.html`, and `pet.html` have no way back to Instagram or the story page (aside from `play-hub.html`'s "← Back to our story" link). |

## Priority actions

1. **Settle on one brand name** ("SparklePop" is the clear candidate) and make it consistent in every `<title>`, `<h1>`, and Open Graph tag — right now a parent could see three different names for the same product across one visit.
2. **Fix the Instagram handle mismatch** between `index.html` (`@sparklespop4`) and `play.html`'s shared-image caption (`@sparklespop`) before more images get shared with the wrong handle baked in.
3. **Pull shared chrome into one place** — background gradient, font `<link>`, and the CTA/card/badge styles — so a future visual change (like a font swap) only needs to happen once instead of four times.

## What's working well

The `clamp()`-based responsive type and spacing scale is used consistently and thoughtfully across all four pages — that's a genuinely solid foundation to build a real token system on top of, once the naming and duplication issues above are cleaned up.
