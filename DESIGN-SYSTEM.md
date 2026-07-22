# PHANTOM WORKS — M4Event Design System

> Persona 5 inspired · Dark-first · Red/black · High contrast · Paper cutout shadows
> JetBrains Mono (headings) + Inter (body) · Sharp corners · No gradients · No emoji
> Compiled from: Persona5-DesignSystem + M4Event production rules · 2026-07-18

---

## 1. Design DNA

| Trait | Value |
|-------|-------|
| **Vibe** | Terminal rebellion — hacker chic meets punk elegance |
| **Colors** | Near-black `#0A0A0A`, Phantom Red `#D40000`, white `#FFFFFF` |
| **Typography** | JetBrains Mono (monospace headings) + Inter (clean body) |
| **Shapes** | Sharp corners (`2-4px` radius max), intentional, offset layers |
| **Depth** | Paper cutout red shadows (`0 4px 0 #D40000`) |
| **Labels** | Always UPPERCASE with `0.12em` letter-spacing |
| **Motion** | Fast (`150-300ms`), whip-like easing, staggered entries |
| **Icons** | Inline SVG only — never emoji, never icon fonts |

### Core Principles

1. **Dark-First** — Default is near-black (`#0A0A0A`). Light mode is an afterthought for accessibility.
2. **Red is Power** — Phantom Red (`#D40000`) is the ONLY accent. Never dilute with other accent colors.
3. **Paper Cutouts** — UI elements float with a red offset shadow underneath, creating stacked-paper physicality.
4. **Sharp & Intentional** — Border-radius is minimal (`2-4px`). Every curve is earned.
5. **Typography as Attitude** — JetBrains Mono for headings (terminal feel), Inter for body (clean readable).
6. **Mask Motif** — `.phantom-mask` creates layered cutout effect with offset red frame.

---

## 2. CSS Tokens (Copy-Paste Ready)

### 2.1 Core Tokens — `:root`

```css
:root {
  /* === Colors === */
  --color-primary: #D40000;
  --color-primary-hover: #E60000;
  --color-primary-dark: #9C0000;
  --color-primary-light: #FF5555;
  --color-on-primary: #FFFFFF;
  --color-accent: #FFFFFF;

  /* === Surfaces === */
  --surface-page: #0A0A0A;
  --surface-card: #121212;
  --surface-elevated: #1A1A1A;
  --surface-sunken: #050505;
  --surface-overlay: rgba(0,0,0,0.8);

  /* === Text === */
  --text-primary: #FFFFFF;
  --text-secondary: #D4D4D4;
  --text-tertiary: #6B6B6B;
  --text-disabled: #3D3D3D;
  --text-inverse: #0A0A0A;
  --text-on-action: #FFFFFF;
  --text-link: #FF1A1A;

  /* === Borders === */
  --border-default: #2A2A2A;
  --border-strong: #3D3D3D;
  --border-focus: #E60000;
  --border-inverse: rgba(0,0,0,0.3);

  /* === Actions === */
  --action-primary: #D40000;
  --action-primary-hover: #E60000;
  --action-primary-disabled: #7A0000;
  --action-secondary: #2A2A2A;
  --action-secondary-hover: #3D3D3D;

  /* === Semantic States === */
  --state-success: #22C55E;
  --state-success-bg: rgba(34,197,94,0.12);
  --state-warning: #F59E0B;
  --state-warning-bg: rgba(245,158,11,0.12);
  --state-danger: #FF1A1A;
  --state-danger-bg: rgba(255,26,26,0.12);
  --state-info: #3B82F6;
  --state-info-bg: rgba(59,130,246,0.12);

  /* === Red Ramp (for references) === */
  --red-600: #D40000;
  --red-800: #9C0000;
  --red-400: #FF5555;

  /* === Typography === */
  --font-display: 'JetBrains Mono', 'Fira Code', monospace;
  --font-body: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', monospace;

  /* === Font Sizes (responsive) === */
  --fs-display: clamp(40px, 6vw, 64px);
  --fs-h1: clamp(32px, 4.5vw, 48px);
  --fs-h2: clamp(26px, 3.5vw, 36px);
  --fs-h3: 22px;
  --fs-body: 15px;
  --fs-small: 13px;
  --fs-caption: 11px;

  /* === Spacing Scale === */
  --gap-xs: 8px;
  --gap-sm: 12px;
  --gap-md: 16px;
  --gap-lg: 24px;
  --gap-xl: 32px;
  --gap-2xl: 48px;
  --gap-3xl: 64px;
  --gap-4xl: 96px;

  /* === Radius === */
  --radius-sm: 2px;
  --radius-md: 4px;
  --radius-lg: 8px;
  --radius-xl: 12px;
  --radius-full: 9999px;

  /* === Shadows (paper cutout signature) === */
  --shadow-sm: 0 2px 0 var(--red-600);
  --shadow-md: 0 4px 0 var(--red-600), 0 6px 12px rgba(0,0,0,0.4);
  --shadow-lg: 0 8px 0 var(--red-600), 0 12px 24px rgba(0,0,0,0.5);
  --shadow-xl: 0 12px 0 var(--red-600), 0 20px 40px rgba(0,0,0,0.6);

  /* === Layout === */
  --container: 1120px;
  --gutter: 32px;

  /* === Mobile (iPhone 15 Pro) === */
  --status-bar-height: 54px;
  --home-indicator-height: 34px;
}
```

