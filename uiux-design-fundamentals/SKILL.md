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
---

# UI/UX Design Fundamentals — Reusable Design Skill

**Source:** "Every UI/UX Concept Explained in Under 10 Minutes" — Kole Jain (Vi Media)

This skill contains extracted design rules for AI agents building web interfaces.
Every rule is actionable and maps directly to CSS/React implementation decisions.

---

## 1. AFFORDANCES & SIGNIFIERS
*[Timestamp: 00:00 – 00:43]*

### Concept
UI elements should visually communicate what they do without needing written instructions.
The user should instantly understand relationships, active states, and interactivity through
visual cues alone — these cues are called **signifiers**.

### Rules
- **RULE 1.1 — Grouping signifier:** Wrap related items in a shared container (border or
  background) to signal they belong together. In the video, three icon+text pairs (Drinks,
  Food, Dessert) are shown — placing a rounded container around Drinks+Food instantly signals
  they are related while Dessert is separate.
- **RULE 1.2 — Selection signifier:** Highlight the active/selected item with an inner
  container or distinct background. The video shows a pill-shaped highlight around "Food"
  within the group container, signaling it is the currently selected tab and the user can
  toggle to the other option.
- **RULE 1.3 — Disabled signifier:** Gray out text and reduce opacity to signal an element
  is inactive/non-interactive. "Dessert" is shown with light gray text — the user instantly
  knows clicking it won't do anything.
- **RULE 1.4 — Required signifier types:** Every interactive UI must include: button press
  states, active navigation highlights, hover states, and tooltips where icon-only controls
  exist.
- **RULE 1.5 — Core principle:** "Good UI has signifiers — the user shouldn't need
  instructions to understand how the interface works."

### Visual Examples from Video
- **BEFORE:** Three bare icon+text pairs — Drinks (champagne icon), Food (burger icon),
  Dessert (cookie icon) — all identical styling, no visual differentiation.
- **STEP 1:** A rounded-rectangle container wraps all three items together, with a slightly
  lighter inner pill around "Food" — instantly signals Food is the selected tab.
- **STEP 2:** Below the tabs, "The Food Menu" heading appears with menu items (Mushroom
  Risotto, Tagliatelle, Penne Alfredo, Bolognese, Shrimp Linguine, Lasagna, Carbonara,
  Gnocchi) — the content responds to the selected tab.
- **STEP 3:** "Dessert" text shown in light gray with reduced opacity — signals disabled state.

### Code Implications
```css
/* Grouping container */
.tab-group {
  display: inline-flex;
  gap: 4px;
  padding: 4px;
  background: #f0f0f0;
  border-radius: 12px;
}

/* Tab item */
.tab-item {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 16px;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.15s ease;
}

/* Selected state — inner container highlight */
.tab-item.active {
  background: #ffffff;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.08);
}

/* Disabled state */
.tab-item.disabled {
  color: #c0c0c0;
  pointer-events: none;
  opacity: 0.5;
}

/* Hover state */
.tab-item:hover:not(.active):not(.disabled) {
  background: rgba(0, 0, 0, 0.04);
}
```

---

## 2. VISUAL HIERARCHY
*[Timestamp: 00:47 – 02:01]*

### Concept
Information should be organized by importance using three tools: **size**, **position**, and
**color**. A card displaying all information at the same size/weight looks like a spreadsheet.
Hierarchy makes it a design.

### Rules
- **RULE 2.1 — Three hierarchy tools:** Size (bigger = more important), Position (top = most
  important), Color (colorful/contrasting = draws the eye). It is the **contrast** — the
  difference between small and big, colorful and not — that creates hierarchy.
- **RULE 2.2 — Image-first cards:** Images at the top of cards add a "pop of color" and make
  scanning easy. Use images whenever possible — like Uber's ride selection list uses car
  images for instant visual scanning.
- **RULE 2.3 — Primary element treatment:** The most important element (item name) should be
  the largest, boldest text, positioned at the top. Otherwise it blends in with secondary info.
- **RULE 2.4 — Secondary info:** Less important data (time, day) should be smaller and
  positioned below the primary element.
- **RULE 2.5 — Price/key metric:** Position price or key metrics top-right, in a distinct
  color (blue in the example — `$32.45`). Being different from surrounding text draws the
  eye to it.
- **RULE 2.6 — Icon-as-label principle:** Replace verbose text labels ("Deliver To:",
  "Pickup From:") with icons + visual connectors. The video replaces label:value pairs with
  pin icons connected by a dotted line between "Syracuse, NY" and "Jamesville, NY" — conveying
  origin→destination without words.
- **RULE 2.7 — Multiple valid layouts:** Hierarchy isn't an exact science. The same card
  can have different valid layouts, but the principles stay the same: important things near
  top, bigger = more important, use images whenever possible.

