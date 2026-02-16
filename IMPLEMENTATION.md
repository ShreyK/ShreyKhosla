# Portfolio Website Implementation

**Project:** Shrey Khosla Portfolio — shreykhosla.com  
**Started:** February 15, 2026  
**Status:** 🚧 In Progress

## Overview

Building a dark, futuristic portfolio website showcasing professional experience, products, and games. The site will be hosted on GitHub Pages with a custom domain (shreykhosla.com).

## Tech Stack

- **Framework:** Astro 5 (static site generation)
- **Styling:** Tailwind CSS v4 + custom CSS with oklch() colors
- **3D Graphics:** Three.js (vanilla, no React)
- **Animations:** GSAP + ScrollTrigger (now fully free)
- **Content:** Astro Content Collections + MDX
- **Deployment:** GitHub Pages via GitHub Actions
- **Domain:** shreykhosla.com

## Architecture Decisions

### Why Astro?
- Zero JS by default → optimal performance
- Perfect for content-heavy portfolios
- Ships only what's needed (Three.js/GSAP load selectively)
- Built-in content collections for blog
- GitHub Pages static deployment

### Why Vanilla Three.js?
- Hero starfield is a simple particle system
- No need for React's component model
- Avoids 50KB+ React runtime overhead
- Direct WebGL control for performance

### Why GSAP?
- Now 100% free (Webflow acquisition 2025)
- ScrollTrigger is best-in-class
- Framework-agnostic
- Rich feature set (SplitText, timelines)

### Why Tailwind v4?
- CSS-first configuration via @theme
- Vite plugin integration with Astro
- Faster builds than v3 PostCSS approach

## Implementation Checklist

### Phase 1: Foundation ✅ / 🚧 / ⏸️
- [ ] Initialize Astro project
- [ ] Install dependencies (three, gsap, tailwindcss, @tailwindcss/vite)
- [ ] Configure astro.config.mjs (site, Vite plugins, integrations)
- [ ] Set up Tailwind v4 with custom theme
- [ ] Create public/CNAME file
- [ ] Update .gitignore

### Phase 2: Core Layout
- [ ] Create src/layouts/BaseLayout.astro
- [ ] Build responsive navigation (glassmorphism, mobile menu)
- [ ] Add View Transitions API
- [ ] Create Footer component
- [ ] Set up global styles (oklch colors, typography, glow utilities)

### Phase 3: Hero Section (Three.js)
- [ ] Create StarfieldHero.astro component
- [ ] Implement Three.js particle system (BufferGeometry + Points)
- [ ] Add mouse parallax effect
- [ ] Add responsive resize handler
- [ ] Performance optimization (reduce particles on mobile)
- [ ] Respect prefers-reduced-motion
- [ ] Overlay text with GSAP SplitText animation

### Phase 4: Experience Timeline
- [ ] Create ExperienceCard.astro component
- [ ] Build vertical timeline layout
- [ ] Add company data:
  - Juniper Creates (May-Jul 2025)
  - Meta Reality Labs (Aug 2023-May 2025)
  - d1g1t Inc. (Oct 2022-Aug 2023)
  - RBC (Jun 2021-Oct 2022)
  - Microsoft (Jun 2018-May 2021)
  - Internships (expandable)
- [ ] GSAP ScrollTrigger entrance animations
- [ ] Tech stack pills with hover effects
- [ ] Phase tags (0→1, 1→N, N→N+1)

### Phase 5: Products Showcase
- [ ] Create ProjectCard.astro component
- [ ] Build responsive grid layout
- [ ] Add product data:
  - Lettucemeet (200K+ MAU)
  - Staunq Trading Chatbot
  - Market Predictor Neural Network
- [ ] Glassmorphism card styling
- [ ] Hover glow animations
- [ ] GSAP scroll-triggered reveals

### Phase 6: Games Section (Endeavor)
- [ ] Create GameShowcase.astro component
- [ ] Full-width cinematic layout
- [ ] Background video/GIF from shrey.games
- [ ] Animated title with glow effect
- [ ] CTA buttons (Steam, shrey.games)
- [ ] Social links (Discord, Twitter, YouTube)