### 2.2 Light Mode Override

```css
@media (prefers-color-scheme: light) {
  :root {
    --color-primary: #B80000;
    --color-primary-hover: #D40000;
    --color-accent: #D40000;

    --surface-page: #F5F5F0;
    --surface-card: #FFFFFF;
    --surface-elevated: #FFFFFF;
    --surface-sunken: #EAEAE5;
    --surface-overlay: rgba(0,0,0,0.6);

    --text-primary: #0A0A0A;
    --text-secondary: #6B6B6B;
    --text-tertiary: #A1A1A1;
    --text-disabled: #8A8A8A;
    --text-inverse: #FFFFFF;
    --text-on-action: #FFFFFF;
    --text-link: #D40000;

    --border-default: #DDD;
    --border-strong: #BBB;
    --border-focus: #E60000;
    --border-inverse: rgba(255,255,255,0.3);

    --shadow-sm: 0 2px 0 var(--red-600);
    --shadow-md: 0 4px 0 var(--red-600), 0 6px 12px rgba(0,0,0,0.12);
    --shadow-lg: 0 8px 0 var(--red-600), 0 12px 24px rgba(0,0,0,0.15);
    --shadow-xl: 0 12px 0 var(--red-600), 0 20px 40px rgba(0,0,0,0.2);
  }
}
```

### 2.3 Base Reset + Body

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { -webkit-text-size-adjust: 100%; scroll-behavior: smooth; }
body {
  background: var(--surface-page);
  color: var(--text-primary);
  font-family: var(--font-body);
  font-size: var(--fs-body);
  line-height: 1.6;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  overflow-x: hidden;
}
img, svg { display: block; max-width: 100%; }
a { color: inherit; text-decoration: none; }
button { font: inherit; cursor: pointer; border: none; background: none; }
p { text-wrap: pretty; }
h1, h2, h3, h4 { text-wrap: balance; font-family: var(--font-display); }
```

---

## 3. Typography

| Level | Size | Weight | Line-Height | Letter-Spacing | Font | Usage |
|-------|------|--------|-------------|----------------|------|-------|
| Display | `clamp(40px, 6vw, 64px)` | 700 | 1.0 | -0.02em | JetBrains Mono | Hero titles |
| H1 | `clamp(32px, 4.5vw, 48px)` | 700 | 1.1 | -0.01em | JetBrains Mono | Section headers |
| H2 | `clamp(26px, 3.5vw, 36px)` | 700 | 1.15 | -0.01em | JetBrains Mono | Card titles |
| H3 | 22px | 700 | 1.2 | normal | JetBrains Mono | Sub-section titles |
| Body | 15px | 400 | 1.6 | normal | Inter | Paragraphs |
| Small | 13px | 400 | 1.5 | normal | Inter | Secondary info |
| Caption | 11px | 600 | 1.35 | 0.08em | Inter, UPPERCASE | Labels, timestamps |
| Label | 11px | 700 | 1.2 | 0.12em | Inter, UPPERCASE | Button text, nav items |

### Mobile Typography (fixed sizes)

For mobile screens (390px width), use fixed sizes instead of `clamp()`:

| Level | Mobile Size |
|-------|-------------|
| Display | 36px |
| H1 | 28px |
| H2 | 22px |
| H3 | 15px |
| Body | 15px |
| Small | 13px |
| Caption | 11px |
| Label | 11px |

---

## 4. Spacing Rules

### Desktop Spacing

```css
/* Section spacing */
.section { padding-block: clamp(56px, 8vw, 96px); }
.container { max-width: var(--container); margin-inline: auto; padding-inline: var(--gutter); }