### Visual Examples from Video
- **BEFORE (spreadsheet card):** A flat white card with label:value rows all in the same
  font size and weight:
  ```
  Restaurant:   Chipotle
  Item:         Burrito Bowl
  Day:          Today
  Time:         9:30am
  Deliver To:   Jamesville, NY
  Pickup From:  Syracuse, NY
  Total Cost:   $32.45
  ```
- **Transformation steps:**
  1. "Restaurant" label removed — Chipotle icon (brown rounded square with pepper logo) added
     at top-left
  2. "Burrito Bowl" made largest/boldest text next to the icon
  3. "Today 9:30am" set small and gray, below the title
  4. "$32.45" moved to top-right in blue color
  5. "Deliver To" / "Pickup From" labels replaced with location pin icons + dotted connecting line
- **AFTER v1:** Compact card — icon + "Burrito Bowl" (bold) + "Today 9:30am" (small gray)
  at top, "$32.45" blue top-right, pin icons with locations below.
- **AFTER v2:** Same data but with a large food photograph at top spanning the card width,
  icon overlapping the image bottom edge, same hierarchy beneath. Both layouts are valid.

### Code Implications
```css
/* Card with hierarchy */
.card {
  border-radius: 12px;
  overflow: hidden;
  background: #fff;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.06);
}

/* Card image — full width at top */
.card-image {
  width: 100%;
  aspect-ratio: 16 / 10;
  object-fit: cover;
}

/* Primary text — largest, boldest */
.card-title {
  font-size: 20px;
  font-weight: 700;
  line-height: 1.2;
}

/* Secondary text — smaller, muted */
.card-subtitle {
  font-size: 14px;
  color: #888;
  line-height: 1.4;
}

/* Key metric — colored, positioned top-right */
.card-price {
  font-size: 16px;
  font-weight: 600;
  color: #3b82f6; /* blue to draw eye */
}

/* Header row with justify-between for title + price */
.card-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}
```

---

## 3. GRIDS, LAYOUTS & SPACING
*[Timestamp: 02:05 – 03:13]*

### Concept
Grids are **guidelines, not rigid rules**. White space ("letting things breathe") is far more
important than strict grid compliance. The **4-point grid system** creates consistency because
every value can be split in half.

### Rules
- **RULE 3.1 — Grids are guidelines:** The 12-column grid and 8px spacing are guidelines, not
  rigid requirements. Custom landing pages often don't align to any columns — and that's fine.
  The video shows a "Track deadlines. Get paid." landing page with a pink column overlay
  demonstrating that the content doesn't align to columns.
- **RULE 3.2 — When grids ARE useful:** For highly structured pages — galleries, blogs,
  repeating content — grids provide responsive guidelines: 12 columns desktop, 8 columns
  tablet, 4 columns mobile.
- **RULE 3.3 — White space is king:** "Letting things breathe" is MORE important than any
  grid system. Spacing creates visual grouping and hierarchy.
- **RULE 3.4 — Exact spacing values (from video annotations):**
  - Heading: **64px font size**, **72px line height**
  - Body/subtext: **20px font size**, **28px line height**
  - Announcement bar text: **16px font size**, **20px line height**
  - Gap between major section items: **32px**
  - Gap between grouped elements: **16px** (e.g., announcement↔heading, heading↔subtext)
- **RULE 3.5 — Spacing-as-hierarchy:** Group elements that belong together with tighter
  spacing (16px) while keeping larger gaps (32px) between separate groups. This is another
  form of visual hierarchy — through spacing alone.
- **RULE 3.6 — 4-point grid system:** All spacing values should be multiples of 4:
  `4 | 8 | 12 | 16 | 20 | 24 | 28 | 32 | 36 | 40`. Not because it inherently looks better,
  but because you can always split values in half, creating mathematical consistency.

### Visual Examples from Video
- **Landing page with column overlay:** "Track deadlines. Get paid." page with pink vertical
  column lines overlaid — the hero heading, subtext, and buttons don't snap to any columns.
  Point: grids aren't required for custom layouts.
- **Mobile responsive column example:** Same grid overlay shown at desktop (12 columns),
  tablet (8 columns), and mobile (4 columns) on the "James Brighton, Sr. Product Designer"
  portfolio card — demonstrating responsive behavior.
- **"Detailed Analytics" section with spacing annotations:** Dark green section with:
  - Green dot + "Introducing Data Aggregation" announcement bar (16px/20px)
  - "Detailed Analytics" heading (64px/72px)
  - Body text (20px/28px)
  - "See it in action →" button
  - Pink annotation labels showing: **16px gap** between announcement and heading,
    **32px gap** between heading and body, **32px gap** between body and button.
- **4-point grid visualization:** Row of colored squares increasing from 4px to 28px in
  4px increments, demonstrating the divisibility principle.
- **Scale comparison (1x → 0.5x → 0.25x):** The same "Detailed Analytics" section shown at
  three scales to demonstrate proportional consistency.

