# Visual Examples & Design Context

Detailed before/after descriptions from the source video. Each section shows
what was wrong, what changed, and why — providing the design *taste* behind
the rules in SKILL.md. Consult this when making design judgment calls.

**Source:** "Every UI/UX Concept Explained in Under 10 Minutes" — Kole Jain (Vi Media)

---

## 1. AFFORDANCES & SIGNIFIERS
*[Timestamp: 00:00 – 00:43]*

### Expanded Concept
UI elements should visually communicate what they do without needing written
instructions. The user should instantly understand relationships, active states,
and interactivity through visual cues alone — these cues are called **signifiers**.

### Detailed Rule Context
- **RULE 1.1:** In the video, three icon+text pairs (Drinks with champagne icon,
  Food with burger icon, Dessert with cookie icon) are shown. Placing a rounded
  container around Drinks+Food instantly signals they are related while Dessert
  is separate.
- **RULE 1.2:** The video shows a pill-shaped highlight around "Food" within the
  group container, signaling it is the currently selected tab and the user can
  toggle to the other option.
- **RULE 1.3:** "Dessert" is shown with light gray text — the user instantly
  knows clicking it won't do anything.

### Visual Examples
- **BEFORE:** Three bare icon+text pairs — Drinks (champagne icon), Food (burger
  icon), Dessert (cookie icon) — all identical styling, no visual differentiation.
- **STEP 1:** A rounded-rectangle container wraps all three items together, with
  a slightly lighter inner pill around "Food" — instantly signals Food is the
  selected tab.
- **STEP 2:** Below the tabs, "The Food Menu" heading appears with menu items
  (Mushroom Risotto, Tagliatelle, Penne Alfredo, Bolognese, Shrimp Linguine,
  Lasagna, Carbonara, Gnocchi) — the content responds to the selected tab.
- **STEP 3:** "Dessert" text shown in light gray with reduced opacity — signals
  disabled state.

---

## 2. VISUAL HIERARCHY
*[Timestamp: 00:47 – 02:01]*

### Expanded Concept
Information should be organized by importance using three tools: **size**,
**position**, and **color**. A card displaying all information at the same
size/weight looks like a spreadsheet, not a design. It is the **contrast** —
the difference between small and big, colorful and not — that actually creates
the hierarchy.

### Detailed Rule Context
- **RULE 2.2:** Images always add a "pop of color" and make scanning super easy.
  Just like Uber's ride selection list uses car images for instant visual scanning.
- **RULE 2.5:** Price "$32.45" is positioned top-right aligned, and colored blue.
  It's different than the rest, which draws the eye to it.
- **RULE 2.6:** Instead of just "Deliver To:" and "Pickup From:" text labels,
  use pin icons and a dotted line to demonstrate that it's moving from Jamesville
  to Syracuse without having to actually say that.
- **RULE 2.7:** "It's not an exact science, and you could definitely end up with
  a design that looks different. And it wouldn't be wrong, but the same ideas
  apply. Most important things near the top, bigger and colorful is more important,
  and images are used whenever possible."

### Visual Examples
- **BEFORE (spreadsheet card):** A flat white card with label:value rows all in
  the same font size and weight:
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
  1. "Restaurant" label removed — Chipotle icon (brown rounded square with pepper
     logo) added at top-left
  2. "Burrito Bowl" made largest/boldest text next to the icon
  3. "Today 9:30am" set small and gray, below the title
  4. "$32.45" moved to top-right in blue color
  5. "Deliver To" / "Pickup From" labels replaced with location pin icons +
     dotted connecting line
- **AFTER v1:** Compact card — icon + "Burrito Bowl" (bold) + "Today 9:30am"
  (small gray) at top, "$32.45" blue top-right, pin icons with locations below.
- **AFTER v2:** Same data but with a large food photograph at top spanning the
  card width, icon overlapping the image bottom edge, same hierarchy beneath.
  Both layouts are valid.

---

## 3. GRIDS, LAYOUTS & SPACING
*[Timestamp: 02:05 – 03:13]*

### Expanded Concept
Grids are guidelines, not rigid rules. White space ("letting things breathe")
is far more important than strict grid compliance. The 4-point grid system
creates consistency not because it inherently looks better, but because you
can always split things in half, which creates consistency throughout a design.

### Visual Examples
- **Landing page with column overlay:** "Track deadlines. Get paid." page with
  pink vertical column lines overlaid — the hero heading, subtext, and buttons
  don't snap to any columns. Point: grids aren't required for custom layouts.
- **Mobile responsive column example:** Same grid overlay shown at desktop
  (12 columns), tablet (8 columns), and mobile (4 columns) on the
  "James Brighton, Sr. Product Designer" portfolio card — demonstrating
  responsive behavior.