/* Grid gaps */
--gap-xs: 8px;    /* Inline element gaps */
--gap-sm: 12px;   /* Card internal gaps */
--gap-md: 16px;   /* Card-to-card spacing */
--gap-lg: 24px;   /* Section sub-elements */
--gap-xl: 32px;   /* Major section dividers */
--gap-2xl: 48px;  /* Between unrelated sections */
--gap-3xl: 64px;  /* Large breaks */
--gap-4xl: 96px;  /* Page-level spacing */
```

### Mobile Spacing

| Context | Value |
|---------|-------|
| Screen content padding | `0 24px 24px` (sides + bottom) |
| Card padding | `20px` (always consistent) |
| Card-to-card gap | `16px` minimum |
| Section margin-bottom | `28px` between major sections |
| Sub-section margin-bottom | `20px` |
| Inline element gaps | `8px` |
| Input padding | `16px` |
| Row/item padding | `16px` |
| Bottom nav height | `80px` |

### Hard Rules

- **No content overlap** — every section must have at least 28-32px of breathing room between unrelated content blocks
- **Consistent card padding** — always `20px`, never vary
- **Consistent screen padding** — always `0 24px 24px` for screen-content containers
- **No `margin-top` on first child** — use margin-bottom on the element above

---

## 5. Components

### 5.1 Buttons

| Variant | Background | Text | Border | Hover |
|---------|-----------|------|--------|-------|
| Primary | `var(--action-primary)` | `var(--text-on-action)` | none | `var(--action-primary-hover)` |
| Secondary | transparent | `var(--text-primary)` | `1.5px solid var(--border-strong)` | bg fills |
| Ghost | transparent | `var(--color-primary)` | none | underline |

**Standardized sizing:**

| Size | Padding | Font | Radius |
|------|---------|------|--------|
| Default | `14px 24px` | Label (11px) | `var(--radius-md)` (4px) |
| SM | `6px 16px` | Label (11px) | `var(--radius-sm)` (2px) |
| LG | `16px 40px` | Small (13px) | `var(--radius-md)` (4px) |

**All buttons:** uppercase text, `0.12em` letter-spacing, `700` weight, `150ms` transitions, `box-shadow: var(--shadow-md)` on primary.

**Follow button (inline variant):**

```css
.follow-btn {
  padding: 6px 16px;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  border-radius: var(--radius-sm);
  background: var(--action-primary);
  color: var(--text-on-action);
  border: none;
}
```

### 5.2 Cards

| Property | Token |
|----------|-------|
| Background | `var(--surface-card)` |
| Border | `1px solid var(--border-default)` |
| Radius | `var(--radius-md)` (4px) |
| Shadow | `var(--shadow-sm)` (2px red offset) |
| Padding | `20px` (always) |
| Title | `var(--font-display)`, `var(--fs-h3)`, 700 |
| Body | `var(--font-body)`, `var(--fs-body)`, `var(--text-secondary)` |

### 5.3 Inputs

| State | Border | Background |
|-------|--------|------------|
| Default | `1px solid var(--border-default)` | `var(--surface-card)` |
| Focus | `2px solid var(--border-focus)` | `var(--surface-card)` |
| Error | `2px solid var(--state-danger)` | `var(--state-danger-bg)` |

**Standardized CSS:**

```css
.input {
  width: 100%;
  padding: 16px;
  background: var(--surface-card);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-md);
  color: var(--text-primary);
  font-family: var(--font-body);
  font-size: 15px;
}
.input:focus {
  outline: none;
  border-width: 2px;
  border-color: var(--border-focus);
}
.input.error {
  border-width: 2px;
  border-color: var(--state-danger);
  background: var(--state-danger-bg);
}
```

**No focus ring shadows** — use `border-width: 2px` only. Focus shadows are an AI visual tell.

### 5.4 Badges

```css
.badge {
  padding: 4px 10px;
  border-radius: var(--radius-full);
  font-size: 10px;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  background: var(--surface-elevated);
  color: var(--text-secondary);
}
.badge-success { background: var(--state-success-bg); color: var(--state-success); }
.badge-warning { background: var(--state-warning-bg); color: var(--state-warning); }
.badge-danger { background: var(--state-danger-bg); color: var(--state-danger); }
.badge-info { background: var(--state-info-bg); color: var(--state-info); }
```

### 5.5 Toggle / Switch

| State | Track | Knob |
|-------|-------|------|
| ON | `var(--color-primary)` | `#FFFFFF`, right |
| OFF | `var(--border-default)` | `#FFFFFF`, left |

