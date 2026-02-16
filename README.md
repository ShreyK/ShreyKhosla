# Shrey Khosla Portfolio

[![Deploy to GitHub Pages](https://github.com/ShreyK/ShreyKhosla/actions/workflows/deploy.yml/badge.svg)](https://github.com/ShreyK/ShreyKhosla/actions/workflows/deploy.yml)

**Live Site:** [shreykhosla.com](https://shreykhosla.com)

Professional portfolio showcasing 7+ years of software engineering experience across full-stack development, game development, and AR/VR research at companies including Meta, Microsoft, RBC, and startups.

## Features

- 🌌 **Interactive 3D Hero** — Three.js starfield with parallax effects
- ⚡ **GSAP Animations** — Smooth scroll-triggered reveals and transitions
- 🎮 **Games Showcase** — Featured: Endeavor (Rust/Bevy deep space game on Steam)
- 💼 **Experience Timeline** — 7 companies, 0→1 to N→N+1 product phases
- 🚀 **Products** — Lettucemeet (200K+ MAU), Staunq, Market Predictor
- 📝 **Blog/Devlog** — MDX-powered content collections
- 🎨 **Dark Futuristic Design** — oklch() colors, glassmorphism, glowing accents
- ♿ **Accessible** — WCAG 2.1 AA compliant, motion-safe fallbacks
- 🚀 **Performance** — Lighthouse 95+ scores, optimized for speed

## Tech Stack

- **Framework:** [Astro 5](https://astro.build) — Zero JS by default, static site generation
- **Styling:** [Tailwind CSS v4](https://tailwindcss.com) — CSS-first configuration
- **3D Graphics:** [Three.js](https://threejs.org) — Vanilla implementation, no React overhead
- **Animations:** [GSAP](https://gsap.com) + ScrollTrigger — Now fully free
- **Content:** Astro Content Collections + MDX
- **Deployment:** GitHub Pages via GitHub Actions
- **Domain:** Custom domain (shreykhosla.com) with HTTPS

## Project Structure

```
shrey.khosla/
├── docs/                        # Documentation
│   ├── IMPLEMENTATION.md        # Detailed implementation tracking
│   ├── NEXT_STEPS.md           # Session planning and objectives
│   └── BUGFIXES.md             # Bug tracking and resolutions
├── public/
│   ├── CNAME                    # Custom domain configuration
│   ├── favicon.svg
│   ├── robots.txt
│   └── images/                  # Static assets
├── src/
│   ├── components/              # Reusable Astro components
│   │   ├── StarfieldHero.astro  # Three.js hero section
│   │   ├── Navbar.astro
│   │   ├── ExperienceCard.astro
│   │   ├── ExperienceTimeline.astro
│   │   ├── ProductCard.astro
│   │   ├── ProductsGrid.astro
│   │   ├── GameShowcase.astro
│   │   ├── TechPill.astro
│   │   └── Footer.astro
│   ├── content.config.ts        # Content collections schema
│   ├── data/
│   │   └── blog/                # MDX blog posts
│   ├── layouts/
│   │   ├── BaseLayout.astro     # Global layout
│   │   └── BlogLayout.astro
│   ├── pages/
│   │   ├── index.astro          # Main single-page site
│   │   └── blog/                # Blog routes
│   └── styles/
│       └── global.css           # Tailwind + custom theme
├── astro.config.mjs
├── package.json
└── .github/
    └── workflows/
        └── deploy.yml           # GitHub Actions deployment
```

## Development

### Prerequisites

- Node.js 18+ recommended
- npm or pnpm

### Setup

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

The dev server will start at `http://localhost:4321`

### Environment

No environment variables required — fully static site.

## Deployment

Deployed automatically to GitHub Pages via GitHub Actions on push to `main` branch.

### Custom Domain Setup

1. **DNS Configuration** (at domain registrar):
   - A Records (`@`) → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - CNAME (`www`) → `<username>.github.io`

2. **GitHub Settings**:
   - Repository → Settings → Pages → Custom domain → `shreykhosla.com`
   - Enable "Enforce HTTPS" after DNS propagation

3. **CNAME File**:
   - Already included in `public/CNAME` with domain name

## Performance

- Lighthouse Performance: 95+
- First Contentful Paint: <1.5s
- Time to Interactive: <3.0s
- Cumulative Layout Shift: <0.1

Optimizations:
- Zero JS by default (Astro Islands architecture)
- Lazy-loaded Three.js hero (only on viewport)
- Optimized images (WebP/AVIF via Astro Image)
- Font preloading
- CSS `content-visibility` for off-screen sections

## Accessibility

- Semantic HTML throughout
- ARIA labels on interactive elements
- Keyboard navigation support
- Color contrast ≥4.5:1
- `prefers-reduced-motion` support (disables Three.js animation, reduces GSAP effects)

## Browser Support

- Chrome/Edge 115+
- Firefox 128+
- Safari 15.4+
- Mobile: iOS Safari 15.4+, Chrome Android 115+

## Links

- **Live Site:** [shreykhosla.com](https://shreykhosla.com)
- **LinkedIn:** [linkedin.com/in/shreykhosla](https://linkedin.com/in/shreykhosla)
- **Games:** [shrey.games](https://shrey.games)
- **Lettucemeet:** [lettucemeet.com](https://lettucemeet.com)
- **Email:** theshreykhosla@gmail.com

## License

© 2026 Shrey Khosla. All rights reserved.

---

**Implementation Docs:** See [docs/](./docs/) folder for detailed development tracking:
- [IMPLEMENTATION.md](./docs/IMPLEMENTATION.md) - Full implementation checklist and architecture
- [NEXT_STEPS.md](./docs/NEXT_STEPS.md) - Session planning and objectives  
- [BUGFIXES.md](./docs/BUGFIXES.md) - Bug tracking and resolutions
