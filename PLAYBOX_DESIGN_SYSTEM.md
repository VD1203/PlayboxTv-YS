# PlayBox TV — Design System Reference

Source: Figma file `gGdnHiDBzOE1UHKPI8UVoC` ("PlayBox TV - UI Sample"), read via figma-console MCP on 2026-10-19.
Purpose: the single reference for generating new PlayBox TV screens so they match the existing system.

---

## 1. File map

| Page | What's there | Use |
|---|---|---|
| **Design system** | `typography-showcase` (580:5261), `Colors` (609:6362), `Neutral` (609:7824), `Primary` (609:8411) | Token documentation |
| **Components** | ` CTA` (961:22198), `Others` (961:22512), `Posters` (1816:19610) | Component library — instantiate from here |
| **Icon Set** | `Final Icons` component set (902:50927) — 1,146 variants | All icons |
| **Final Sample** | `Home Page\| 2` section (2369:5234) → `Home Page` frame (2369:5235) | Canonical reference screen |
| Working Draft, Creat Account, Graphics, Animation, Deck, Junk | Explorations, onboarding/profile flows, motion drafts | Reference only |

---

## 2. Visual language (in one paragraph)

Dark-only, cinematic OTT aggregator for mobile (**402 × 874**, iPhone 16/17 Pro). Near-black canvas `#111111` with a warm **burgundy → black** gradient atmosphere. Brand energy comes from a **crimson/scarlet red** used sparingly on primary CTAs, selected states, the "New Movie" ribbon and live/progress accents. Secondary surfaces are **frosted glass** (white 10–20% + Figma GLASS effect). Content is poster-led: tall rounded posters (r 8–12) in horizontal carousels, OTT provider logos in circles, and a floating pill-shaped glass bottom nav. Headings use the wide **Zalando Sans SemiExpanded**; everything else uses **Zalando Sans**.

---

## 3. Color tokens (collection `Color`, 65 vars, single mode)

### Brand
| Token | Hex | Role |
|---|---|---|
| `Brand/Midnight Black` | `#111111` | App background (`Background/BG` aliases this) |
| `Brand/Deep Burgundy` | `#2F1818` | Gradient start, disabled primary CTA, ribbon tail |
| `Brand/Crimson Red` | `#5E0405` | **Primary CTA fill**, ribbon gradient end |
| `Brand/Vivid Scarlet` | `#EA0004` | Core brand red (= Primary-500) |
| `Brand/Coral Red` | `#FF3F42` | Highlight / ribbon fold |
| `Brand/Pure White` | `#FFFFFF` | |

**Usage (from the `Colors` doc frame 609:6362):** the four reds (Deep Burgundy, Crimson Red, Vivid Scarlet, Coral Red) are used mainly as **gradients and glow** on tags and CTAs, and for highlighting text. Midnight Black and Pure White are for backgrounds, text, selections and icons. Positioning: "a rich spectrum of reds balanced by strong black and white neutrals"; bold, cinematic, energetic.

### Primary scale
`50 #FDE6E6` · `100 #F8B0B1` · `200 #F58A8C` · `300 #F15457` · `400 #FF3E42` · **`500 #EA0004` (main)** · `600 #D50004` · `700 #A60003` · `800 #5E0405` · `900 #2E1818`

### Neutral scale (named `Nutral-*` in Figma)
`50 #FFFFFF` · `100 #F2F3F3` · `200 #D6D6D7` · `300 #BCBDBD` · `400 #A2A2A3` · **`500 #888888` (main)** · `600 #6E6E6F` · `700 #393939` · `800 #1F1F1E` · `900 #111111`

**Doc frames vs variables:** the swatches on the Colors, Neutral and Primary frames are hand-filled, not bound to variables. The labels differ slightly from the variables in three places: Neutral-50 is labelled `#FFFEFF` (variable `#FFFFFF`), Primary-400 is labelled `#FF3F42` (variable `#FF3E42`), and Primary-900 is labelled `#2F1818` (variable `#2E1818`). The labels show the intent: **Primary-400 = Coral Red and Primary-900 = Deep Burgundy**. The Colors frame also contains a leftover hidden "Orange" swatch (`#F07331`, with the label `#AACC43`) that has no matching variable. Ignore it.

