# M4Event — Implementation Handoff

This archive is the source of truth for turning the design into production code. Each HTML file is a self-contained mobile screen prototype. Start from `m4event-all-screens.html` (the assembled viewer) to browse all screens, then use individual files for implementation.

## Implementation target
- Build production UI from the exported HTML screens, not a loose reinterpretation.
- Preserve typography scale, spacing rhythm, color tokens, zero-radius, and component states.
- Replace static placeholders only when the target app has real data or functional equivalents.
- Keep generated UI free of preview labels or design-process annotations.
- Treat this handoff as a visual contract: if implementation choices conflict, match the exported pixels and behavior first, then refactor internals.

## Design system
Full token reference: `DESIGN-SYSTEM.md`

Key tokens extracted from actual CSS:
- `--color-primary: #E61919`
- `--surface-page: #0B0B0B`
- `--text-primary: #ECECEA`
- `--font-display: 'Archivo Black', 'Inter', sans-serif`
- `--font-body: 'JetBrains Mono', 'IBM Plex Mono', ui-monospace, monospace`
- `--radius-*: 0` (brutalist zero)

## Source map
| File | Screens | Content |
|------|---------|---------|
| `m4event-auth.html` | 10 | Splash → Welcome → Login → Register → Forgot Password → Email Verification → Account Created → Loading → Error → Success → Empty |
| `m4event-discovery.html` | 10 | Home → Search → Results → Categories → Featured → Nearby → Upcoming → Recommendations → Filters → Empty → No Internet |
| `m4event-screens-part1.html` | 11 | Event Detail → Gallery → Participants → Organizers → Partners → Buy Ticket → Checkout → Payment Confirmation → My Ticket → My Tickets → Ticket Details |
| `m4event-manage.html` | 10 | Create Steps 1-5 → My Events → Dashboard → Analytics → Revenue → Activity |
| `m4event-social.html` | 7 | Photo Wall → Upload → Photo Detail → Likes → Comments → Live Feed → Notifications → Activity Feed |
| `m4event-final.html` | 18 | Profile → Edit → Settings → Notifications → Privacy → Security → Help → About → Partner Dashboard → Admin Overview → Users → Events Manage → Reports → Loading → Empty → Success → Error → 404 |
| `m4event-landing.html` | Landing | Marketing landing page (hero, features, steps, CTA) |
| `m4event-all-screens.html` | 69 (assembled) | All screens in a side-by-side viewer with sidebar navigation |

## Responsive contract
Validate across this viewport matrix:
- Mobile compact: 360×800
- Mobile standard: 390×844
- Mobile large: 430×932
- Foldable / small tablet: 600×960
- Tablet portrait: 820×1180
- Desktop: 1440×900

All screens are designed at 390px width (iPhone 15 Pro). Use a fixed-width phone frame for mobile contexts; scale proportionally for larger viewports.

## Files removed (not in this archive)
- `mobile-auth.html` — merged into `m4event-auth.html`
- `m4event-create-dashboard.html` — renamed to `m4event-manage.html`
- `index.html` — replaced by `m4event-all-screens.html` (assembled viewer)

## Supporting files
- `DESIGN-SYSTEM.md` — Full design token reference
- `DESIGN-MANIFEST.json` — Machine-readable screen map
- `critique.json` — Design critique notes
- `README.md` — Project overview

## Coding checklist for AI tools
1. Open `DESIGN-SYSTEM.md` and extract tokens before writing components.
2. Implement each HTML file as its own route/surface; keep landing page separate from app screens.
3. Use extracted tokens: colors, type scale (Archivo Black headings + JetBrains Mono body), zero-radius, flat surfaces.
4. All buttons, labels, nav items must be UPPERCASE with letter-spacing.
5. Use inline SVG icons — no emoji, no icon fonts.
6. Preserve interactive controls, hover/focus/pressed states, form behavior.
7. No box-shadow on input focus — use `border-width: 2px` only.
8. No gradients, no glassmorphism, no rounded corners.
9. Confirm the production result visually matches the exported design before refactoring internals.
10. If a detail is ambiguous, keep the exported HTML/CSS behavior rather than inventing a new pattern.