- **"Detailed Analytics" section with spacing annotations:** Dark green section
  with:
  - Green dot + "Introducing Data Aggregation" announcement bar (16px font, 20px line-height)
  - "Detailed Analytics" heading (64px font, 72px line-height)
  - Body text "Know exactly who is clicking. Location, Device, Browser, and
    Referrer data." (20px font, 28px line-height)
  - "See it in action →" button
  - Pink annotation labels showing: **16px gap** between announcement and heading,
    **32px gap** between heading and body, **32px gap** between body and button
- **4-point grid visualization:** Row of colored squares increasing in size from
  4px to 28px in 4px increments (4px pink, 8px peach, 12px light yellow, 16px
  yellow, 20px yellow-green, 24px green, 28px light green), demonstrating the
  divisibility principle.
- **Scale comparison (1x → 0.5x → 0.25x):** The same "Detailed Analytics"
  section shown at three proportional scales to demonstrate consistency.

---

## 4. TYPOGRAPHY & FONT SIZING
*[Timestamp: 03:17 – 04:51]*

### Expanded Concept
Design is mostly just text. And for picking a font, you'll never need more than
one for any design. Over the last 7 years of designing, the presenter has rarely
used any fonts other than the recommended ones. This shouldn't be where you're
spending tons of time.

### Detailed Rule Context
- **RULE 4.2:** All 7 fonts displayed in a 2-column grid, each rendered in its
  own typeface. "Unbounded" shown noticeably bolder/heavier than the rest.
- **RULE 4.3:** The presenter calls this "kind of a hack" — tightening letter-
  spacing by -2% to -3% and dropping line-height to 110-120% "instantly makes
  any larger text look super pro, real fast."
- **RULE 4.5:** For dashboards, "that range shrinks dramatically to where you
  don't normally have text sizes larger than 24 pixels because of the increase
  in information density."

### Visual Examples
- **"just text" slide:** Simple centered text on gray background reinforcing
  that design = mostly text.
- **Font grid:** DM Sans, Axiforma, SF Pro, Geist (left column), Plus Jakarta
  Sans, Montserrat, Unbounded (right column). Each shown in its own typeface.
- **Letter-spacing before/after:** The "Tight knit team, fuelling global
  influence" heading on the Linkd landing page with team avatars above and
  "Book a call" (primary filled black) + "Live demo" (ghost) buttons below.
  BEFORE: default letter-spacing feels loose and amateur. AFTER: tightened
  letter-spacing — text feels tighter, more professional, more intentional.
  Visible difference in how the characters sit closer together.
- **Type scale comparison:**
  - LEFT: Landing page scale on dark background — 64px H1, 42px H2, 32px H3,
    20px H4, 16px H5, 14px H6 — shown next to "Detailed Analytics" section
  - RIGHT: Dashboard scale on dark background — 24px H1, 20px H2, 18px H3,
    16px H4, 14px H5, 12px H6 — shown next to "Kangaroo Inc." dashboard with
    sidebar (Home, Analytics, Customers, Partners, Payouts) and "Links" panel
  - Dramatically smaller range for dashboards to fit dense information
- **Mobin inspiration app:** The presenter shows Mobin (sponsor) as a source
  of design inspiration — curated mobile and web app designs from top teams.

---

## 5. COLOR THEORY
*[Timestamp: 04:57 – 05:44]*

### Expanded Concept
Colors are difficult and everyone has their own tastes. Start with one primary
color (generally your brand color). You can lighten it for a good background or
darken it for text colors — both good ways to incorporate subtle color and make
an otherwise drab design look much more interesting.

### Detailed Rule Context
- **RULE 5.3:** "With all of that, we're already halfway to a color ramp, which
  is what large companies use to build out chips, states, charts, and really
  anything else."
- **RULE 5.5:** "As a beginner, let the color find you" — like an announcement
  bar to grab attention, a focus state on an input, or a green "new" chip on a
  link. These are all semantic colors, colors that have meaning and provide
  signifiers to the user.

### Visual Examples
- **Purple color ramp:** ~11 swatches displayed as rounded rectangle chips in a
  horizontal row, graduating from very light lavender through vivid purple to
  very dark indigo.
- **"Raspberry Turkish Delight" card:** Product card using the purple ramp —
  lightest purple as card + page background, medium purple for button + small
  chip at top, dark purple for "Raspberry Turkish Delight" heading text.
  Description reads: "Indulge in a limited edition 24 pack box of raspberry
  turkish delight for the month of February only. While stock lasts."
  Button in mid-purple. "Only 13 left!" urgency text below button.