### Text (aliases)
| Token | → | Hex |
|---|---|---|
| `Text/Primary` | Nutral-50 | `#FFFFFF` |
| `Text/Secondary` | Nutral-200 | `#D6D6D7` (unselected tabs/nav, subtext) |
| `Text/Tertiary` | Nutral-300 | `#BCBDBD` (meta, "Currently Playing") |
| `Text/Disabled` | Nutral-600 | `#6E6E6F` (note: disabled CTA text actually uses `#A2A2A3` / Nutral-400) |
| `Text/On-Primary`, `Text/On-Dark` | Nutral-50 | `#FFFFFF` |

### Semantic
`Success #18B866` · `Error #EF4444` · `Warning #F5A900`

### Transparency
`Transparency white/{5,10,15,20,25,30,40,50,60,70,75,80,90,95}%` and the same set for `Transparency black/…`. Use these for glass surfaces and image scrims.

### Paint & effect styles
- `Linear_BG` — linear gradient `#2F1818 → #111111` (page atmosphere)
- `Glass_1` — GLASS effect, radius 0
- `Glass_2` — GLASS effect, radius 4 (used on secondary CTA, bottom nav, rectangle tabs)

---

## 4. Typography (collection `Typography` + 32 text styles, all variable-bound)

**Families:** Titles → `Zalando Sans SemiExpanded` · Body → `Zalando Sans`. Letter-spacing 0 everywhere.

| Size token | px | Line height |
|---|---|---|
| XS | 10 | 14 |
| S | 12 | 16 |
| M | 14 | 20 |
| L | 16 | 22 |
| XL | 18 | 26 |
| 2XL | 20 | 32 |
| 3XL | 24 | 36 |
| 4XL | 28 | 40 |
| 5XL | 32 | 52 |
| 6XL | 40 | 64 |

**Title styles** (`Typography/Tittle/text-{XL…6XL} {Semibold|Bold}-{size}`) — SemiExpanded, SemiBold 600 or Bold 700, sizes 18–40.
**Body styles** (`Typography/Body/text-{xs|s|m|L} {Light|Regular|Medium|SemiBold|Bold}-{size}`) — 10–16px, weights 300–700.

**How they're used on the Home screen**
| Element | Style |
|---|---|
| Section heading ("Top Picks For You") | Title XL SemiBold 18/26 |
| Promo/feature heading | Title 3XL SemiBold 24/36 |
| CTA label | Body M Medium 14 |
| Card title | Body M Medium 14, white |
| Card subtext / meta | Body S Regular 12, `#D6D6D7` |
| Tags, badges, nav labels | Body S Medium/SemiBold 12 |
| Tabs | Body M 14 (Medium default → SemiBold selected) or Body L 16 |

---

## 5. Spacing & radius (collection `Spacing`, 18 vars, scoped to GAP + CORNER_RADIUS)

`0 · 2 · 4 · 6 · 8 · 10 · 12 · 16 · 20 · 24 · 28 · 32 · 36 · 40 · 48 · 56 · 60 · 999 (Circle)`

**Observed layout rules**
- Screen: 402 wide, **16px side padding** (content width 370).
- Vertical gap between home sections: **20**.
- Section = heading + carousel, gap **12**.
- Carousel item gap: **12** (8 for compact rails, 16 for sports).
- Radius: posters **8** (small) / **12** (medium, large, horizontal); CTAs **16**; tabs/badges **8**; nav, pills, progress bars **999**.

---

## 6. Components (page **Components**)

### CTA
| Component | Variants | Spec |
|---|---|---|
| **Primary CTA** (961:22328) | State: Default / Pressed / Disabled · Size: Medium (213w) / Large (370w) · `Show Icon` | h 46, r 16, gap 8, fill `#5E0405` with inner red glow; Disabled fill `#2F1818`, text `#A2A2A3`. **Pressed = scaled down** (h 39, r 13.7) rather than recoloured |
| **Secondary CTA** (793:22632) | same | h 46, r 16, fill `#7D7D7D` @20% + Glass r4; Disabled @30% |
| **Tertiary CTA** (793:22635) | Default / Disabled · `Show Icon` | Text-only, underlined label, padding 0/12 |

