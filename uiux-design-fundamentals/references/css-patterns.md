# CSS Patterns Reference

Complete CSS code patterns for implementing the UI/UX design rules.
Read this file when you need specific CSS values, custom properties, or
implementation patterns.

---

## Design Tokens Starter

```css
:root {
  /* Spacing — 4-point grid */
  --space-1: 4px;  --space-2: 8px;  --space-3: 12px;
  --space-4: 16px; --space-5: 20px; --space-6: 24px;
  --space-7: 28px; --space-8: 32px; --space-9: 36px;
  --space-10: 40px;

  /* Typography — Landing page scale */
  --text-h1: 64px; --text-h2: 42px; --text-h3: 32px;
  --text-h4: 20px; --text-h5: 16px; --text-h6: 14px;

  /* Shadows — elevation-based */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.04);
  --shadow-md: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.04);
  --shadow-lg: 0 4px 12px rgba(0, 0, 0, 0.08);
  --shadow-xl: 0 8px 30px rgba(0, 0, 0, 0.12);

  /* Semantic colors */
  --color-info:    #3b82f6;
  --color-danger:  #ef4444;
  --color-warning: #f59e0b;
  --color-success: #22c55e;

  /* Transitions */
  --transition-fast: 0.15s ease;
}
```

---

## Primary Color Ramp

Derive from one brand color using HSL. Replace hue 260 with your brand hue.

```css
:root {
  --primary-50:  hsl(260, 80%, 96%);
  --primary-100: hsl(260, 70%, 90%);
  --primary-200: hsl(260, 65%, 82%);
  --primary-300: hsl(260, 60%, 72%);
  --primary-400: hsl(260, 55%, 60%);
  --primary-500: hsl(260, 50%, 50%);
  --primary-600: hsl(260, 55%, 42%);
  --primary-700: hsl(260, 60%, 34%);
  --primary-800: hsl(260, 65%, 24%);
  --primary-900: hsl(260, 70%, 16%);
}
```

---

## Dashboard Type Scale Override

```css
.dashboard {
  --text-h1: 24px; --text-h2: 20px; --text-h3: 18px;
  --text-h4: 16px; --text-h5: 14px; --text-h6: 12px;
}
```

---

## Heading Typography (Letter-Spacing Hack)

```css
h1, h2, .heading-xl {
  letter-spacing: -0.02em;
  line-height: 1.15;
}

p, .body-text {
  font-size: var(--text-h4);
  line-height: 1.4;
  letter-spacing: normal;
}

body {
  font-family: 'DM Sans', 'Plus Jakarta Sans', 'Geist', system-ui, sans-serif;
}
```

---

## Affordances & Signifiers

```css
/* Grouping container */
.tab-group {
  display: inline-flex;
  gap: 4px;
  padding: 4px;
  background: #f0f0f0;
  border-radius: 12px;
}

/* Tab item base */
.tab-item {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 16px;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.15s ease;
}

/* Selected state */
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

## Card with Visual Hierarchy

```css
.card {
  border-radius: 12px;
  overflow: hidden;
  background: #fff;
  box-shadow: var(--shadow-md);
}

.card-image {
  width: 100%;
  aspect-ratio: 16 / 10;
  object-fit: cover;
}

.card-title {
  font-size: 20px;
  font-weight: 700;
  line-height: 1.2;
}

.card-subtitle {
  font-size: 14px;
  color: #888;
  line-height: 1.4;
}

.card-price {
  font-size: 16px;
  font-weight: 600;
  color: #3b82f6;
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}
```

---

## Section Spacing

```css
.section {
  display: flex;
  flex-direction: column;
  gap: var(--space-8); /* 32px section gap */
}

.section .text-group {
  display: flex;
  flex-direction: column;
  gap: var(--space-4); /* 16px grouped gap */
}
```

---

## Responsive Grid

```css
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

## Dark Mode Tokens

```css
:root[data-theme="dark"] {
  --surface-0: #0f0f14;   /* page background */
  --surface-1: #1a1a24;   /* card level 1 */
  --surface-2: #24243a;   /* card level 2 */
  --surface-3: #2e2e4a;   /* popover/modal */
  --border-color: rgba(255, 255, 255, 0.08);
}

/* Desaturated chip in dark mode */
.chip-dark {
  background: hsl(160, 20%, 18%);
  color: hsl(160, 60%, 70%);
}

/* Alternative dark base colors */
.theme-purple { --surface-0: #12091f; --surface-1: #1e1035; }
.theme-red    { --surface-0: #1a0a12; --surface-1: #2d1020; }
.theme-green  { --surface-0: #0a1410; --surface-1: #142a1e; }
```

---

## Shadow Scale

```css
.card    { box-shadow: var(--shadow-md); }
.popover { box-shadow: var(--shadow-xl); }

/* Tactile raised button */
.button-tactile {
  box-shadow:
    0 2px 4px rgba(0, 0, 0, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.15);
}
.button-tactile:active {
  box-shadow:
    0 0 0 rgba(0, 0, 0, 0),
    inset 0 2px 4px rgba(0, 0, 0, 0.1);
  transform: translateY(1px);
}
```

---

## Buttons

```css
.button {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 12px 24px; /* 2:1 ratio */
  border-radius: 8px;
  font-weight: 500;
  cursor: pointer;
  transition: all var(--transition-fast);
}

.button-primary {
  background: #111;
  color: #fff;
}
.button-primary:hover { background: #333; }

.button-ghost {
  background: transparent;
  color: #111;
}
.button-ghost:hover { background: rgba(0, 0, 0, 0.05); }

/* Icon sizing — match line-height */
.icon { width: 24px; height: 24px; flex-shrink: 0; }

/* Nav link (ghost button variant) */
.nav-link {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 16px;
  border-radius: 8px;
  background: transparent;
  transition: background-color var(--transition-fast);
}
.nav-link:hover { background: rgba(0, 0, 0, 0.05); }
.nav-link.active { background: rgba(0, 0, 0, 0.08); font-weight: 600; }
```

---

## Button & Input States

```css
/* Button states */
.button:hover  { filter: brightness(1.1); }
.button:active { filter: brightness(0.9); transform: translateY(1px); }
.button:disabled, .button[aria-disabled="true"] {
  opacity: 0.5;
  cursor: not-allowed;
  pointer-events: none;
}

/* Loading state */
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

/* Global transitions */
button, a, input, select, textarea {
  transition: all 0.15s ease;
}
```

---

## Micro Interaction (Copied Chip)

```css
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

### React Pattern for Copy Confirmation

```jsx
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

## Image Overlay Patterns

```css
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

/* Linear gradient (GOOD) */
.gradient-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to top,
    rgba(0, 0, 0, 0.85) 0%,
    rgba(0, 0, 0, 0.5) 40%,
    transparent 65%
  );
}

/* Gradient + progressive blur (BEST) */
.blur-overlay {
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
  mask-image: linear-gradient(to top, black 0%, black 30%, transparent 70%);
  -webkit-mask-image: linear-gradient(to top, black 0%, black 30%, transparent 70%);
}

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
