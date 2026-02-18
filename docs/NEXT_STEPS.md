# Next Steps - Session 2

**Date:** February 15, 2026
**Goal:** Build content sections (Experience, Products, Games)

## Current Status

✅ **Completed:**
- Foundation (Astro + Tailwind v4 + Three.js + GSAP)
- Starfield hero with animations
- Navigation & Footer
- GitHub Actions deployment
- Bug fixes for UI issues

## This Session's Objectives

### 1. Experience Timeline Section ⏳ In Progress
Build an interactive vertical timeline showcasing career history.

**Companies to Feature (7 total + internships):**
1. **Juniper Creates** (May-Jul 2025) - Senior SWE - 1→N PaaS
2. **Meta | Reality Labs** (Aug 2023-May 2025) - Contingent Worker - 0→1 Research
3. **d1g1t Inc.** (Oct 2022-Aug 2023) - Senior SWE - 1→N FinTech
4. **RBC** (Jun 2021-Oct 2022) - Senior SWE - 0→1 Enterprise
5. **Microsoft** (Jun 2018-May 2021) - SWE - N→N+1 Multiple products
6. **Internships** (Expandable section):
   - Microsoft (Sept-Dec 2017) - 3D Viewer
   - theScore (May-Aug 2016) - Android
   - KnowRoaming (Sept-Dec 2015) - Android
   - Uken Games (Jan-May 2015) - QA/Game Design
   - UW HCI Research (May-Aug 2014) - Research Dev

**Design Approach:**
- Vertical timeline with alternating left/right cards (desktop)
- Single column on mobile
- Each card contains:
  - Company logo (placeholder for now)
  - Job title
  - Date range
  - Phase tag (0→1, 1→N, N→N+1)
  - 2-3 key achievements (bullet points)
  - Tech stack pills at bottom
- GSAP ScrollTrigger for entrance animations
- Cards slide in from left/right with stagger
- Timeline dot glows on card hover

**Components to Build:**
- `ExperienceCard.astro` - Individual company card
- `ExperienceTimeline.astro` - Container with timeline line
- `TechPill.astro` - Reusable tech stack badge

**Data Structure:**
```typescript
interface Experience {
  company: string;
  role: string;
  startDate: string;
  endDate: string;
  phase: '0→1' | '1→N' | 'N→N+1';
  description: string;
  achievements: string[];
  techStack: string[];
  logo?: string;
}
```

### 2. Products Showcase Section
Grid layout featuring 3 main products:

**Products:**
1. **Lettucemeet** (https://lettucemeet.com)
   - Description: Scheduling group meetings made easy
   - Tech: React, Node, PostgreSQL, Docker, AWS ECS
   - Links: Live site
   - Visual: Screenshot/mockup

2. **Staunq Trading Chatbot** (https://github.com/ShreyK/staunq)
   - Description: Cryptocurrency + AI Chatbot
   - Tech: NextJS, OpenAI GPT-3, Binance API, Vercel
   - Links: GitHub repo
   - Visual: Screenshot of chat interface

3. **Market Predictor Neural Network** (https://github.com/ShreyK/mp)
   - Description: ML models for crypto price prediction
   - Tech: TensorFlow, Keras LSTM, Python, pandas, sklearn
   - Links: GitHub repo
   - Visual: Model architecture diagram or prediction chart

**Design:**
- 3-column grid on desktop, single column on mobile
- Each card:
  - Hero image/screenshot at top
  - Glassmorphism overlay on hover
  - Title, description, metrics
  - Tech stack pills
  - CTA buttons (View Site / View Code)
  - Glow border animation on hover
- GSAP ScrollTrigger: cards scale up from 0.95 + fade in

**Components:**
- `ProductCard.astro` - Individual product card
- `ProductsGrid.astro` - Container section

### 3. Games Section (Endeavor Featured)
Full-width cinematic showcase for Endeavor game.

**Content:**
- Background: shrey.games GIF/video (gif1.gif)
- Large "ENDEAVOR" title with animated glow
- Subtitle: "3D Deep Space Game"
- Description: Built with Rust + Bevy Engine, cross-platform (Steam, Windows, Linux, macOS)
- Feature highlights:
  - Procedural universe generation
  - Complex ship combat system
  - Sentient ship and station entities
  - Deep space materials and exploration
- CTA Buttons:
  - **Play on Steam** (link to Steam page when available)
  - **Visit shrey.games** (https://shrey.games)
  - **Watch Trailer** (YouTube link if available)
- Social Links: Discord, Twitter (@MrReyRay), YouTube (@ShreyGames)
- Dev log preview (latest updates from shrey.games)

**Design:**
- Full-width section with video/GIF background
- Dark overlay for readability
- Large centered content with gradient text effect
- Icon-based social links
- Animated shimmer effect on title
- Scroll-triggered fade-in for content

**Components:**
- `GameShowcase.astro` - Full Endeavor section

### 4. About/Skills Section (Quick)
Brief bio and skills grid.

**Content:**
- Short bio paragraph (2-3 sentences)
- Education:
  - University of Waterloo - BASc Software Engineering (Honours, Co-Op) 2013-2018
  - Awards: President's Entrance Scholarship, International Engineering, Outstanding Co-Op
- Skills categorized:
  - **Fullstack:** React, Angular, JS/TS
  - **Backend:** Node, Java, Python, Django
  - **DevOps:** Nginx, Jenkins, AWS, Azure
  - **Game Dev:** C#, Lua, Rust, Bevy, Unity
  - **Native Apps:** C#, C++, Java, Kotlin
  - **Databases:** PostgreSQL, MongoDB, DynamoDB
  - **AR/VR:** HoloLens, Meta Quest, Meta Research Devices
  - **Tools:** Git, Docker, Kubernetes, CI/CD

**Design:**
- 2-column layout (bio + education on left, skills grid on right)
- Skills displayed as pill badges with category headers
- Subtle hover effects on skills
- Simple, clean design

## Implementation Order

1. ✅ Fix Footer icon SVGs (DONE)
2. ✅ Fix color variables in global.css (DONE)
3. 🔄 Build Experience Timeline (IN PROGRESS)
4. ⏳ Build Products Showcase
5. ⏳ Build Games/Endeavor Section
6. ⏳ Build About/Skills Section
7. ⏳ Test all sections with real content
8. ⏳ GSAP ScrollTrigger animations for all sections
9. ⏳ Responsive testing (mobile, tablet, desktop)
10. ⏳ Performance audit

## Assets Needed

- [ ] Company logos (Juniper, Meta, d1g1t, RBC, Microsoft, etc.)
- [ ] Lettucemeet screenshots
- [ ] Staunq screenshots
- [ ] Market Predictor visualization
- [ ] Endeavor gameplay GIF/video (can use existing from shrey.games)
- [ ] Profile photo (for About section)
- [ ] OG image for social sharing

## Session Target

By end of session:
- Experience Timeline fully functional with all data
- Products section with placeholder images
- Games section with Endeavor showcase
- About section with skills grid
- All sections scroll-animated with GSAP
- Responsive at 320px, 768px, 1024px, 1920px
- Ready for asset replacement

## Testing Checklist

- [ ] All external links open in new tab
- [ ] All internal links scroll smoothly
- [ ] Animations trigger properly on scroll
- [ ] Mobile menu works
- [ ] All text is readable on backgrounds
- [ ] No layout shift on load
- [ ] Fast load time (<3s)

---

**Next Session:** Blog setup, sample posts, final polish, deployment