- **Announcement bar example:** Colored bar at top of page to grab attention.
- **Input focus state:** "FIRST NAME" label above input field with "Kole Jain"
  placeholder, showing colored border glow when focused.
- **Green "New" chip:** Next to "Candidates" in sidebar nav with icons (Home,
  Job listings, Candidates), a green pill badge reads "New" — semantic color
  conveying status information.

---

## 6. DARK MODE
*[Timestamp: 05:48 – 06:17]*

### Expanded Concept
Designing in dark mode presents some pretty interesting challenges. Dark mode
inverts the depth model — shadows don't work, borders need lower contrast, and
bright chip colors are too harsh. Depth is created by making foreground elements
LIGHTER than the background.

### Detailed Rule Context
- **RULE 6.3:** "This chip is also far too bright, so we can dim down the
  saturation and brightness and flip that for the text to create some hierarchy."
- **RULE 6.4:** "There's also a ton of flexibility for deep purples, reds, or
  greens, not just navy blue or gray."

### Visual Examples
- **Bluetooth Speaker card (teal-green):** Dark card (#1a2a24-ish) on darker
  background (#0f1814-ish). "new" chip in desaturated teal green. Card shows:
  "new" chip top-left, "Bluetooth Speaker" heading, "Hear the music" subtext,
  product image (gray fabric speaker), "$149" price bottom-left, "Buy now"
  ghost button bottom-right. Card surface visibly lighter than page.
- **Color variant showcase:** Four versions of the same Bluetooth Speaker card
  side by side on a very dark background:
  1. Teal-green base
  2. Navy-purple base (deep indigo card)
  3. Magenta/red base (deep rose card)
  4. Olive-green base (deep forest card)
  Each with matching desaturated "new" chip color.
- **Dark elevation visual:** A tilted/rotated dark card showing the lighter-
  surface-on-darker-background principle — the 3D perspective angle emphasizes
  that the card "floats" via color difference alone, not shadow.
- **Border contrast fix:** Card border dimmed from visible light to barely-there
  rgba(255,255,255,0.08).
- **Chip desaturation:** Bright green "new" chip toned down — background becomes
  muted/desaturated, text becomes brighter/lighter to maintain readability.

---

## 7. SHADOWS & DEPTH
*[Timestamp: 06:21 – 06:53]*

### Expanded Concept
Shadows are a fantastic tool to use on light mode. But most shadows, along with
the one shown in the video, are too strong. Reducing the opacity and dialing up
the blur helps a lot. The strength needed depends on the foreground/background
relationship. "Just remember, if the shadow is the first thing you notice on a
design, you're not using it right."

### Visual Examples
- **Heavy shadow card:** A card with a dark, opaque, clearly visible drop shadow
  — looks outdated and heavy. Fixed by: lowering opacity from ~0.3 to ~0.06 and
  increasing blur from ~4px to ~12px, becoming a soft, barely-there shadow that
  lifts the card without being noticeable.
- **Elevation comparison:** Cards sitting on a page surface need less shadow
  (low elevation), while popovers/dropdowns that sit above other content need
  stronger shadows (high elevation) to convey the layering.
- **Tactile raised button:** A 3D-looking raised button created using the
  combination of outer shadow (creates the raised/floating appearance) and inner
  shadow/highlight (creates the bevel/depth effect on the button surface itself).

---

## 8. ICONS & BUTTONS
*[Timestamp: 06:54 – 07:27]*

### Expanded Concept
To create strong designs, you'll need icons. Most icons are generally too large.
The trick is to get the line height of your font (in the video's case 24 pixels)
and make the icons the same size. Sidebar links are actually just buttons without
a background until you hover — "ghost buttons." A good guideline for padding is
to double the height for the width.

### Detailed Rule Context
- **RULE 8.1:** "The trick is to get the line height of your font, in this case
  24 pixels, and make the icons the same size. And then tighten up the text."
- **RULE 8.2:** "Sidebar links like this are actually just buttons without a
  background until you hover, which are often called ghost buttons."
- **RULE 8.5:** "A good guideline for padding on these is to double the height
  for the width." Video annotates 16px padding on the "See what we can do" button.

### Visual Examples
- **Sidebar with ghost buttons:** "linkd" sidebar showing: Quick actions (Cmd+K
  shortcut badge), Home (house icon), Job listings (briefcase icon), Candidates
  (people icon + green "New" badge). Icons sized to match text line-height at
  24px. On hover, "Job listings" row shows a subtle gray background fill.
- **Isolated standalone button:** The "Job listings" nav item extracted from the
  sidebar and centered on a blank page — it IS a button with icon + text + subtle
  hover background. Same component, different context.
- **Primary + ghost button pair:** "See what we can do →" (filled black button
  with arrow icon, white text) alongside "Job listings" (transparent background,
  dark text, briefcase icon). The filled button has a pink annotation arrow
  showing "16px padding."
- **"Send offer" + "Message" pair:** On the "James Brighton, Sr. Product Designer"
  profile card — "Send offer" in solid black with white text (primary) next to
  "Message" in light gray/white background (ghost). Shows Projects: 12,
  References: 8, Rating: 4.87 with star icon.

---

## 9. FEEDBACK & STATES
*[Timestamp: 07:31 – 08:05]*

### Expanded Concept
A good rule of design is when a user does anything, there should be a response.
Every button needs at least four states. Inputs are even more critical. And this
applies everywhere — loading spinners when data is fetching, success messages
when an action completes, even micro animations on scroll or swipe. "Every
interaction needs a response."

### Visual Examples
- **Button state table:** 5 numbered rows showing the same "Watch the replay ▶"
  button in a blue/navy color:
  1. **Default** — standard navy blue with play icon
  2. **Hovered** — slightly lighter blue
  3. **Pressed** — noticeably darker blue
  4. **Disabled** — grayed out, reduced opacity, muted
  5. **Loading** — navy blue with a spinning loader icon replacing the play icon
- **Input focus state:** "EMAIL" label above a white input field. When focused,
  the input gets a blue/purple border glow ring signaling active interaction.
- **Input error state:** Same input with red border and error message text below.
- **Toast notification sequence:**
  1. Dark rounded card appears: gear icon + "A new update is available v4.3" +
     description text + "Skip this update" (ghost) + "Install now" (filled) buttons
  2. After clicking "Install now": transforms to show "Update installing... v4.3"
     with green progress bar filling and "8m 32s left" countdown + "Cancel" +
     "Explore features" buttons — demonstrating ongoing system feedback
- **Keyboard shortcut modal:** "Quick access your datasets" modal with animated
  key caps showing Cmd + Shift + K, "Close" (filled) + "All shortcuts" (ghost)
  buttons below — visual response that teaches the user.

---

## 10. MICRO INTERACTIONS
*[Timestamp: 08:09 – 08:33]*

### Expanded Concept
Micro interactions are a form of feedback, but they step things up a notch. For
example, a copy button has states and feedback when you hover and click, but you
still don't know that you've copied anything. Instead, if you have a chip slide
up, that's a micro interaction that confirms the action. These can range from
"highly practical to much more fun and playful."

### Visual Examples
- **Copy interaction sequence on personal site (kolejain.com):**
  Sidebar shows: Youtube (play icon), Instagram (camera icon), LinkedIn (in icon).
  Below the social links, the email "hello@kolejain.com" with timestamp
  "8:58:03 PM MST".
  1. User hovers over email link → cursor changes to pointer
  2. User clicks → email is copied to clipboard
  3. Dark rounded chip with green checkmark badge + "Copied!" text slides UP
     from below the email link
  4. Chip auto-dismisses after ~2 seconds
  The chip has a dark (#1a1a2e) background with white "Copied!" text and a
  green checkmark circle icon on the left.

---

## 11. OVERLAYS & IMAGE TEXT
*[Timestamp: 08:37 – 09:04]*

### Expanded Concept
Overlays are really important because if you screw them up, you're going to ruin
the image and the text too. A full screen overlay works but "doesn't do the image
justice." A linear gradient preserves the image while creating readable text.
Adding progressive blur on top creates "an even more modern look."

### Visual Examples
- **Ski/winter product card — 4 iterations:**
  1. **Raw text on image:** Skier photo (person in red jacket skiing downhill with
     mountains in background) with white "Hit the slopes this winter" text directly
     on the photo — text is hard to read where it overlaps bright snow, image
     details are lost behind the text.
  2. **Full dark overlay:** (implied by transcript) Dark overlay covering entire
     image — text becomes readable but the beautiful ski photo is completely
     obscured, defeating the purpose of using an image.
  3. **Linear gradient:** Skier clearly visible in top ~60% of card. Smooth gradient
     from transparent to dark in the middle zone. Solid dark area at bottom where
     text sits: "Hit the slopes this winter" heading + "New Merino wool socks to
     stay warm all day long" subtext + "Buy now" pill button. A vertical gradient
     preview strip is shown to the right of the card, visualizing the
     transparent-to-opaque transition. Both the image and text work well together.
  4. **Gradient + progressive blur:** Same layout as #3 but the transition zone
     between clear image and dark text area has a subtle frosted glass blur effect.
     The image progressively blurs as it approaches the text area. Most polished,
     modern result. This is the current standard for premium overlays.