Dimensions: `40x22px` track, `18px` knob. Radius: `11px` (pill).

---

## 6. Mobile Screen Architecture

### iPhone 15 Pro Frame

```css
.iphone-frame {
  width: 390px;
  background: var(--surface-page);
  border-radius: 44px;
  border: 3px solid #333;
  overflow: hidden;
  position: relative;
  box-shadow: 0 0 0 1px #555, 0 20px 60px rgba(0,0,0,0.8);
}

.status-bar {
  height: 54px;
  background: var(--surface-page);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 32px;
  font-family: var(--font-body);
  font-size: 14px;
  font-weight: 600;
  color: var(--text-primary);
  position: relative;
}

.dynamic-island {
  position: absolute;
  top: 11px;
  left: 50%;
  transform: translateX(-50%);
  width: 120px;
  height: 33px;
  background: #000;
  border-radius: 20px;  /* Hardware, not a design choice */
}

.screen-content {
  min-height: 700px;
  padding: 0 24px 24px;
}

.home-indicator {
  height: 34px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.home-indicator .bar {
  width: 130px;
  height: 5px;
  background: #333;
  border-radius: 3px;
}
```

### Screen Navigation (multi-screen pages)

```css
.screen-nav {
  position: sticky;
  top: 0;
  z-index: 100;
  background: var(--surface-page);
  padding: 12px 16px;
  width: 100%;
  max-width: 460px;
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  border-bottom: 1px solid var(--border-default);
  margin-bottom: 24px;
}
.screen-nav button {
  background: var(--surface-card);
  border: 1px solid var(--border-default);
  color: var(--text-secondary);
  font-family: var(--font-body);
  font-size: 10px;
  font-weight: 600;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  padding: 6px 10px;
  border-radius: var(--radius-md);
  cursor: pointer;
  transition: all 150ms;
}
.screen-nav button:hover,
.screen-nav button.active {
  background: var(--color-primary);
  color: var(--color-on-primary);
  border-color: var(--color-primary);
}
```

### Bottom Navigation

```css
.bottom-nav {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 80px;
  background: var(--surface-card);
  border-top: 1px solid var(--border-default);
  display: flex;
  align-items: flex-start;
  padding-top: 10px;
  justify-content: space-around;
  z-index: 50;
}
.bottom-nav .nav-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  color: var(--text-tertiary);
  font-size: 10px;
  font-weight: 600;
  letter-spacing: 0.06em;
  text-transform: uppercase;
}
.bottom-nav .nav-item.active {
  color: var(--color-primary);
}
.bottom-nav .nav-item svg {
  width: 22px;
  height: 22px;
}
```

---

## 7. Signature Utilities

### `.phantom-mask` — Layered Paper Cutout

```css
.phantom-mask {
  position: relative;
  border: 2px solid var(--color-primary);
}
.phantom-mask::before {
  content: '';
  position: absolute;
  inset: 6px -6px -6px 6px;
  border: 2px solid var(--color-primary);
  z-index: -1;
}
```

### `.phantom-stripe` — Diagonal Red Corner

