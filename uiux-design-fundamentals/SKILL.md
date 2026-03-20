---
name: uiux-design-fundamentals
description: >
  Comprehensive UI/UX design rules for building polished web interfaces in React/HTML/CSS.
  Use this skill whenever building, designing, or reviewing any frontend UI — cards, layouts,
  landing pages, dashboards, dark mode, buttons, inputs, overlays, navigation, or any visual
  component. Covers visual hierarchy, spacing, typography, color, dark mode, shadows, icons,
  buttons, feedback states, micro interactions, and image overlays. Triggers on any task
  involving frontend design, component styling, CSS architecture, or UI quality review.
  Even if the user just says "make it look good" or "style this component" — use this skill.
license: MIT
metadata:
  author: bakwankawa
  version: 1.0.0
  source: "Every UI/UX Concept Explained in Under 10 Minutes — Kole Jain (Vi Media)"
  category: design
  tags: [ui, ux, css, frontend, design-system, dark-mode, typography, spacing]
---

# UI/UX Design Fundamentals

Actionable design rules for AI agents building web interfaces. Every rule maps
directly to CSS/React implementation decisions. For CSS code patterns and
starter templates, consult `references/css-patterns.md`.

---

## 1. AFFORDANCES & SIGNIFIERS

UI elements should visually communicate what they do without instructions.

- **RULE 1.1 — Grouping:** Wrap related items in a shared container (border or background) to signal they belong together.
- **RULE 1.2 — Selection:** Highlight the active/selected item with an inner container or distinct background color.
- **RULE 1.3 — Disabled:** Gray out text and reduce opacity to signal non-interactive elements.
- **RULE 1.4 — Required signifiers:** Every interactive UI must have: button press states, active nav highlights, hover states, tooltips on icon-only controls.
- **RULE 1.5 — Core principle:** "Good UI has signifiers — the user shouldn't need instructions to understand how the interface works."

---

## 2. VISUAL HIERARCHY

Organize information by importance using **size**, **position**, and **color**.

- **RULE 2.1 — Three tools:** Size (bigger = more important), Position (top = most important), Color (contrasting = draws the eye). It's the **contrast** that creates hierarchy.
- **RULE 2.2 — Image-first cards:** Images at top of cards add a "pop of color" and make scanning easy. Use images whenever possible.
- **RULE 2.3 — Primary element:** Most important text = largest, boldest, positioned at top.
- **RULE 2.4 — Secondary info:** Less important data = smaller, below the primary element.
- **RULE 2.5 — Key metric:** Position price or key metrics top-right, in a distinct color (e.g., blue `#3b82f6`).
- **RULE 2.6 — Icon-as-label:** Replace verbose text labels ("Deliver To:") with icons + visual connectors (pin icons + dotted line).
- **RULE 2.7 — Multiple valid layouts:** Hierarchy isn't an exact science — same principles, different arrangements.

---

## 3. GRIDS, LAYOUTS & SPACING

Grids are **guidelines, not rigid rules**. White space matters more than grid compliance.

- **RULE 3.1 — Grids are guidelines:** 12-column grid and 8px spacing are not rigid. Custom landing pages often don't align to columns.
- **RULE 3.2 — When grids help:** Galleries, blogs, repeating content — responsive behavior: 12 columns desktop, 8 tablet, 4 mobile.
- **RULE 3.3 — White space is king:** "Letting things breathe" is MORE important than strict grid adherence.
- **RULE 3.4 — Exact spacing values:**
  - Heading: **64px** font size, **72px** line height
  - Body/subtext: **20px** font size, **28px** line height
  - Announcement bar: **16px** font size, **20px** line height
  - Major section gap: **32px**
  - Grouped element gap: **16px** (announcement-to-heading, heading-to-subtext)
- **RULE 3.5 — Spacing-as-hierarchy:** Tighter spacing (16px) for related elements, larger gaps (32px) between groups.
- **RULE 3.6 — 4-point grid:** All spacing values should be multiples of 4: `4 | 8 | 12 | 16 | 20 | 24 | 28 | 32 | 36 | 40`. Creates consistency through divisibility.

---

## 4. TYPOGRAPHY & FONT SIZING

Design is mostly text. One font is almost always enough.

- **RULE 4.1 — One font only:** Pick one good sans-serif and stick to it.
- **RULE 4.2 — Recommended fonts:** DM Sans, Axiforma, SF Pro, Geist, Plus Jakarta Sans, Montserrat, Unbounded.
- **RULE 4.3 — Letter-spacing hack (instant pro look):**
  - Tighten `letter-spacing` to **-0.02em to -0.03em**
  - Drop `line-height` to **1.1 to 1.2**
  - Apply ONLY to headings/large text — not body copy
- **RULE 4.4 — Landing page type scale (6 sizes):** 64px, 42px, 32px, 20px, 16px, 14px
- **RULE 4.5 — Dashboard type scale (6 sizes):** 24px, 20px, 18px, 16px, 14px, 12px
- **RULE 4.6 — Maximum 6 font sizes** per design.

---

## 5. COLOR THEORY

Start with one primary color and derive everything from it.

- **RULE 5.1 — One primary color:** Start with your brand color.
- **RULE 5.2 — Derive from primary:** Lighten for backgrounds, darken for text.
- **RULE 5.3 — Build a color ramp:** Lightest (background) through mid-tones (buttons/chips) to darkest (text). ~11 swatches from --primary-50 to --primary-900.
- **RULE 5.4 — Semantic colors:** Blue = trust/links, Red = danger/errors, Yellow = warning, Green = success.
- **RULE 5.5 — Let color find you:** Add color where purpose demands it: announcement bars (attention), input focus (feedback), status chips (information).
- **RULE 5.6 — Core principle:** "Use color for purpose, not just for decoration."