### Code Implications
```css
/* Spacing scale (4-point grid) as CSS custom properties */
:root {
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-7: 28px;
  --space-8: 32px;
  --space-9: 36px;
  --space-10: 40px;
}

/* Section layout — 32px between major items, 16px for grouped elements */
.section {
  display: flex;
  flex-direction: column;
  gap: var(--space-8); /* 32px default section gap */
}

.section .text-group {
  display: flex;
  flex-direction: column;
  gap: var(--space-4); /* 16px grouped element gap */
}

/* Responsive grid columns */
.grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--space-5);
}
@media (max-width: 1024px) {
  .grid { grid-template-columns: repeat(8, 1fr); }
}
@media (max-width: 640px) {
  .grid { grid-template-columns: repeat(4, 1fr); }
}
```

---

## 4. TYPOGRAPHY & FONT SIZING
*[Timestamp: 03:17 – 04:51]*

### Concept
Design is mostly just text. One font is almost always enough. Tighter letter-spacing on large
text is an instant quality upgrade. Landing pages and dashboards have very different
typographic scale ranges.

### Rules
- **RULE 4.1 — One font only:** You will almost never need more than one font for any design.
  Pick one good sans-serif and stick to it. Don't spend excessive time on font selection.
- **RULE 4.2 — Recommended fonts (from video, shown in grid):**
  1. **DM Sans** (geometric, clean)
  2. **Axiforma** (rounded, friendly)
  3. **SF Pro** (Apple system font)
  4. **Geist** (modern, Vercel's font)
  5. **Plus Jakarta Sans** (geometric, versatile)
  6. **Montserrat** (classic, widely available)
  7. **Unbounded** (bold, display/decorative — shown in heavy weight)
- **RULE 4.3 — The letter-spacing hack (instant pro look):**
  - Tighten `letter-spacing` to **-2% to -3%** (`-0.02em` to `-0.03em`)
  - Drop `line-height` to **110% to 120%** (`1.1` to `1.2`)
  - Apply ONLY to larger text (headings, hero text) — not body copy
  - This "instantly makes any larger text look super pro, real fast"
- **RULE 4.4 — Landing page type scale (6 sizes, wide range):**
  - H1: **64px** (hero headings)
  - H2: **42px**
  - H3: **32px**
  - H4: **20px** (body text size)
  - H5: **16px**
  - H6: **14px**
- **RULE 4.5 — Dashboard type scale (6 sizes, compressed range):**
  - H1: **24px** (max — rarely larger due to information density)
  - H2: **20px**
  - H3: **18px**
  - H4: **16px**
  - H5: **14px**
  - H6: **12px**
- **RULE 4.6 — Maximum 6 font sizes:** Whether landing page or dashboard, keep to ~6 font
  sizes maximum per design to maintain consistency.

### Visual Examples from Video
- **"just text" slide:** Simple centered text reinforcing that design = mostly text.
- **Font grid:** All 7 fonts displayed in a 2-column grid, each rendered in its own typeface.
  "Unbounded" shown noticeably bolder/heavier than the rest.
- **Letter-spacing before/after:** The "Tight knit team, fuelling global influence" heading
  on the Linkd landing page. BEFORE: default letter-spacing feels loose and amateur. AFTER:
  tightened letter-spacing — text feels tighter, more professional, more intentional.
  Visible difference in how the characters sit together.
- **Type scale comparison:** Left side shows landing page scale (64px H1 down to 14px H6)
  next to a dark-mode "Detailed Analytics" section. Right side shows dashboard scale
  (24px H1 down to 12px H6) next to a dark-mode "Kangaroo Inc." dashboard — dramatically
  smaller range to fit dense information.

### Code Implications
```css
/* Type scale — Landing pages */
:root {
  --text-h1: 64px;
  --text-h2: 42px;
  --text-h3: 32px;
  --text-h4: 20px;
  --text-h5: 16px;
  --text-h6: 14px;
}

/* Type scale — Dashboards (override) */
.dashboard {
  --text-h1: 24px;
  --text-h2: 20px;
  --text-h3: 18px;
  --text-h4: 16px;
  --text-h5: 14px;
  --text-h6: 12px;
}

/* The letter-spacing hack — apply to headings only */
h1, h2, .heading-xl {
  letter-spacing: -0.02em;
  line-height: 1.15;
}

/* Body text — normal spacing */
p, .body-text {
  font-size: var(--text-h4);
  line-height: 1.4;
  letter-spacing: normal;
}

/* Font family — pick ONE */
body {
  font-family: 'DM Sans', 'Plus Jakarta Sans', 'Geist', system-ui, sans-serif;
}
```

---

## 5. COLOR THEORY
*[Timestamp: 04:57 – 05:44]*

### Concept
Start with one primary/brand color and derive everything from it. Colors should have
**purpose** (semantic meaning), not just be decoration. Let color "find you" — add it where
purpose demands it.

### Rules
- **RULE 5.1 — One primary color:** Start with a single brand color as your primary.
- **RULE 5.2 — Derive from primary:** Lighten the primary for backgrounds, darken it for
  text. Both add subtle, cohesive color without being overwhelming.
- **RULE 5.3 — Build a color ramp:** From lightest (background tint) through mid-tones
  (buttons, chips) to darkest (text). This is what large companies use for chips, states,
  charts, and everything else. The video shows a purple ramp (~11 swatches) from near-white
  lavender through vivid purple to near-black indigo, applied to a "Raspberry Turkish Delight"
  product card where: lightest purple = card background, medium purple = button + chip,
  darkest purple = heading text.
- **RULE 5.4 — Semantic colors with meaning:**
  - **Blue** → trust, links, informational
  - **Red** → danger, urgency, errors, destructive actions
  - **Yellow** → warning, caution
  - **Green** → success, confirmation, positive status
- **RULE 5.5 — Let color find you:** Add color where purpose demands it, not for decoration:
  - Announcement bars → grab attention (accent color)
  - Input focus states → signal active interaction (blue border)
  - Status chips/badges → convey information (green "New" chip)
- **RULE 5.6 — Core principle:** "Use color for purpose, not just for decoration."

### Visual Examples from Video
- **Purple color ramp:** ~11 swatches from very light lavender (#e8e0ff-ish) through vivid
  purple (#5b21b6-ish) to very dark indigo (#1e0a3c-ish), displayed as rounded rectangle
  swatches in a row.
- **"Raspberry Turkish Delight" card:** Product card using the purple ramp — lightest purple
  as card + page background, "Raspberry Turkish Delight" heading in dark purple, buttons in
  mid-purple, "Only 13 left!" urgency text below.
- **Announcement bar example:** Colored bar at top of page to grab attention.
- **Input focus state:** Input field with colored (blue) border when focused.
- **Green "New" chip:** Next to "Candidates" in sidebar nav, a green pill badge reads "New"
  — semantic color conveying status.

### Code Implications
```css
:root {
  /* Primary color ramp (derive from one brand color using HSL) */
  --primary-50:  hsl(260, 80%, 96%);  /* lightest — backgrounds */
  --primary-100: hsl(260, 70%, 90%);
  --primary-200: hsl(260, 65%, 82%);
  --primary-300: hsl(260, 60%, 72%);
  --primary-400: hsl(260, 55%, 60%);
  --primary-500: hsl(260, 50%, 50%);  /* mid — buttons, chips */
  --primary-600: hsl(260, 55%, 42%);
  --primary-700: hsl(260, 60%, 34%);
  --primary-800: hsl(260, 65%, 24%);
  --primary-900: hsl(260, 70%, 16%);  /* darkest — text */

  /* Semantic colors */
  --color-info:    #3b82f6;  /* blue — trust, links */
  --color-danger:  #ef4444;  /* red — errors, destructive */
  --color-warning: #f59e0b;  /* yellow — warnings */
  --color-success: #22c55e;  /* green — success, confirmation */
}
```

---

## 6. DARK MODE
*[Timestamp: 05:48 – 06:17]*

### Concept
Dark mode inverts the depth model. Shadows don't work; instead, depth is created by making
elevated surfaces **lighter** than the background. Borders need lower contrast, and bright
chip colors must be desaturated.

### Rules
- **RULE 6.1 — Lower border contrast:** Light borders on dark backgrounds create too much
  contrast. Reduce border opacity significantly — use `rgba(255, 255, 255, 0.08)` or similar.
- **RULE 6.2 — Elevation through lightness:** Dark mode has no shadows for depth. Instead,
  higher elevation = lighter surface color. Card surfaces should be lighter than the page
  background. The video shows a dark card visibly lighter than its dark background — the
  opposite of light mode where shadows create depth.
- **RULE 6.3 — Desaturate chip colors:** Bright saturated chip backgrounds are too harsh in
  dark mode. Dim both saturation and brightness on chip backgrounds, then **flip** — make chip
  text brighter/lighter to maintain hierarchy. The video shows a bright green "new" chip being
  toned down to a muted teal background with lighter text.
- **RULE 6.4 — Creative base colors:** Dark mode backgrounds don't have to be navy blue or
  gray. The video shows cards with deep purple, deep red/magenta, and deep green backgrounds
  as valid alternatives — the "Bluetooth Speaker" card shown in teal-green, navy-purple,
  deep magenta, and olive-green variants.

### Visual Examples from Video
- **Bluetooth Speaker card:** Dark card on darker background. "new" chip in teal green.
  Card surface is noticeably lighter (#2a2a3e-ish) than the page (#111118-ish).
- **Color variant showcase:** Four versions of the same Bluetooth Speaker card side by side —
  teal-green base, navy-purple base, magenta/red base, olive-green base — showing flexibility
  beyond gray.
- **Dark elevation visual:** A tilted dark card showing the lighter-surface-on-darker-background
  principle — the 3D perspective emphasizes that the card "floats" via color difference, not shadow.

### Code Implications
```css
/* Dark mode surface elevation ladder */
:root[data-theme="dark"] {
  --surface-0: #0f0f14;   /* page background — darkest */
  --surface-1: #1a1a24;   /* card level 1 — slightly lighter */
  --surface-2: #24243a;   /* card level 2 / elevated — lighter still */
  --surface-3: #2e2e4a;   /* popover / modal — lightest */

  --border-color: rgba(255, 255, 255, 0.08); /* subtle borders */
}

/* Dark mode chip — desaturated background + bright text */
.chip-dark {
  background: hsl(160, 20%, 18%);  /* low saturation, low lightness */
  color: hsl(160, 60%, 70%);       /* higher saturation + lightness for text */
}

/* Alternative dark base colors */
.theme-purple { --surface-0: #12091f; --surface-1: #1e1035; }
.theme-red    { --surface-0: #1a0a12; --surface-1: #2d1020; }
.theme-green  { --surface-0: #0a1410; --surface-1: #142a1e; }
```

---

## 7. SHADOWS & DEPTH
*[Timestamp: 06:21 – 06:53]*

### Concept
Shadows create depth in light mode. Most shadows are **too strong**. Shadow strength should
match the element's elevation level. If the shadow is the first thing you notice, it's wrong.

### Rules
- **RULE 7.1 — Most shadows are too strong:** Fix by reducing opacity AND increasing blur
  radius. A heavy dark shadow → reduced opacity + higher blur = subtle, professional shadow.
- **RULE 7.2 — Elevation-based shadow strength:**
  - Cards on a page → **less shadow** (low elevation): `0 1px 3px rgba(0,0,0,0.06)`
  - Popovers/dropdowns above content → **more shadow** (high elevation):
    `0 8px 30px rgba(0,0,0,0.12)`
- **RULE 7.3 — Tactile button effects:** Combine inner and outer shadows to create
  raised/pressed button effects. Inner shadow for the pressed state, outer shadow for the
  raised/default state.
- **RULE 7.4 — The golden rule:** "If the shadow is the FIRST thing you notice on a design,
  you're not using it right." Shadows should be subtle and supportive, never the focal point.

### Visual Examples from Video
- **Heavy shadow card:** A card with a dark, opaque, visible shadow — looks outdated and
  heavy. Fixed by: lowering opacity and increasing blur, becoming a soft, barely-there shadow.
- **Elevation comparison:** Cards with subtle shadow vs popovers needing stronger shadows
  because they sit above other content.
- **Tactile button:** A raised 3D-looking button using the combination of outer shadow
  (raised appearance) and inner shadow (depth/bevel effect).

### Code Implications
```css
/* Shadow elevation scale */
:root {
  --shadow-sm:  0 1px 2px rgba(0, 0, 0, 0.04);
  --shadow-md:  0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.04);
  --shadow-lg:  0 4px 12px rgba(0, 0, 0, 0.08);
  --shadow-xl:  0 8px 30px rgba(0, 0, 0, 0.12);  /* popovers, dropdowns */
}

/* Card — low elevation */
.card { box-shadow: var(--shadow-md); }

/* Popover — high elevation */
.popover { box-shadow: var(--shadow-xl); }

/* Tactile raised button */
.button-tactile {
  box-shadow:
    0 2px 4px rgba(0, 0, 0, 0.1),           /* outer shadow — raised */
    inset 0 1px 0 rgba(255, 255, 255, 0.15); /* inner highlight — bevel */
}
.button-tactile:active {
  box-shadow:
    0 0 0 rgba(0, 0, 0, 0),                 /* no outer shadow — pressed down */
    inset 0 2px 4px rgba(0, 0, 0, 0.1);     /* inner shadow — pressed */
  transform: translateY(1px);
}
```

---

## 8. ICONS & BUTTONS
*[Timestamp: 06:54 – 07:27]*

### Concept
Icons should match the text line-height for visual alignment. Sidebar navigation links are
just ghost buttons. Button horizontal padding should be double the vertical padding.

### Rules
- **RULE 8.1 — Icon size = text line-height:** Most icons are too large. Set icon width and
  height to match the line-height of adjacent text. If line-height is 24px, icons should be
  24px. Then tighten the gap between icon and text.
- **RULE 8.2 — Ghost buttons:** Sidebar navigation links are just buttons without a
  background — they only show a background on hover. These are called "ghost buttons."
  The video shows a sidebar with icons (Quick actions, Home, Job listings, Candidates, etc.)
  — when hovered, a subtle background appears.
- **RULE 8.3 — Sidebar link = standalone button:** If you isolate a sidebar link and center
  it, you get a perfectly good standalone button. This is the mental model: nav items and
  buttons are the same component.
- **RULE 8.4 — Primary + ghost pair:** Ghost buttons are used as the secondary CTA alongside
  a filled primary CTA. The video shows: "See what we can do →" (filled black button with
  arrow icon) next to "Job listings" (ghost button with briefcase icon).
- **RULE 8.5 — Button padding ratio 2:1:** Horizontal padding = 2x vertical padding. The
  video annotates **16px vertical padding** on the "See what we can do" button, implying
  ~32px horizontal padding. Example: `padding: 12px 24px` or `padding: 16px 32px`.
- **RULE 8.6 — Icons optional:** Buttons work with or without icons. Both are valid.

### Visual Examples from Video
- **Sidebar with ghost buttons:** "linkd" sidebar showing: Quick actions (Cmd+K), Home,
  Job listings, Candidates (with green "New" badge). Icons sized to match text line-height.
  On hover, "Job listings" shows a subtle gray background fill.
- **Isolated standalone button:** The "Job listings" nav item extracted and centered — it's
  a button with icon + text + subtle hover background.
- **Primary + ghost button pair:** "See what we can do →" (filled black, white text, icon)
  alongside "Job listings" (transparent background, dark text, icon). The filled button has
  a pink annotation showing "16px padding."
- **"Send offer" + "Message" pair:** Another primary+secondary example — "Send offer" in
  solid black, "Message" in light gray/white ghost style.

### Code Implications
```css
/* Icon sizing — match line-height */
.icon {
  width: 24px;   /* match adjacent text line-height */
  height: 24px;
  flex-shrink: 0;
}

/* Button base */
.button {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 12px 24px;  /* 2:1 ratio — horizontal = 2x vertical */
  border-radius: 8px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.15s ease;
}

/* Primary (filled) button */
.button-primary {
  background: #111;
  color: #fff;
}
.button-primary:hover { background: #333; }

/* Ghost (secondary) button */
.button-ghost {
  background: transparent;
  color: #111;
}
.button-ghost:hover { background: rgba(0, 0, 0, 0.05); }

/* Nav/sidebar link (ghost button variant) */
.nav-link {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 16px;
  border-radius: 8px;
  background: transparent;
  transition: background-color 0.15s ease;
}
.nav-link:hover { background: rgba(0, 0, 0, 0.05); }
.nav-link.active { background: rgba(0, 0, 0, 0.08); font-weight: 600; }
```

---

## 9. FEEDBACK & STATES
*[Timestamp: 07:31 – 08:05]*

### Concept
When a user does **anything**, there must be a visual response. Every interactive element
needs multiple states. Every interaction needs feedback — loading spinners, success messages,
error indicators.

### Rules
- **RULE 9.1 — Core principle:** "When a user does anything, there should be a response."
  No silent interactions.
- **RULE 9.2 — Button states (minimum 4, ideally 5):** The video shows a table with a blue
  "Watch the replay ▶" button in 5 states:
  1. **Default** — base color (e.g., navy blue)
  2. **Hovered** — slightly darker/lighter
  3. **Pressed/Active** — noticeably darker
  4. **Disabled** — grayed out, reduced opacity
  5. **Loading** — same button with a spinner icon replacing or alongside the label
- **RULE 9.3 — Input states (minimum 3):**
  - **Focus state** — colored border (blue) when user clicks into the field
  - **Error state** — red border + error message text below the field
  - **Warning state** — for optional/non-blocking issues
- **RULE 9.4 — System-level feedback everywhere:**
  - Loading spinners when data is fetching
  - Success messages when actions complete (video shows toast: "A new update is available v4.3"
    with progress bar changing to "Update installing... v4.3 — 8m 32s left")
  - Error messages when things fail
- **RULE 9.5 — Micro-animations count as feedback:** Animations on scroll, swipe, or state
  changes all serve as feedback — "every interaction needs a response."

### Visual Examples from Video
- **Button state table:** 5 rows showing the same "Watch the replay ▶" button:
  Row 1: Default (navy blue), Row 2: Hovered (slightly lighter),
  Row 3: Pressed (darker), Row 4: Disabled (gray, muted),
  Row 5: Loading (navy blue with spinner icon)
- **Input focus state:** "EMAIL" label above input field with blue border glow when focused.
- **Toast notification:** Dark rounded card showing "A new update is available v4.3" with
  "Skip this update" and "Install now" buttons. Then transforms to show "Update installing...
  v4.3" with green progress bar and "8m 32s left" — demonstrating ongoing feedback.
- **Keyboard shortcut modal:** "Quick access your datasets" modal showing Cmd+Shift+K with
  animated/highlighted key caps — visual response teaching the user.

### Code Implications
```css
/* Button states */
.button:hover  { filter: brightness(1.1); }
.button:active { filter: brightness(0.9); transform: translateY(1px); }
.button:disabled, .button[aria-disabled="true"] {
  opacity: 0.5;
  cursor: not-allowed;
  pointer-events: none;
}
.button.loading {
  position: relative;
  pointer-events: none;
  color: transparent;
}
.button.loading::after {
  content: '';
  position: absolute;
  width: 16px; height: 16px;
  border: 2px solid rgba(255,255,255,0.3);
  border-top-color: #fff;
  border-radius: 50%;
  animation: spin 0.6s linear infinite;
}
@keyframes spin { to { transform: rotate(360deg); } }

/* Input states */
.input:focus {
  outline: none;
  border-color: var(--color-info);
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.15);
}
.input.error {
  border-color: var(--color-danger);
  box-shadow: 0 0 0 3px rgba(239, 68, 68, 0.1);
}
.input-error-message {
  color: var(--color-danger);
  font-size: 14px;
  margin-top: 4px;
}

/* Transition for all interactive states */
button, a, input, select, textarea {
  transition: all 0.15s ease;
}
```

---

## 10. MICRO INTERACTIONS
*[Timestamp: 08:09 – 08:33]*

### Concept
Micro interactions are a form of feedback that goes beyond basic states. They **confirm**
that an action actually produced the intended result. They range from practical (confirmation
chips) to playful (confetti animations).

### Rules
- **RULE 10.1 — Beyond states:** Micro interactions are an elevated form of feedback. Basic
  states (hover, active) acknowledge input; micro interactions confirm the **result**.
- **RULE 10.2 — The copy button pattern:** A copy button with hover + click states is basic
  feedback — but you still don't know the copy succeeded. A "Copied!" chip sliding up after
  the click is a micro interaction that **confirms** the clipboard action. The video shows:
  dark rounded chip with green checkmark + "Copied!" text appearing below the email link
  after clicking.
- **RULE 10.3 — Practical to playful range:** From "highly practical" (confirmation chips,
  green checkmarks, progress indicators) to "much more fun and playful" (confetti, bouncy
  animations, wiggle effects). Both ends of the spectrum are valid.
- **RULE 10.4 — Purpose is always confirmation:** The user must know their action produced
  the intended result. Without confirmation, the user is left uncertain.

### Visual Examples from Video
- **Copy interaction sequence:** User hovers over email "hello@kolejain.com" → cursor
  changes → clicks → dark rounded chip slides up from below with green checkmark icon +
  "Copied!" text → chip auto-dismisses after a moment. The chip has a dark (#1a1a2e)
  background with white text and green checkmark badge.

### Code Implications
```css
/* Slide-up confirmation chip */
.copied-chip {
  position: absolute;
  bottom: -40px;
  left: 50%;
  transform: translateX(-50%) translateY(8px);
  background: #1a1a2e;
  color: #fff;
  padding: 6px 14px;
  border-radius: 20px;
  font-size: 14px;
  display: flex;
  align-items: center;
  gap: 6px;
  opacity: 0;
  transition: opacity 0.2s ease, transform 0.2s ease;
  pointer-events: none;
  white-space: nowrap;
}

.copied-chip.visible {
  opacity: 1;
  transform: translateX(-50%) translateY(0);
}
```

```jsx
// React pattern for copy confirmation
function CopyButton({ text }) {
  const [copied, setCopied] = useState(false);

  const handleCopy = async () => {
    await navigator.clipboard.writeText(text);
    setCopied(true);
    setTimeout(() => setCopied(false), 2000);
  };

  return (
    <div style={{ position: 'relative' }}>
      <button onClick={handleCopy}>{text}</button>
      <span className={`copied-chip ${copied ? 'visible' : ''}`}>
        <CheckIcon /> Copied!
      </span>
    </div>
  );
}
```

---

## 11. OVERLAYS & IMAGE TEXT
*[Timestamp: 08:37 – 09:04]*

### Concept
Text over images needs careful treatment. Full overlays are lazy — they kill the image.
**Linear gradients** preserve the image while making text readable. **Progressive blur on
top of the gradient** is the modern, premium approach.

### Rules
- **RULE 11.1 — Never raw text on images:** Placing text directly on a photograph without
  any treatment ruins both the image and the text readability.
- **RULE 11.2 — Full overlay is lazy:** A solid dark overlay makes text readable but
  "doesn't do the image justice" — the image is obscured.
- **RULE 11.3 — Linear gradient (better):** A gradient that is transparent at the top
  (preserving the image) and fades to a dark solid at the bottom (creating a readable text
  area). This shows the image AND makes text readable.
- **RULE 11.4 — Gradient + progressive blur (best/modern):** Add a progressive blur
  (`backdrop-filter: blur()`) on top of the gradient. The image blurs gradually into the
  text area for a premium, contemporary look. This is the current modern standard.

### Visual Examples from Video
- **Ski/winter product card — 4 iterations:**
  1. **Raw:** Skier photo with white "Hit the slopes this winter" text directly on the image
     — text is hard to read, image details are lost behind text.
  2. **Full overlay:** (implied) Dark overlay covering entire image — text is readable but
     image beauty is lost.
  3. **Linear gradient:** Skier clearly visible in top 60% of card, smooth gradient from
     transparent to dark in middle zone, solid dark at bottom where "Hit the slopes this
     winter" heading + "New Merino wool socks to stay warm all day long" subtext + "Buy now"
     button sit — both image and text work well. A gradient preview strip is shown to the
     right of the card, showing the transparent-to-opaque transition.
  4. **Gradient + progressive blur:** Same layout but the transition zone has a subtle
     frosted glass blur effect — the image progressively blurs as it approaches the text area.
     Most polished, modern result.

### Code Implications
```css
/* Overlay container */
.image-card {
  position: relative;
  border-radius: 16px;
  overflow: hidden;
}

.image-card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Linear gradient overlay (GOOD) */
.image-card .gradient-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to top,
    rgba(0, 0, 0, 0.85) 0%,
    rgba(0, 0, 0, 0.5) 40%,
    transparent 65%
  );
}

/* Progressive blur + gradient (BEST — modern) */
.image-card .blur-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to top,
    rgba(0, 0, 0, 0.85) 0%,
    rgba(0, 0, 0, 0.4) 40%,
    transparent 65%
  );
  backdrop-filter: blur(0px);
  -webkit-backdrop-filter: blur(0px);
  mask-image: linear-gradient(
    to top,
    black 0%,
    black 30%,
    transparent 70%
  );
  -webkit-mask-image: linear-gradient(
    to top,
    black 0%,
    black 30%,
    transparent 70%
  );
}

/* Text content positioned at bottom */
.image-card .content {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 24px;
  color: #fff;
  z-index: 1;
}
```

---

## MASTER CHECKLIST — QUICK REFERENCE

### NEVER DO
- Display all information at the same size/weight (spreadsheet layout)
- Use light borders on dark mode cards
- Use bright saturated chip colors in dark mode
- Make shadows the most noticeable element on a design
- Use icons larger than the adjacent text's line-height
- Create interactive elements without hover/active/disabled states
- Place text on images without gradient/blur treatment
- Use more than one font family per design
- Use more than 6 font sizes per page
- Add color purely for decoration without semantic purpose
- Keep default letter-spacing on large headings
- Leave the user uncertain whether their action succeeded

### ALWAYS DO
- Use containers/grouping to show relationships between elements
- Highlight active/selected states with background changes
- Put the most important info at the top, large, and bold
- Use 32px as default gap, 16px for grouped elements (4-point grid)
- Tighten letter-spacing (-2% to -3%) and line-height (110-120%) on headings
- Create depth in dark mode through lighter surface colors (not shadows)
- Provide 4+ states for every button (default, hover, active, disabled)
- Provide focus + error states for every input
- Confirm actions with micro interactions (e.g., "Copied!" chip)
- Use linear gradient + optional blur for text-over-image overlays
- Match icon size to adjacent text line-height
- Use 2:1 width:height padding ratio on buttons
- Use semantic colors (blue=trust, red=danger, green=success, yellow=warning)
- Build color ramps from one primary color (lighten for bg, darken for text)
- Use images in cards/content whenever possible for visual scanning
- Apply transitions (0.15s ease) to all interactive state changes

---

## RECOMMENDED FONTS (from video)

| # | Font | Character |
|---|------|-----------|
| 1 | DM Sans | Geometric, clean, versatile |
| 2 | Axiforma | Rounded, friendly |
| 3 | SF Pro | Apple system font, neutral |
| 4 | Geist | Modern, Vercel's font |
| 5 | Plus Jakarta Sans | Geometric, versatile |
| 6 | Montserrat | Classic, widely available |
| 7 | Unbounded | Bold, display/decorative |

---

## SPACING SCALE (4-point grid)

```
4px | 8px | 12px | 16px | 20px | 24px | 28px | 32px | 36px | 40px
```

**Key values from video:**
- **16px** → grouped element gap (announcement↔heading, heading↔subtext)
- **32px** → section element gap (between major components)
- **64px** → heading font size (landing page H1)
- **72px** → heading line height
- **20px** → body text font size
- **28px** → body text line height
- **16px** → announcement bar font size
- **20px** → announcement bar line height

---

## TYPE SCALES

**Landing page scale:**
`64px → 42px → 32px → 20px → 16px → 14px`

**Dashboard scale:**
`24px → 20px → 18px → 16px → 14px → 12px`

---

## CSS CUSTOM PROPERTIES STARTER

```css
:root {
  /* Spacing (4-point grid) */
  --space-1: 4px;  --space-2: 8px;  --space-3: 12px;
  --space-4: 16px; --space-5: 20px; --space-6: 24px;
  --space-7: 28px; --space-8: 32px; --space-9: 36px;
  --space-10: 40px;

  /* Typography — Landing page */
  --text-h1: 64px; --text-h2: 42px; --text-h3: 32px;
  --text-h4: 20px; --text-h5: 16px; --text-h6: 14px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0,0,0,0.04);
  --shadow-md: 0 1px 3px rgba(0,0,0,0.06), 0 1px 2px rgba(0,0,0,0.04);
  --shadow-lg: 0 4px 12px rgba(0,0,0,0.08);
  --shadow-xl: 0 8px 30px rgba(0,0,0,0.12);

  /* Semantic colors */
  --color-info:    #3b82f6;
  --color-danger:  #ef4444;
  --color-warning: #f59e0b;
  --color-success: #22c55e;

  /* Transitions */
  --transition-fast: 0.15s ease;
}
```