```css
.phantom-stripe {
  position: relative;
  overflow: hidden;
}
.phantom-stripe::before {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  width: 100px;
  height: 100px;
  background: var(--color-primary);
  clip-path: polygon(100% 0, 0 0, 100% 100%);
  opacity: 0.15;
}
```

### `.phantom-divider` — Thick Red Rule

```css
.phantom-divider {
  border: none;
  height: 4px;
  background: var(--color-primary);
  margin: 24px 0;
}
```

---

## 8. Icons — Inline SVG Only

**Rule: No emoji. No icon fonts. Only inline SVG.**

All icons in M4Event screens use inline SVG with these attributes:

```css
.icon-sm { width: 16px; height: 16px; }
.icon-md { width: 20px; height: 20px; }
.icon-lg { width: 24px; height: 24px; }
```

Standard fill: `currentColor` (inherits from parent text color).
Standard stroke: `currentColor`, `stroke-width: 1.5` or `2`.

### Common Icons (SVG)

| Icon | Use | SVG |
|------|-----|-----|
| Home | Bottom nav | `<path d="M3 9.5L12 3l9 6.5V20a1 1 0 01-1 1H4a1 1 0 01-1-1V9.5z"/>` |
| Search | Search screens | `<circle cx="11" cy="11" r="7"/><path d="M21 21l-4.35-4.35"/>` |
| Calendar | Event dates | `<rect x="3" y="4" width="18" height="18" rx="2"/><path d="M16 2v4M8 2v4M3 10h18"/>` |
| Ticket | Ticketing | `<path d="M2 9a3 3 0 010-6h20a3 3 0 010 6M2 9v6a3 3 0 003 3h14a3 3 0 003-3V9"/>` |
| Camera | Photo wall | `<path d="M23 19a2 2 0 01-2 2H3a2 2 0 01-2-2V8a2 2 0 012-2h4l2-3h6l2 3h4a2 2 0 012 2z"/><circle cx="12" cy="13" r="4"/>` |
| Bell | Notifications | `<path d="M18 8A6 6 0 006 8c0 7-3 9-3 9h18s-3-2-3-9M13.73 21a2 2 0 01-3.46 0"/>` |
| User | Profile | `<path d="M20 21v-2a4 4 0 00-4-4H8a4 4 0 00-4 4v2"/><circle cx="12" cy="7" r="4"/>` |
| Settings | Settings | `<circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.65 1.65 0 00.33 1.82l.06.06a2 2 0 01-2.83 2.83l-.06-.06a1.65 1.65 0 00-1.82-.33 1.65 1.65 0 00-1 1.51V21a2 2 0 01-4 0v-.09A1.65 1.65 0 009 19.4a1.65 1.65 0 00-1.82.33l-.06.06a2 2 0 01-2.83-2.83l.06-.06A1.65 1.65 0 004.68 15a1.65 1.65 0 00-1.51-1H3a2 2 0 010-4h.09A1.65 1.65 0 004.6 9a1.65 1.65 0 00-.33-1.82l-.06-.06a2 2 0 012.83-2.83l.06.06A1.65 1.65 0 009 4.68a1.65 1.65 0 001-1.51V3a2 2 0 014 0v.09a1.65 1.65 0 001 1.51 1.65 1.65 0 001.82-.33l.06-.06a2 2 0 012.83 2.83l-.06.06A1.65 1.65 0 0019.4 9a1.65 1.65 0 001.51 1H21a2 2 0 010 4h-.09a1.65 1.65 0 00-1.51 1z"/>` |
| Shield | Security/Privacy | `<path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>` |
| Help | Help/FAQ | `<circle cx="12" cy="12" r="10"/><path d="M9.09 9a3 3 0 015.83 1c0 2-3 3-3 3M12 17h.01"/>` |
| Bar Chart | Statistics | `<path d="M18 20V10M12 20V4M6 20v-6"/>` |
| Users | User Management | `<path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.87M16 3.13a4 4 0 010 7.75"/>` |
| Map Pin | Location | `<path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/>` |
| Heart | Likes | `<path d="M20.84 4.61a5.5 5.5 0 00-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 00-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 000-7.78z"/>` |
| Message | Comments | `<path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/>` |
| Clock | Upcoming | `<circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/>` |
| Star | Featured | `<path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>` |
| Download | App Download | `<path d="M21 15v4a2 2 0 01-2 2H5a2 2 0 01-2-2v-4M7 10l5 5 5-5M12 15V3"/>` |
| Menu | Hamburger | `<line x1="3" y1="12" x2="21" y2="12"/><line x1="3" y1="6" x2="21" y2="6"/><line x1="3" y1="18" x2="21" y2="18"/>` |
| Arrow Left | Back | `<path d="M19 12H5M12 19l-7-7 7-7"/>` |
| X | Close | `<line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/>` |
| Check | Checkmark | `<polyline points="20 6 9 17 4 12"/>` |
| Share | Share | `<circle cx="18" cy="5" r="3"/><circle cx="6" cy="12" r="3"/><circle cx="18" cy="19" r="3"/><path d="M8.59 13.51l6.83 3.98M15.41 6.51l-6.82 3.98"/>` |
| Dollar | Payment/Price | `<line x1="12" y1="1" x2="12" y2="23"/><path d="M17 5H9.5a3.5 3.5 0 000 7h5a3.5 3.5 0 010 7H6"/>` |
| Globe | Language | `<circle cx="12" cy="12" r="10"/><path d="M2 12h20M12 2a15.3 15.3 0 014 10 15.3 15.3 0 01-4 10 15.3 15.3 0 01-4-10 15.3 15.3 0 014-10z"/>` |
| Lock | Auth | `<rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0110 0v4"/>` |
| Mail | Email | `<path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><path d="M22 6l-10 7L2 6"/>` |
| Edit | Edit Profile | `<path d="M11 4H4a2 2 0 00-2 2v14a2 2 0 002 2h14a2 2 0 002-2v-7"/><path d="M18.5 2.5a2.12 2.12 0 013 3L12 15l-4 1 1-4 9.5-9.5z"/>` |