Default label: "▶ Watch Now", Body M Medium 14 white.

### Navigation
| Component | Variants | Spec |
|---|---|---|
| **Bottom Menu** (1729:3193) | Home / Sports / Verticals / Live TV / Search | 370×72 floating pill, r 99, white 10% + Glass, padding 6/12. Active item = red circular blob + SemiBold white label; inactive = Medium 12 `#D6D6D7` |
| **Tab Bar Circular** (978:27508) | Default / Selected | Icon-in-circle + label (Movies / Playshots / Shows / Upcoming). Selected: red fill, SemiBold 16 |
| **Tab Bar Rectangle** (1776:20568) | Default / Selected · `Show Close` | h 38, r 8, white 15% + Glass; Selected red with close badge |
| **Tab Style New** (1995:1934) | Default / Selected | Text tab, red underline when selected |

### Content
| Component | Variants | Spec |
|---|---|---|
| **Movie Posters** (873:14726) | Small 114×186 · Medium 162×224 · Large 161×274 · Horizontal-small 322×203 · Horizontal-medium 322×263 | Toggles: `Show lock`, `Show OTT`, `Show Progress Bar`, `Show Text`, `Show Subtext`, `Show Tags`, `Show Play`, `Live indicator`, `Live Dot`; `Instance` swap for OTT logo |
| **Trending cards** (961:27425) | Rank 1/2/3 · Small 162×229 / Large 322×229 · `Lock` | Giant rank numeral behind poster (Roboto Condensed Bold 150, `#7D7D7D` @20%) |
| **Square Poster** (1816:20253) | — | 179 wide, image + heading (Body M Medium 14) + subtext (Body S Regular 12) |
| **Movie Posters Tags** (1345:32381) | — | "New Movie" ribbon, 82×28, gradient `#2F1818 → #5E0405`, folded corner `#FF3F42` |
| **U A Rating** (2012:16532) | Neutral ("U/A 16+", `#111111` text) / Warning ("A+", `#D50004` text) | White chip, h 24, r 8, padding 4/8 |
| **Progress Bar** (873:14820) | Size Small 114 / Medium 151 / Large 307 · Progress 5/50/90% | h 3, r 999, track `#6E6E6F`, fill red |
| **OTT Logos** (867:14702) | 26 providers (Sony Liv, Hotstar, Zee5, aha, SunNXT, Discovery, Lionsgateplay, Fancode, …) | Logo tiles |
| **OTT Logos / OTT Icon** (867:14720) | XL / Large / Medium / Small | Circular glass frame around a provider logo |
| **Icon Button** (793:22647) | L 46 / M 38 / S 30 | Circular play button |
| **Verticals Action Controller** (1816:20341) | Expanded / Collapsed · `Show Add Icon`, `Show 1x`, `Show Volume` | Vertical glass pill for short-video player |
| **Overlay** (1808:17335) | — | 402×874 black scrim for modals |
| **Slider** (720:5653, Working Draft) | — | Hero carousel |

### Icons — `Final Icons` (902:50927)
1,146 variants. `Property 1` = category (arrow, building, business, contact, design, development, device, editor, education, file, food, logo, map, media, part, shape, system, transport, user, weather). `Property 2` = `<name>_line` / `<name>_fill` (MingCute naming). Use **line** for default, **fill** for selected/active.

---

## 7. Inconsistencies to know about (don't copy blindly)

- Naming typos baked into tokens: `Nutral-*`, `Tittle`, `Disbaled`, `Nuetral`. Reference tokens by their actual names.
- `Background/linear_BG` variable is `#FFFFFF` (placeholder) — use the **`Linear_BG` paint style** for the gradient instead.
- `Primary-400 #FF3E42` vs `Brand/Coral Red #FF3F42`, and `Primary-900 #2E1818` vs `Brand/Deep Burgundy #2F1818`: each pair is meant to be the same color (the doc labels say so) but the values are 1 apart.
- Secondary CTA / OTT circle fill `#7D7D7D` is not in the neutral scale.
- Trending rank numerals use **Roboto Condensed**, outside the two-family system.
- Some text on screens isn't linked to styles (e.g. hero "Watch Now" 13.25px, one "Trending on Hotstar" heading at 20px instead of 18).
- Icon Button S (30px) and M (38px) are under the 44px touch-target minimum.
- `typography-showcase` frame copy is generic Zalando boilerplate ("Exclusive Brands", "© 2025 Zalando Design System Group") — not PlayBox content.
- The figma-console MCP's default rules suggest Lucide icons via Iconify and a 4/8/12/16/24/32/48 spacing scale. **For PlayBox, use the file's own `Final Icons` set** (MingCute — `mingcute:*` on Iconify if a fallback is needed) **and its own spacing tokens** (which include 10/20/28 etc.).

