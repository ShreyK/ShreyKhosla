# Portfolio Website Development Log

## Project Brief

Building a professional portfolio website for Shrey Khosla (shreykhosla.com) — a dark, futuristic showcase of 7+ years experience as a Senior Software Engineer across startups and enterprise (Meta, Microsoft, RBC, d1g1t, Juniper Creates).

**Key Features:**
- 3D Three.js starfield hero section
- Experience timeline with GSAP scroll animations
- Products showcase (Lettucemeet 200K+ MAU, Staunq, Market Predictor)
- Featured game section (Endeavor on Steam/shrey.games)
- Blog/devlog with MDX support
- Custom domain with GitHub Pages

**Tech Stack:**
- Astro 5 (static generation)
- Tailwind CSS v4
- Three.js (vanilla)
- GSAP + ScrollTrigger
- MDX content collections

## Session Notes

### February 15, 2026
- Initial planning and architecture decisions
- Created comprehensive implementation plan
- Selected Astro over Next.js for zero-JS default
- Chose vanilla Three.js over R3F to avoid React overhead
- GSAP selected (now fully free from Webflow acquisition)
- Started implementation with project scaffolding

#### Session 1: Foundation & Core Setup (Completed)
**Completed:**
- ✅ Created IMPLEMENTATION.md with detailed project tracking
- ✅ Updated README.md with project overview and setup instructions  
- ✅ Updated Claude.md for session tracking
- ✅ Configured .gitignore for Node/Astro project
- ✅ Initialized Astro 5 project with minimal template
- ✅ Installed dependencies: astro, @astrojs/mdx, @astrojs/sitemap, tailwindcss@4, @tailwindcss/vite, three, gsap
- ✅ Configured astro.config.mjs with site URL, MDX, sitemap, Tailwind v4 Vite plugin
- ✅ Created global.css with Tailwind v4 @theme, oklch() color system, custom utilities
- ✅ Set up content collections for blog/devlog (src/content.config.ts)
- ✅ Created BaseLayout.astro with SEO meta tags, Open Graph, fonts
- ✅ Built responsive Navbar component with glassmorphism, mobile menu
- ✅ Built Footer component with social links, quick links
- ✅ Created basic page structure (index.astro) with all main sections
- ✅ Added public/CNAME file for custom domain (shreykhosla.com)
- ✅ Added public/robots.txt with sitemap reference
- ✅ Created public/favicon.svg with SK branding
- ✅ Set up GitHub Actions deployment workflow (.github/workflows/deploy.yml)
- ✅ Built Three.js StarfieldHero component with:
  - 3000 particles with depth-layered starfield
  - Mouse parallax effect
  - Gentle rotation animation
  - Color palette (blue/cyan/purple theme)
  - Performance optimizations (capped pixel ratio, reduced particles on low-end)
  - prefers-reduced-motion support (1000 stars, no animation)
  - GSAP text entrance animations
- ✅ Successfully built and tested locally
- ✅ Committed initial setup to git

**Tech Stack Confirmed:**
- Astro 5.1.0
- Tailwind CSS 4.0.0 with Vite plugin (CSS-first config via @theme)
- Three.js 0.171.0 (vanilla, no React)
- GSAP 3.12.7 (free, includes ScrollTrigger)
- @astrojs/mdx 4.1.0
- @astrojs/sitemap 3.2.2
- TypeScript 5.7.0

**Design System:**
- Colors: oklch() for perceptual uniformity
  - Base: oklch(0.10 0.01 240) - deep space black
  - Navy: oklch(0.20 0.03 240)
  - Accent Blue: oklch(0.65 0.25 240)
  - Accent Cyan: oklch(0.75 0.20 200)
  - Accent Purple: oklch(0.60 0.22 290)
- Typography: Inter Variable (body), Space Grotesk (headings), JetBrains Mono (code)
- Effects: Glassmorphism (backdrop-blur), glow borders, animated gradients

**Next Steps:**
- Build Experience Timeline section with company cards and GSAP ScrollTrigger
- Build Products showcase section (Lettucemeet, Staunq, Market Predictor)
- Build Games section (Endeavor featured)
- Set up blog pages and sample posts
- Add About/Education section
- Performance optimizations and accessibility audit