---

## 9. Anti-AI-Slop Rules

These patterns are **forbidden** in M4Event designs:

### Gradients
- NO linear-gradient, radial-gradient, or mesh gradients anywhere
- NO gradient backgrounds on cards, sections, or overlays
- Flat, high-contrast surfaces only

### Color
- NO purple, blue, cyan, or neon palettes
- NO aurora backgrounds
- NO floating blurred blobs
- NO random glowing effects
- Red (`#D40000`) is the ONLY accent color

### Shape & Surface
- NO glassmorphism / backdrop-filter: blur (unless explicitly part of a native OS element like Dynamic Island)
- NO neumorphism
- NO oversized border-radius (max 2-4px for UI elements, 8px for large panels)
- NO rounded cards with left colored border accent

### Depth
- NO soft/blurry shadows — the hard red offset shadow IS the brand
- NO fake 3D dashboards
- NO excessive shadows

### Content
- NO emoji as icons — use inline SVG only
- NO generic AI illustrations
- NO isometric characters
- NO decorative circles/shapes with no purpose
- NO "Feature One / Feature Two" placeholder text
- NO invented metrics ("10x faster", "99.9% uptime")
- NO lorem ipsum

### Layout
- NO perfectly symmetrical "AI-generated" spacing
- NO layouts copied from Stripe, Linear, Notion, Apple, or Framer
- Prioritize usability over aesthetics
- Allow natural visual variation

### Visual Hierarchy
- Create emphasis through typography and spacing
- NOT through gradients, glow effects, or oversized elements

### Focus States
- NO box-shadow on input focus — use `border-width: 2px` only
- Focus ring shadows are an AI visual tell

---

## 10. Anti-Patterns (Persona 5)

| Don't | Why |
|-------|-----|
| Gradients | P5 is flat, sharp, high-contrast. No gradients anywhere. |
| Purple/pink/neon | Red is the ONLY accent color. |
| Large border-radius | Keep 2-8px max. Curves must be earned. |
| Emoji as icons | Use inline SVG only. |
| Center everything | Left-align with asymmetric balance. |
| Soft/blurry shadows | Hard red offset shadow IS the brand. |
| Raw hex in components | Every color must reference a CSS custom property. |
| Ignore light mode | Both modes must be tested. Red offset survives in both. |
| Focus ring shadows | Use `border-width: 2px` on focus. |