---

## 6. DARK MODE

Dark mode inverts the depth model entirely.

- **RULE 6.1 — Lower border contrast:** Use `rgba(255, 255, 255, 0.08)` instead of light borders.
- **RULE 6.2 — Elevation through lightness:** No shadows for depth. Higher elevation = lighter surface color. Cards lighter than page background.
- **RULE 6.3 — Desaturate chip colors:** Dim saturation+brightness on chip backgrounds, make chip text brighter/lighter.
- **RULE 6.4 — Creative base colors:** Not just navy/gray — deep purples, reds, greens are valid.

---

## 7. SHADOWS & DEPTH

Most shadows are too strong. If the shadow is the first thing you notice, it's wrong.

- **RULE 7.1 — Fix strong shadows:** Reduce opacity AND increase blur radius.
- **RULE 7.2 — Elevation-based strength:**
  - Cards on page: `0 1px 3px rgba(0,0,0,0.06)` (low elevation)
  - Popovers/dropdowns: `0 8px 30px rgba(0,0,0,0.12)` (high elevation)
- **RULE 7.3 — Tactile buttons:** Combine inner + outer shadows for raised/pressed effects.
- **RULE 7.4 — Golden rule:** Shadows should be subtle and supportive, never the focal point.

---

## 8. ICONS & BUTTONS

- **RULE 8.1 — Icon size = text line-height:** If line-height is 24px, icons should be 24px. Then tighten the gap.
- **RULE 8.2 — Ghost buttons:** Sidebar nav links = buttons without a background until hover.
- **RULE 8.3 — Nav = button:** An isolated sidebar link, centered, IS a standalone button.
- **RULE 8.4 — Primary + ghost pair:** Filled primary CTA + transparent ghost secondary CTA side by side.
- **RULE 8.5 — Padding ratio 2:1:** Horizontal padding = 2x vertical. E.g., `padding: 12px 24px` or `padding: 16px 32px`.
- **RULE 8.6 — Icons optional:** Buttons work with or without icons.

---

## 9. FEEDBACK & STATES

When a user does anything, there must be a visual response.

- **RULE 9.1 — Core principle:** "When a user does anything, there should be a response."
- **RULE 9.2 — Button states (minimum 4):** Default, Hovered, Pressed/Active, Disabled. Optional 5th: Loading (spinner).
- **RULE 9.3 — Input states:** Focus (colored border), Error (red border + message), Warning (optional).
- **RULE 9.4 — System feedback:** Loading spinners, success messages, error messages — everywhere.
- **RULE 9.5 — Transitions count:** Apply `transition: all 0.15s ease` to all interactive elements.

---

## 10. MICRO INTERACTIONS

Feedback that goes beyond basic states — confirms the **result** of an action.

- **RULE 10.1 — Beyond states:** Basic states acknowledge input; micro interactions confirm the result.
- **RULE 10.2 — Copy button pattern:** Hover+click = basic feedback. A "Copied!" chip sliding up = micro interaction that confirms the action.
- **RULE 10.3 — Practical to playful:** From confirmation chips to confetti animations — both valid.
- **RULE 10.4 — Purpose is confirmation:** The user must know their action produced the intended result.

---

## 11. OVERLAYS & IMAGE TEXT

Text over images needs careful treatment.

- **RULE 11.1 — Never raw text on images** without treatment.
- **RULE 11.2 — Full overlay is lazy:** Makes text readable but kills the image.
- **RULE 11.3 — Linear gradient (better):** Transparent at top, dark at bottom. Shows image AND makes text readable.
- **RULE 11.4 — Gradient + progressive blur (best):** Add `backdrop-filter: blur()` on top of gradient for a modern, premium look.

---

## QUICK REFERENCE

### NEVER DO
- Display all info at same size/weight (spreadsheet layout)
- Use light borders on dark mode cards
- Use bright saturated chips in dark mode
- Make shadows the most noticeable element
- Use icons larger than adjacent text line-height
- Create interactive elements without hover/active/disabled states
- Place text on images without gradient/blur
- Use more than one font family
- Use more than 6 font sizes
- Add color for decoration without purpose
- Keep default letter-spacing on large headings

### ALWAYS DO
- Use containers/grouping to show element relationships
- Highlight active/selected states with background changes
- Put most important info at top, large, bold
- Use 32px section gap, 16px grouped gap (4-point grid)
- Tighten letter-spacing (-0.02em) and line-height (1.1-1.2) on headings
- Create dark mode depth through lighter surfaces (not shadows)
- Provide 4+ states for every button
- Provide focus + error states for every input
- Confirm actions with micro interactions
- Use gradient + blur for text-over-image overlays
- Match icon size to text line-height
- Use 2:1 padding ratio on buttons
- Use semantic colors (blue=trust, red=danger, green=success, yellow=warning)
- Build color ramps from one primary color
- Apply `transition: 0.15s ease` to all interactive elements

---

## REFERENCE VALUES

**Fonts:** DM Sans, Axiforma, SF Pro, Geist, Plus Jakarta Sans, Montserrat, Unbounded

**Landing page scale:** 64px, 42px, 32px, 20px, 16px, 14px

**Dashboard scale:** 24px, 20px, 18px, 16px, 14px, 12px

**Spacing (4-point grid):** 4, 8, 12, 16, 20, 24, 28, 32, 36, 40px

**Key gaps:** 16px (grouped elements), 32px (section elements)

For complete CSS custom properties, shadow scales, color ramp templates,
button patterns, dark mode tokens, and overlay code — see `references/css-patterns.md`.