### Phase 7: Blog / Devlog
- [ ] Configure content collections in src/content.config.ts
- [ ] Create blog schema (title, pubDate, tags, heroImage, draft)
- [ ] Set up src/data/blog/ directory
- [ ] Create BlogCard.astro component
- [ ] Build src/pages/blog/index.astro (listing)
- [ ] Build src/pages/blog/[id].astro (detail page)
- [ ] Add MDX support
- [ ] Create sample devlog posts

### Phase 8: About / Skills
- [ ] Create About section component
- [ ] Add education (UWaterloo, awards)
- [ ] Build skills grid (categorized tech stacks)
- [ ] Create SkillBadge.astro component

### Phase 9: Contact
- [ ] Create ContactSection.astro
- [ ] Email + social links
- [ ] Optional: Formspree contact form
- [ ] Animated CTAs with glow effects

### Phase 10: SEO & Performance
- [ ] Add comprehensive meta tags
- [ ] Configure @astrojs/sitemap
- [ ] Add Open Graph images
- [ ] Create robots.txt
- [ ] Optimize images (Astro Image component)
- [ ] Add font preloading
- [ ] Implement content-visibility for off-screen sections
- [ ] Lighthouse audit (target 95+)

### Phase 11: Accessibility
- [ ] Semantic HTML throughout
- [ ] ARIA labels on interactive elements
- [ ] Keyboard navigation support
- [ ] Color contrast validation (≥4.5:1)
- [ ] Comprehensive prefers-reduced-motion support

### Phase 12: Deployment
- [ ] Create .github/workflows/deploy.yml
- [ ] Configure GitHub Actions (withastro/action@v5)
- [ ] Set GitHub Pages source to "GitHub Actions"
- [ ] Verify build succeeds

### Phase 13: Custom Domain
- [ ] Configure DNS A records (185.199.108-111.153)
- [ ] Configure DNS CNAME (www → username.github.io)
- [ ] Add custom domain in GitHub repo settings
- [ ] Verify domain in GitHub account settings
- [ ] Enable HTTPS enforcement

### Phase 14: Testing & Launch
- [ ] Local dev testing (npm run dev)
- [ ] Build test (npm run build)
- [ ] Responsive testing (320px - 1920px)
- [ ] Cross-browser testing (Chrome, Firefox, Safari)
- [ ] Performance validation
- [ ] Accessibility validation
- [ ] Deploy to production
- [ ] Verify DNS propagation
- [ ] Final production QA

## File Structure

```
shrey.khosla/
├── public/
│   ├── CNAME                    # shreykhosla.com
│   ├── favicon.svg
│   ├── robots.txt
│   └── images/                  # Assets
├── src/
│   ├── components/
│   │   ├── StarfieldHero.astro
│   │   ├── Navbar.astro
│   │   ├── ExperienceCard.astro
│   │   ├── ProjectCard.astro
│   │   ├── GameShowcase.astro
│   │   ├── BlogCard.astro
│   │   ├── SkillBadge.astro
│   │   ├── ContactSection.astro
│   │   └── Footer.astro
│   ├── content.config.ts
│   ├── data/
│   │   └── blog/                # MDX posts
│   ├── layouts/
│   │   ├── BaseLayout.astro
│   │   └── BlogLayout.astro
│   ├── pages/
│   │   ├── index.astro          # Main single-page
│   │   ├── blog/
│   │   │   ├── index.astro
│   │   │   └── [id].astro
│   │   └── projects/
│   │       └── [slug].astro
│   └── styles/
│       └── global.css
├── astro.config.mjs
├── package.json
├── tsconfig.json
└── .github/
    └── workflows/
        └── deploy.yml
```

## Design System

### Colors (oklch)
- **Base:** Deep navy/black (oklch(0.15 0.02 240))
- **Accent:** Electric blue/cyan (oklch(0.65 0.25 240))
- **Glow:** Purple accents (oklch(0.60 0.22 290))
- **Text:** High contrast white/off-white (oklch(0.95 0.01 240))

### Typography
- **Body:** Inter Variable
- **Headings:** Space Grotesk or JetBrains Mono
- **Code:** JetBrains Mono

### Spacing Scale (Tailwind)
- 4px base unit system
- Consistent padding/margins

### Animations
- **Scroll reveals:** GSAP ScrollTrigger with stagger
- **Hero text:** SplitText character animation
- **Hover:** Glow border transitions
- **Page transitions:** Astro View Transitions (fade/slide)