---

## 11. Page Types & Layout Rhythms

### Landing Page

```
Hero (centered) → Feature cards (3-col grid) → Split layout sections (4x alternating)
→ How It Works (4 steps) → Screens Preview (5 phones) → Testimonials (3 cards)
→ Stats bar → Final CTA → Footer
```

### Mobile App Screens (per file)

```
Screen nav bar (sticky, top) → Screens (shown/hidden via JS) → Each screen:
  iPhone frame → Status bar → Dynamic Island → Screen content → Bottom nav
```

### Standard Section Rhythms

| Page Kind | Rhythm |
|-----------|--------|
| Landing | Hero → 3 features → Split sections → Steps → Screens → Testimonials → CTA |
| Mobile file | 8-12 screens per file, navigated via tab bar |
| Dashboard | Stats cards → Charts → Tables → Activity feed |

---

## 12. Font Import

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;600;700;800&display=swap" rel="stylesheet">
```

---

## 13. M4Event Product Context

- **Product:** M4Event — event management mobile app
- **Company:** M4Vision
- **Target audience:** Event organizers, attendees, partners
- **Platform:** Mobile-first (iOS/Android), responsive landing page
- **MVP features:** Create events, Public/Private, Invitations, Ticketing, QR Code Tickets, Dashboard, Partners, Management, Photo Wall, Live Sharing, Likes/Comments, Statistics
- **Quality benchmark:** Linear, Stripe, Notion, Airbnb, Framer

---

## 14. Screen File Map

| File | Screens | Content |
|------|---------|---------|
| `index.html` | Landing page | Hero, Features, Split sections, How it Works, Screens, Testimonials, CTA, Footer |
| `mobile-auth.html` | 11 screens | Splash, Welcome, Login, Register, Forgot Password, Email Verification, Account Created, Loading, Error, Success, Empty |
| `m4event-discovery.html` | 11 screens | Home, Search, Search Results, Categories, Featured Events, Nearby, Upcoming, Recommendations, Filters, Empty Search, No Internet |
| `m4event-screens-part1.html` | 11 screens | Event Details, Gallery, Participants, Organizers, Partners, Buy Ticket, Checkout, Payment Confirmation, QR Ticket, My Tickets, Ticket Details |
| `m4event-create-dashboard.html` | 10 screens | Create Event Steps 1-5, My Events, Drafts, Upcoming, Past, Dashboard |
| `m4event-social.html` | 8 screens | Photo Wall, Photo Upload, Photo Detail, Likes, Comments, Live Feed, Notifications, Activity Feed |
| `m4event-final.html` | 14 screens | Profile, Edit Profile, Settings, Notifications, Privacy, Security, Help, About, Partner Dashboard, Admin Dashboard, User Mgmt, Event Mgmt, Reports, Statistics, Loading, Empty, Success, Error, 404 |

---

## 15. Checklist (P0 — must pass on every artifact)

- [ ] All colors use CSS custom properties — no raw hex outside `:root`
- [ ] All headings use `var(--font-display)` (JetBrains Mono)
- [ ] All labels are UPPERCASE with `0.12em` letter-spacing
- [ ] No emoji anywhere — only inline SVG icons
- [ ] No gradients anywhere — flat surfaces only
- [ ] No `backdrop-filter: blur()` (except hardware elements like Dynamic Island)
- [ ] No `box-shadow` on input focus — use `border-width: 2px` only
- [ ] Card padding is always `20px`
- [ ] Button padding is always `14px 24px` (default) or `6px 16px` (sm)
- [ ] Screen content padding is always `0 24px 24px`
- [ ] Red is the ONLY accent color — no purple, blue, cyan, neon
- [ ] Every section has at least 28px of breathing room
- [ ] `data-od-id` on every `<section>` (for comment mode targeting)
- [ ] No `scrollIntoView` calls
- [ ] No invented metrics or filler copy
- [ ] Shadow system uses paper cutout red offset only
- [ ] `border-radius: 20px` ONLY on Dynamic Island (hardware, not design)
- [ ] Every interactive element has visible states (hover, active, disabled)

---

> *Phantom Works · M4Event Design System · Compiled 2026-07-18*