---

## 8. Accessibility (WCAG 2.2 AA baseline — mandatory)

The tokens, components and patterns above are the house style. Treat them as **strong defaults, not law**: wherever following them would break accessibility, accessibility wins. Adjust the token or component, and note the deviation.

Standards: **WCAG 2.2 AA**, plus platform tap-target guidance (**iOS 44×44pt, Android 48×48dp**).
Contrast ratios were calculated against the tokens (glass surfaces blended over `#111111`).

### 8.1 Text contrast — needs 4.5:1 (≥3:1 only for large text: 24px+, or 18.66px+ bold)

| Pair | Ratio | Verdict |
|---|---|---|
| White on `#111111` | 18.9 | ✅ |
| Text/Secondary `#D6D6D7` on `#111111` | 13.0 | ✅ |
| Text/Tertiary `#BCBDBD` on `#111111` | 10.0 | ✅ |
| Nutral-400 `#A2A2A3` on `#111111` | 7.4 | ✅ |
| Nutral-500 `#888888` on `#111111` | 5.3 | ✅ (lowest neutral for readable text) |
| Text/Disabled `#6E6E6F` on `#111111` | 3.7 | ⚠️ OK only for truly disabled controls (exempt). **Never** use for placeholder, helper, meta or timestamp text |
| White on Crimson `#5E0405` (Primary CTA) | 14.0 | ✅ |
| White on Deep Burgundy `#2F1818` | 16.6 | ✅ |
| Disabled CTA `#A2A2A3` on `#2F1818` | 6.5 | ✅ |
| White on Secondary CTA glass (≈`#272727`) | 14.9 | ✅ *over dark only*; see 9.3 |
| White / `#D6D6D7` on Bottom Menu glass (≈`#292929`) | 14.6 / 10.0 | ✅ *over dark only* |
| White on Vivid Scarlet `#EA0004` | 4.7 | ✅ (just passes) |
| White on Primary-600 `#D50004` | 5.5 | ✅ (preferred for bright-red fills that carry text) |
| **White on Coral Red `#FF3F42`** | **3.5** | ❌ Normal text. Large/bold text only; use Primary-600 for text-bearing fills |
| **Vivid Scarlet `#EA0004` as text on `#111111`** | **4.05** | ❌ For small text. Use **Coral Red `#FF3F42` (5.4)** or **Primary-300 `#F15457` (5.5)** for red text, links and highlights on dark |
| `#D50004` on white (A+ badge) | 5.5 | ✅ |
| `#111111` on white (U/A badge) | 18.9 | ✅ |
| Success / Error / Warning text on `#111111` | 7.3 / 5.0 / 9.5 | ✅ |
| **White on Success `#18B866`** | **2.6** | ❌ Use `#111111` text on Success fills |
| **White on Error `#EF4444`** | **3.8** | ❌ Use Primary-600/700 fill, or dark text |
| `#111111` on Warning `#F5A900` | 9.5 | ✅ (never white on Warning) |

### 8.2 Non-text contrast — 3:1 for UI boundaries, states and meaningful graphics