### Motion Safety
- Detect `prefers-reduced-motion`
- Disable Three.js particle animation
- Reduce GSAP effects to simple fades
- Maintain functionality without motion

## Content Structure

### Experience (7 companies)
1. **Juniper Creates** — Senior SWE (May-Jul 2025) — 1→N PaaS
2. **Meta | Reality Labs** — Contingent Worker (Aug 2023-May 2025) — 0→1 Research
3. **d1g1t Inc.** — Senior SWE (Oct 2022-Aug 2023) — 1→N FinTech
4. **RBC** — Senior SWE (Jun 2021-Oct 2022) — 0→1 Enterprise
5. **Microsoft** — SWE (Jun 2018-May 2021) — N→N+1 Consumer products
6. **Internships:** Microsoft, theScore, KnowRoaming, Uken Games, UW HCI

### Products (3 featured)
1. **Lettucemeet** — 200K+ MAU scheduling platform (React, Node, PostgreSQL, Docker, AWS)
2. **Staunq** — Crypto AI Chatbot (NextJS, OpenAI GPT-3, Binance API, Vercel)
3. **Market Predictor** — ML Neural Network (TensorFlow, Keras LSTM, Python, pandas)

### Games
1. **Endeavor** — 3D Deep Space Game (Rust, Bevy Engine, Steam, cross-platform)
   - Links: shrey.games, Steam, Discord, YouTube

### Blog Topics
- Endeavor development logs
- Web performance
- Game development insights
- Engineering experiences

### Education
- **University of Waterloo** — BASc Software Engineering (Honours, Co-Op, 2013-2018)
- **Awards:** President's Entrance Scholarship, International Engineering Student Scholarship, Outstanding Co-Op Performance

### Skills (Categorized)
- **Fullstack:** React, Angular, JS/TS
- **Backend:** Node, Java, Python, Django
- **DevOps:** Nginx, Jenkins, AWS, Azure
- **Game Dev:** C#, Lua, Rust, Bevy, Unity
- **Native Apps:** C#, C++, Java
- **DB:** PostgreSQL, MongoDB, DynamoDB
- **AR/VR:** HoloLens, Meta Quest, Meta Research Devices
- **HCI:** Kinect SDK, large-scale displays

## Links & Assets

- **LinkedIn:** https://linkedin.com/in/shreykhosla
- **Games Site:** https://shrey.games
- **Lettucemeet:** https://lettucemeet.com
- **GitHub:** https://github.com/ShreyK (assumed)
- **Email:** theshreykhosla@gmail.com

### Assets Needed
- [ ] Profile photo (high-res)
- [ ] Company logos (Juniper, Meta, d1g1t, RBC, Microsoft, etc.)
- [ ] Project screenshots (Lettucemeet, Staunq, Market Predictor)
- [ ] Endeavor gameplay GIF/video
- [ ] Favicon (SVG preferred)
- [ ] OG image for social sharing

## Performance Targets

- Lighthouse Performance: ≥95
- Lighthouse Accessibility: ≥95
- Lighthouse Best Practices: ≥95
- Lighthouse SEO: ≥95
- First Contentful Paint: <1.5s
- Time to Interactive: <3.0s
- Cumulative Layout Shift: <0.1

## Browser Support

- Chrome/Edge 115+ (latest 2 versions)
- Firefox 128+ (latest 2 versions)
- Safari 15.4+ (latest 2 versions on macOS/iOS)
- Mobile: iOS Safari 15.4+, Chrome Android 115+

## Notes

- Three.js hero is performance-sensitive — monitor FPS on low-end devices
- GSAP ScrollTrigger requires careful refresh() calls on resize
- Astro Content Collections cache aggressively — clear cache if build issues
- GitHub Pages propagation can take 24h for custom domain DNS
- View Transitions API has varying browser support — graceful degradation

## Resources

- [Astro Docs](https://docs.astro.build)
- [Three.js Docs](https://threejs.org/docs)
- [GSAP Docs](https://gsap.com/docs/v3/)
- [Tailwind CSS v4](https://tailwindcss.com/docs)
- [GitHub Pages Custom Domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

---

**Last Updated:** February 15, 2026
