# Tailwind CSS → Astro Scoped Styles Migration

## Overview

Migrating all Tailwind v4 utility classes to Astro native scoped `<style>` tags. Design tokens (colors, fonts) are preserved as CSS custom properties in `:root`. The migration is phased so the site remains functional at every step.

## Approach

- **During migration:** `@import "tailwindcss"` + `@theme {}` stay in `global.css`. Tailwind generates both utility classes (used by unmigrated components) AND CSS custom properties (`--color-*`, `--font-family-*`) used by migrated components' scoped styles.
- **Per component:** Remove all Tailwind utility `class="..."` strings, add a scoped `<style>` block with semantic class names.
- **Phase 5 (final):** Replace `@import "tailwindcss"` + `@theme {}` with a plain `:root {}` block, remove `@tailwindcss/vite` from `astro.config.mjs`, uninstall packages.

## Key Translation Patterns

```css
/* Spacing */
p-8           → padding: 2rem
px-4 py-2     → padding: 0.5rem 1rem
gap-4         → gap: 1rem
mb-6          → margin-bottom: 1.5rem
space-y-4     → > * + * { margin-top: 1rem }
max-w-7xl     → max-width: 80rem

/* Typography */
text-sm       → font-size: 0.875rem
text-xl       → font-size: 1.25rem
text-4xl      → font-size: 2.25rem
font-bold     → font-weight: 700
font-semibold → font-weight: 600
leading-relaxed → line-height: 1.625

/* Colors — CSS custom properties */
text-text-primary   → color: var(--color-text-primary)
text-accent-blue    → color: var(--color-accent-blue)
bg-space-dark       → background: var(--color-space-dark)

/* Opacity modifiers */
bg-accent-blue/10   → background: oklch(from var(--color-accent-blue) l c h / 0.1)
border-accent-blue/30 → border-color: oklch(from var(--color-accent-blue) l c h / 0.3)

/* Flex & Grid */
flex items-center justify-center → display: flex; align-items: center; justify-content: center
grid grid-cols-1 md:grid-cols-3  → display: grid; grid-template-columns: 1fr; @media (min-width:768px) { grid-template-columns: repeat(3,1fr) }

/* Transitions */
transition-colors duration-300 → transition: color 300ms ease
transition-all duration-300    → transition: all 300ms ease

/* Hover */
hover:text-accent-cyan → &:hover { color: var(--color-accent-cyan) }
hover:scale-105        → &:hover { transform: scale(1.05) }

/* Responsive */
md:text-5xl → @media (min-width: 768px) { font-size: 3rem }
/* Breakpoints: sm=640px, md=768px, lg=1024px */

/* Group hover */
group-hover:scale-110 → .parent:hover & { transform: scale(1.1) }

/* Gradients */
bg-gradient-to-b from-space-black to-space-navy →
  background: linear-gradient(to bottom, var(--color-space-black), var(--color-space-navy))

/* Backdrop blur */
backdrop-blur-lg → backdrop-filter: blur(16px)
```

## Custom Global Classes (keep in `global.css`)

These are already plain CSS — keep using them via `class` attributes:
- `.glassmorphism` — frosted glass background + border
- `.glow-border` — animated gradient border on hover
- `.glow-text` — multi-layer text-shadow

---

## Migration Status

### Phase 0 — Infrastructure
| Task | Status |
|---|---|
| Define `:root` CSS tokens (final, Phase 5) | ✅ Done |
| Remove `@import "tailwindcss"` + `@theme {}` | ✅ Done |
| Remove `@tailwindcss/vite` from `astro.config.mjs` | ✅ Done |
| Uninstall `tailwindcss` + `@tailwindcss/vite` packages | ✅ Done (12 packages removed) |

### Phase 1 — Light Components
| File | Tailwind Classes | Status |
|---|---|---|
| `src/components/TechPill.astro` | ~19 | ✅ Done |
| `src/components/Footer.astro` | ~35 | ✅ Done |

### Phase 2 — Moderate Components
| File | Tailwind Classes | Status |
|---|---|---|
| `src/components/Navbar.astro` | ~35 | ✅ Done |
| `src/components/ExperienceTimeline.astro` | ~35 | ✅ Done |
| `src/components/ProductsGrid.astro` | ~30 | ✅ Done |

### Phase 3 — Heavy Components
| File | Tailwind Classes | Status |
|---|---|---|
| `src/components/ExperienceCard.astro` | ~55 | ✅ Done |
| `src/components/StarfieldHero.astro` | ~55 | ✅ Done |
| `src/components/ProductCard.astro` | ~55 | ✅ Done |
| `src/components/GameShowcase.astro` | ~60 | ✅ Done |
| `src/components/AboutSection.astro` | ~75 | ⏸ Deferred (commented out) |

### Phase 4 — Pages
| File | Tailwind Classes | Status |
|---|---|---|
| `src/pages/index.astro` | ~25 | ✅ Done |
| `src/pages/blog/index.astro` | ~40 | ✅ Done |
| `src/pages/blog/[...slug].astro` | ~35 | ✅ Done |

### Phase 5 — Cleanup
| Task | Status |
|---|---|
| Add plain `:root {}` block to `global.css` | ✅ Done |
| Remove `@import "tailwindcss"` from `global.css` | ✅ Done |
| Remove `@theme {}` block from `global.css` | ✅ Done |
| Remove import + plugin from `astro.config.mjs` | ✅ Done |
| Uninstall packages: `npm uninstall tailwindcss @tailwindcss/vite` | ✅ Done |
| Grep verify: no remaining Tailwind utility patterns | ✅ Done |
| `npm run build` — confirm zero errors | ✅ Done — 0 errors, 0 warnings, 5 pages |

---

## Verification Checklist (after each component)

- [ ] `npm run dev` — no console errors
- [ ] Visual comparison at 375px, 768px, 1280px
- [ ] Hover states work
- [ ] Transitions/animations still fire
- [ ] `prefers-reduced-motion` overrides still apply (StarfieldHero, GameShowcase)

## Notes

- **`color-mix()` vs relative color syntax:** Using `oklch(from var(--color-x) l c h / 0.1)` (CSS Relative Color Syntax, widely supported in 2026) for opacity modifiers like `/10`, `/20`, `/30`.
- **Dynamic classes:** Converted to `data-*` attributes selected in scoped CSS (ExperienceCard phase colors, TechPill variants).
- **`group-hover`:** Converted to `.parent:hover .child` combinator selectors in scoped CSS.
- **`space-y-*`:** Some converted to `display: flex; flex-direction: column; gap:` for clarity.
