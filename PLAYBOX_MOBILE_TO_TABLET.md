# PlayBox TV — Mobile to Tablet (Portrait) Guidelines

How to turn a PlayBox mobile UI into an **iPad portrait** UI. There are no tablet wireframes, so the mobile UI is the source.
Related: [PLAYBOX_DESIGN_SYSTEM.md](PLAYBOX_DESIGN_SYSTEM.md) (tokens, accessibility) · [PLAYBOX_WIREFRAME_TO_UI_RULES.md](PLAYBOX_WIREFRAME_TO_UI_RULES.md) (working and Figma execution rules, which still apply).

**Current scope:** iPad, portrait only. The user names the screen for each task. No new components for now; tablet blocks will be made into components later.

---

## 1. Screen size

| | Size | Use |
|---|---|---|
| **Base design** | **834 × 1194** | iPad Air / iPad Pro 11", the size every tablet design is made at |
| Check: smallest | 768 × 1024 | iPad mini / older iPads; the layout must not break |
| Check: largest | 1024 × 1366 | iPad Pro 12.9"; the layout must not look stretched or empty |

Height grows with the content (as on mobile). The width is fixed at 834.

---

## 2. Process

1. **Read the mobile screen's structure first:** its sections, their order and why each exists. The tablet version keeps the same priority and section order; only the layout changes.
2. **Give every element one responsive behaviour** (section 3).
3. **Build at 834**, then check at 768 and 1024 by resizing the frame (section 7).
4. **Deliver** the tablet frame next to its mobile source.

---

## 3. Responsive behaviours

Every element gets exactly one:

| Behaviour | Meaning | Typical elements |
|---|---|---|
| **Fill** | Stretches with the width | Section headers, CTA rows, search fields, dividers, toasts |
| **Reflow** | More items per row. Items may also get bigger than on mobile, or stay the same; decide per screen | Poster rails, "More like this" grids, channel lists, chips |
| **Reposition** | Stacked on mobile, side by side on tablet | Title + actions, thumbnail + episode info, meta rows |
| **Step up** | Moves to the next token size | Cards, hero, headings, icons in key actions |
| **Reveal** | Shows information mobile hides or truncates | Full episode synopsis, labels next to icons, longer titles |
| **Cap** | Stops growing at a maximum width | Body text, synopsis, Bottom Menu, dialogs |

---

## 4. Design guidelines

### 4.1 Grid and spacing (tokens only)

| | Mobile | Tablet portrait |
|---|---|---|
| Side margin | 16 | **24** |
| Card gap | 8–12 | **16** |
| Gap between sections | 20 | **24** |
| Heading → content gap | 12 | **16** |
| Columns | 4 | **8** (gutter 16, margin 24) |

Content width at 834 is 834 − 48 = **786**.

### 4.2 Typography

Stay on the existing token scale, with no new sizes.

| Element | Mobile | Tablet portrait |
|---|---|---|
| Page / content title | Title 3XL 24 | **Title 4XL 28** |
| Section heading | Title XL 18 | **Title 2XL 20** |
| Card title | Body M 14 | **Body L 16** |
| Body / synopsis | Body M 14 | Body M 14 → **Body L 16** for long text |
| Meta, tags, labels | Body S 12 | Body S 12 (unchanged) |

- Long text is capped at about **600px** wide so lines stay readable.

### 4.3 Content density

Show more items per row. Card size is open: cards may grow, or stay the mobile size, whichever works best for that screen. The tablet sizes below are a starting point, not fixed rules.

| Pattern | Mobile | Tablet portrait (starting point) |
|---|---|---|
| Poster rail (portrait cards) | 162 wide, about 2.3 visible | about 200 wide, about **3.5 visible** |
| Small poster rail | 114 wide, about 3 visible | about 140 wide, about **5 visible** |
| Landscape cards (live, streams) | 322 wide, about 1.1 visible | about 380 wide, about **2 visible** |
| Poster grid ("More like this") | 3 columns | **5 columns** |
| Episode rows | Thumbnail + title, synopsis below | Bigger thumbnail, with title, duration and synopsis **beside** it |
| Channel strips (Live TV) | 1 programme + peek | **2–3 programmes** visible |

- Rails always end partly cut off at the right edge to show they scroll.

### 4.4 Hero and banners
- Mobile's tall poster hero becomes a **wider banner** (about 16:9), with text and CTAs over its lower part.
- Carousels keep the peeking neighbours on both sides.

### 4.5 Detail pages (movie and series)
- **Trailer / preview** stays full width at the top, 16:9.
- **Title, meta and primary CTA:** the CTA sits next to the title block instead of below it. The CTA is capped at about 360 rather than stretched to full width.
- **User actions** (Watchlist, Share, Cast, Rate) stay in one row, left-aligned, with labels.
- **Synopsis** is capped at about 600 wide.
- **Tabs** stay left-aligned; they don't stretch across the screen.

### 4.6 Navigation
- **Bottom Menu** stays a floating pill, centred, with a **maximum width of about 560** (no edge-to-edge bar).
- **Top navigation** (logo, notifications, profile) uses the 24 margin, with the same items.

### 4.7 Sheets and pop-ups
- Mobile bottom sheets (season picker, activation pop-up, filters) become **centred dialogs** of about 560 wide, or anchored dropdowns for short lists.

### 4.8 Images and assets
- Reuse the same assets. Watch for upscaling: an image shown more than about 1.5× its source size needs a higher-resolution asset (flag it).

### 4.9 What stays the same
- Section order and content priority, all copy, CTA labels and branding.
- The red interaction colour, focus/selected states and the dark theme.
- All accessibility rules in section 8 of the design system: contrast, touch targets of at least 44×44, minimum text size 12, and no state shown by colour alone.

---

## 5. Components (for now)

- **The tablet view comes first.** Mobile components don't have to be reused; use them only where they suit the tablet layout.
- **New tablet-size elements are allowed.** Build them as named blocks from primitives (tokens, styles, assets), at whatever size the tablet view needs.
- **Don't create components yet.** Tablet components will be made separately later, including how they fit with the existing library.
- If a mobile library component is used, never detach it to resize it. Build a tablet block instead.

---

## 6. Figma execution

- **Placement:** the tablet frame goes in a section next to its mobile source, named `Screen / <Screen name> / Tablet Portrait 834`.
- **Structure:**
  - Auto layout everywhere; nothing positioned by hand.
  - Fill widths for sections, Hug for labels.
  - **Min/max width** on capped elements (synopsis, CTA, Bottom Menu, dialogs).
  - **Wrapping auto layout** for grids, so columns reflow when the width changes.
  - Rails are horizontal auto layout rows that clip at the frame edge.
- **Binding:** colours, type, spacing and radius are bound to UI Sample tokens; no raw values except effects and gradients (flag them).
- **Naming:** every frame and layer has a meaningful name, matching the mobile names where the element is the same.
- **Layout grid:** an 8-column grid (margin 24, gutter 16) on the frame, for checking alignment.

---

## 7. Checks before delivery

1. Live screenshot at **834**.
2. Resize the frame to **768** and **1024**. Nothing overlaps, text doesn't clip, and grids reflow instead of stretching.
3. The section order matches the mobile source.
4. Accessibility rules are met (contrast, 44px targets, text ≥ 12).
5. List anything flagged: raw values, upscaled images, elements that needed a new block.
