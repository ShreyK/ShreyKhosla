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

#### Session 2: Content Sections & Bug Fixes (Completed)
**Completed:**
- ✅ Fixed Footer social icons (proper SVG markup with set:html)
- ✅ Reorganized documentation into docs/ folder
- ✅ Created docs/BUGFIXES.md for tracking UI issues
- ✅ Created docs/NEXT_STEPS.md for session planning
- ✅ Built complete Experience Timeline:
  - 7 companies: Juniper Creates, Meta, d1g1t, RBC, Microsoft
  - 5 internships: Microsoft, theScore, KnowRoaming, Uken Games, UW HCI
  - Alternating left/right cards (desktop), single column (mobile)
  - GSAP ScrollTrigger entrance animations with stagger
  - Phase tags (0→1, 1→N, N→N+1) with color coding
  - Tech stack pills with hover effects
  - Timeline line with glowing dots
  - Expandable internships section
- ✅ Built Products Showcase Grid:
  - 3 products: Lettucemeet (200K+ MAU), Staunq, Market Predictor
  - Responsive 3-column grid (desktop) to single column (mobile)
  - Glassmorphism cards with glow-border hover effects
  - GSAP ScrollTrigger staggered animations
  - CTA buttons (View Live / View Code)
  - Placeholder for product screenshots
- ✅ Built Games/Endeavor Section:
  - Full-width cinematic showcase
  - Animated shimmer gradient on "ENDEAVOR" title
  - Feature highlights grid (4 features)
  - CTA buttons (Steam, shrey.games)
  - Social links (Discord, Twitter, YouTube)
  - Dev log preview from shrey.games
  - Background gradient (ready for gameplay GIF/video)
- ✅ Successfully built and tested locally
- ✅ Committed all changes to git

**Components Created:**
- TechPill.astro - Reusable tech stack badges
- ExperienceCard.astro - Company/internship cards
- ExperienceTimeline.astro - Full timeline section
- ProductCard.astro - Product showcase cards
- ProductsGrid.astro - Products section
- GameShowcase.astro - Endeavor featured section

**Next Steps:**
- Set up blog with MDX content collections and sample posts
- Add About/Skills section with education and tech stack grid
- Add placeholder images for products
- Performance audit and optimizations
- Deploy to GitHub Pages
- Test custom domain configuration

