# PlayBox TV — Wireframe to UI Rules

Rules for converting a PlayBox TV wireframe into UI in Figma.
Visual reference: [PLAYBOX_DESIGN_SYSTEM.md](PLAYBOX_DESIGN_SYSTEM.md).

**Core principle:** the generated UI must be easy to edit at any point: clear names, auto layout, components.

---

## 1. Working rules

1. Do exactly what the task asks. Run the checks the task actually needs, no more and no fewer.
2. When a Figma link with a node-id is shared, work only on that node unless asked otherwise.
3. Existing screen designs are not a reference unless the task says so.
4. When something doesn't make sense or the context is unclear, ask the user instead of assuming.

---

## 2. Interpreting the wireframe

| Rule | Detail |
|---|---|
| Section order | Same as the wireframe |
| Elements within a section | Can be rearranged; the visuals must be explored |
| What the wireframe defines | Only *which* sections and cards exist |
| Wireframe dimensions | Ignore them. Wireframe sizes are random and not thought through |
| Wireframe elements (badges, tags, labels, etc.) | Add every one. If one doesn't make sense, ask the user |
| UI vs wireframe | The UI must be visually designed, not a coloured copy of the wireframe |

---

## 3. Content rules

| Rule | Detail |
|---|---|
| CTA placement | As in the wireframe; if the context suggests otherwise, ask the user |
| CTA copy | Exactly as in the wireframe |
| Assets (posters, artwork, logos) | Reuse the existing assets in the Figma files |
| Interactions | Don't build them. Explain in text how each interaction would work |

---

## 4. Design system rules

1. Use only design-system primitives: color variables, text styles, spacing and radius variables, effect styles (Glass), the paint style (`Linear_BG`).
2. No raw hex values, font sizes or spacing values. Everything is bound to a variable or style.
3. Use existing components (CTAs, posters, tabs, Bottom Menu, tags, ratings, OTT logos, etc.) as instances **from the UI Sample file library**.
4. Icons come from the `Final Icons` set (line = default, fill = active). If a wireframe icon has no close match, ask the user.
5. Use the file's own spacing tokens and icon set, not the figma-console MCP's default spacing scale or Lucide icons.

---

## 5. Component rules

1. Use an existing component wherever one fits.
2. When a block has no component:
   1. Build the first version from primitives.
   2. Show it to the user for approval.
   3. After approval, turn it into a component (with variants and properties where useful).
3. If a new component would be better than an existing one, show it to the user; **the user decides**.

---

## 6. Figma execution rules

### 6.1 Structure
- Screen size: **provided by the user** for each task.
- Deliver the **full screen at once**, not section by section.
- Place output inside a Section or Frame, never loose on the canvas.

### 6.2 Naming
- Every frame and layer has a meaningful name. No `Frame 1984079417`, `Rectangle 2`, `Group 1707479530`.
- Name by role and hierarchy, e.g. `Screen / Home – Unsubscribed` → `Section / Top Picks For You` → `Heading` / `Rail` → `Card`.
- Component instances keep or get names that describe their role.

### 6.3 Auto layout
- Auto layout on every frame that has children. No manual x/y positioning inside layouts.
- Sizing set deliberately: Fill for full-width sections and text blocks, Hug for labels and buttons, Fixed only where a size is intended.
- Gaps and padding bound to spacing variables.
- Horizontal rails are auto layout rows that can scroll or overflow, not loose cards.

### 6.4 Binding
- Fills, strokes and text colors are bound to color variables.
- Text uses text styles.
- Corner radius, gap and padding are bound to spacing variables.
- Effects use effect styles.

### 6.5 Components
- Instance properties (text, toggles, swaps) are used instead of detaching.
- Never detach an existing component to restyle it; ask instead.
- New components are created only after the user approves the first version.

### 6.6 Verification
- Screenshot the result after generating, check alignment, spacing and overflow, and fix issues before delivering.

---

## 7. Accessibility rules

Generated designs must meet **WCAG 2.2 AA**. Details in section 8 of [PLAYBOX_DESIGN_SYSTEM.md](PLAYBOX_DESIGN_SYSTEM.md).

- Text contrast ≥ 4.5:1 (≥ 3:1 for large text); UI and state contrast ≥ 3:1.
- Text on imagery or glass gets a scrim.
- Minimum readable text 12px.
- Touch targets ≥ 44×44 (hit area, even if the visual is smaller).
- Selected and active states are never shown by colour alone.
- Where a design-system token fails accessibility, use the accessible alternative and note the change.
- Accessibility issues in **existing** designs are flagged only when the user asks.

---

## 8. When to ask the user

- A wireframe element doesn't make sense in the UI.
- The context suggests a different CTA from the wireframe.
- A wireframe icon has no match in `Final Icons`.
- A new component might replace an existing one.
- Before turning a new block into a component.