- ❌ **Progress Bar: red fill `#EA0004` vs track `#6E6E6F` is only 1.1:1.** Progress is distinguishable by hue alone, so it's invisible to many colour-blind users. **Fix:** darken the track to Nutral-700 `#393939` or Transparency white/20%, and keep the fill at Vivid Scarlet (fill-to-track contrast then rises to ≈2.6–3:1). For key "resume watching" cards, pair it with text ("23 min left").
- ⚠️ **Primary CTA fill Crimson `#5E0405` vs background is 1.3:1.** The label carries the meaning, so it passes, but the button shape barely reads. Keep the inner red glow or a 1px Coral/Primary-400 top highlight, and don't rely on fill alone to show it is a button.
- ⚠️ **Selected states must not depend on red alone.** The current components already pair colour with weight or shape (Bottom Menu: blob + SemiBold; tabs: underline + SemiBold; circular tabs: size + fill). Keep that pairing in every new selectable element.
- Trending rank numerals (1.3:1) are decorative. That's fine, but the rank must also be exposed as text to assistive tech ("Rank 1, <title>").

### 8.3 Text on imagery and glass

- Glass contrast above assumes a dark backdrop. Over bright posters or hero art, glass can drop below 4.5:1. **Rule:** any text on a poster, hero or glass-over-image needs a scrim: a `Transparency black/60%`+ gradient behind the text area, or raise glass fill to ≥ white 20% plus a black 40% underlay.
- Ribbons, OTT badges and lock icons sitting on posters need their own solid or gradient backing (the "New Movie" ribbon already does this).

### 8.4 Text size and scaling

- Minimum **12px** for any readable text (Body S). **Body XS (10px) only for non-essential decorative micro-labels**, never for prices, ratings, times, legal or error text.- Support Dynamic Type / font scaling up to 200%. Cards, CTAs and section headings must grow in height or truncate gracefully with a full title available. Avoid fixed text-box heights.
- Line height is already ≥1.3 across the scale ✅. Avoid all-caps body copy.

### 8.5 Touch targets

- Every interactive element has a hit area of at least **44×44** (iOS) / 48×48dp (Android), even when its visual is smaller (e.g. Icon Button S 30 / M 38 → add transparent hit area).
- Pressed states may scale the visual, but never shrink the hit area (Primary/Secondary CTA Pressed: keep 46).
- Nav and tab items: equal-width, full-height hit areas across their bar.
- Small close/dismiss badges: at least 24×24 (WCAG 2.5.8), 44 preferred.
- Non-tappable badges (lock, OTT, live) need no hit area; the card is the target.
- Keep ≥8px between adjacent targets.

### 8.6 Screen readers, motion and interaction

- **Accessible names** for every icon-only control: play, "+", bell ("Notifications, 1 new"), avatar ("Profile"), volume, 1x speed, close, search. OTT logos need provider names; lock = "Subscription required"; Live dot = "Live".
- Poster cards are announced as one element: title, OTT, rating, lock/live state, progress.
- **Reduced motion:** hero carousel, car-swipe and home animations must respect `prefers-reduced-motion` / iOS Reduce Motion (cross-fade or none).
- **Auto-advancing carousels** need pause, and must stop on focus or touch (WCAG 2.2.2). No flashing above 3 per second.
- Horizontal rails must be reachable without precise swipes: support VoiceOver/TalkBack swipe navigation and a "View All" alternative.
- Focus order follows visual order. Visible focus indicators (2px Coral Red `#FF3F42` or white ring, ≥3:1) for keyboard and switch control.
- Errors (forms, OTP, payments): icon + text, never colour only; Error colour text on dark is OK (5.0:1).

---

## 9. Rules for generating new PlayBox designs

1. Frame 402×874, fill `Brand/Midnight Black`, optionally `Linear_BG` atmosphere at top.
2. Bind every color, spacing, radius and text to the variables/styles above — no raw hex.
3. 16px side padding; 20 between sections; 12 inside sections and between cards.
4. Instantiate existing components (Posters, CTAs, Bottom Menu, Tabs, Tags, Ratings) before drawing anything new.
5. Red is an accent: one primary CTA per view; selected states; ribbons; progress. Everything else is white/neutral on dark, or glass.
6. Glass surfaces = white 10–20% + `Glass_2`.
7. Headings in SemiExpanded SemiBold; body in Zalando Sans; secondary text `#D6D6D7`, tertiary `#BCBDBD`.
8. Icons from `Final Icons`; line = default, fill = active.
9. **Run the section 8 checks on every screen** (contrast, scrims on imagery, 44px targets, non-colour state cues, accessible names, reduced motion). Where a house-style token fails, swap it for the accessible alternative listed there and note the change.
