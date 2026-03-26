# ❄️ ICE BATTERY — Corporate Homepage

> **Developer:** Afaq Ahmad
> **Project:** Ice Battery K.K. — Premium Corporate Homepage Redesign
> **File:** `index.html` (single-file, zero dependencies except CDN fonts & icons)

---

## 📋 Project Overview

A high-fidelity, fully responsive corporate homepage for **Ice Battery K.K.** — a Japanese thermal energy storage company. The design prioritises immediate brand clarity, delivering the company's mission, vision, history, and product value proposition within the first two seconds of landing.

Built as a single `index.html` file for fast handoff, easy deployment, and zero build-tool overhead.

---

## 👤 Developer

| Field | Detail |
|-------|--------|
| **Name** | Afaq Ahmad |
| **Role** | Frontend Developer / UI Designer |
| **Project Type** | Corporate Homepage — High Fidelity |
| **Deliverable** | Single-file HTML · Responsive · Production-ready |

---

## 🗂️ File Structure

```
ice-battery-homepage/
├── index.html        ← Complete homepage (all HTML + CSS + JS)
└── README.md         ← This file
```

All styles are embedded in `<style>` tags and all scripts in `<script>` tags within `index.html`. External dependencies are loaded via CDN only.

---

## 🎨 Design System

### Colour Palette

| Token | Hex | Usage |
|-------|-----|-------|
| `--midnight` | `#020D16` | Page background |
| `--deep` | `#041C2C` | Section backgrounds |
| `--glacier` | `#0A4F72` | Mid-tone blue |
| `--ice-mid` | `#7AC4E0` | Secondary accent |
| `--accent` | `#00D4FF` | Primary cyan accent |
| `--white` | `#F4F8FB` | Body text |
| `--muted` | `#6A8FA8` | Secondary text |
| `--ice` | `#C8E8F5` | Borders / subtle highlights |

### Typography

| Role | Font | Weight | Usage |
|------|------|--------|-------|
| Display / Headings | **Syne** | 700–800 | H1, H2, section titles |
| Body | **DM Sans** | 300–500 | Paragraphs, descriptions |
| Labels / Data | **DM Mono** | 300–400 | Badges, stats, timestamps |

All fonts loaded via Google Fonts CDN.

### Spacing Scale

```
xs:   0.4rem  (6px)
sm:   0.8rem  (12px)
md:   1.2rem  (19px)
lg:   2rem    (32px)
xl:   3rem    (48px)
2xl:  5rem    (80px)
3xl:  7rem    (112px)
```

### Border Radius

```
Buttons:   4px   (sharp, corporate)
Cards:     8–12px
Badges:    3px
Circles:   50%
```

---

## 📦 External Dependencies (CDN)

| Library | Version | Purpose |
|---------|---------|---------|
| Google Fonts — Syne | latest | Display headings |
| Google Fonts — DM Sans | latest | Body text |
| Google Fonts — DM Mono | latest | Monospace labels |
| Font Awesome | 6.5.0 | Icons (solid + brands) |

No JavaScript frameworks. No build tools. No npm. Pure HTML/CSS/JS.

---

## 🧩 Page Sections

### 1. Navigation (`<nav>`)
- Fixed position, transparent on load
- Frosted glass effect (`backdrop-filter: blur`) on scroll
- Smooth anchor-link navigation
- Hamburger menu for mobile (`≤768px`)

### 2. Hero (`#hero`)
- Full-viewport height
- Animated hex crystal SVG (custom inline SVG)
- Moving grid background (CSS animation)
- Floating radial glow orbs
- Staggered entrance animations (`animation-delay`)
- 4 KPI statistics strip
- Two CTAs: primary + ghost

### 3. Mission (`#mission`)
- Two-column grid (text + hex diagram)
- 3 interactive pillar cards with hover slide
- Animated hexagonal icon cluster (CSS `clip-path`)

### 4. Vision (`#vision`)
- 6-card responsive grid
- Hover-reveal top border line (CSS `scaleX` transform)
- Large decorative typographic watermark ("2050")
- Blockquote-style vision statement

### 5. Timeline (`#timeline`)
- 5-milestone horizontal track
- Scroll-driven animated progress line
- Icon dots with hover/active state
- Collapses to vertical list on mobile

### 6. Numbers Strip (`#numbers`)
- 4 bold KPI figures
- Divider border grid
- Gradient background transition

### 7. Product (`#product`)
- Charge/discharge cycle diagram
- Animated metric progress bars (triggered on scroll)
- 4 value-proposition cards with badge labels

### 8. CTA (`#cta`)
- Centred layout with radial glow background
- Primary + ghost action buttons

### 9. Footer
- 4-column grid: Brand · Product · Company · Resources
- Social icon buttons (LinkedIn, X, YouTube, ResearchGate)
- Live uptime badge with pulsing green dot
- Collapses to single column on mobile

---

## ✨ Interactions & Animations

| Effect | Trigger | Method |
|--------|---------|--------|
| Entrance reveal | Scroll (IntersectionObserver) | CSS `opacity` + `translateY` |
| Nav frost glass | Scroll > 30px | CSS class toggle |
| Timeline progress | Scroll position | JS width calculation |
| Metric bars fill | Section enters viewport | JS `data-width` → CSS width |
| Orb float | Continuous | CSS `@keyframes` |
| Hex crystal rings | Continuous | CSS `@keyframes rotate` |
| Card hover lift | Mouse enter | CSS `transform: translateY` |
| Pillar slide | Mouse enter | CSS `transform: translateX` |
| Top border reveal | Mouse enter | CSS `transform: scaleX` |
| Grid background | Continuous | CSS `@keyframes` drift |

---

## 📱 Responsive Breakpoints

| Breakpoint | Layout Changes |
|------------|----------------|
| `≤1024px` | Hero crystal hidden · Mission diagram hidden · 2-col vision · Stacked product |
| `≤768px` | Nav links hidden → hamburger · Vision 1-col · Timeline vertical |
| `≤480px` | Full single-column · Reduced padding · Numbers stacked |

---

## 🚀 Deployment

### Option A — Static hosting (simplest)
Drop `index.html` into any static host:
- **Netlify** — drag & drop into netlify.com/drop
- **Vercel** — `vercel --prod`
- **GitHub Pages** — push to `gh-pages` branch
- **AWS S3 + CloudFront** — upload and set index document

### Option B — Local preview
```bash
# Using Python (no install needed)
python3 -m http.server 8080

# Using Node.js
npx serve .

# Then open: http://localhost:8080
```

### Option C — Direct open
Open `index.html` directly in any modern browser. All CDN assets load from the internet — ensure an active connection for fonts and icons.

---

## 🔧 Customisation Guide

### Changing brand colours
Edit the `:root` block at the top of the `<style>` tag:
```css
:root {
  --accent: #00D4FF;   /* ← Change this for a different primary accent */
  --glacier: #0A4F72;  /* ← Change this for mid-tone */
}
```

### Updating copy
All text is plain HTML — find any section by its `id` and edit directly:
```html
<section id="mission"> ... </section>
<section id="vision">  ... </section>
```

### Adding/removing timeline items
Each milestone is a `.timeline-item` div inside `.timeline-items`. Copy/paste and update the year, title, and description.

### Swapping icons
Icons use Font Awesome classes. Browse at [fontawesome.com/icons](https://fontawesome.com/icons) and replace any `fa-*` class name.

---

## ✅ Browser Support

| Browser | Support |
|---------|---------|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |
| Opera 76+ | ✅ Full |
| IE 11 | ❌ Not supported |

---

## 📄 Licence & Credits

- **Design & Development:** Afaq Ahmad
- **Client:** Ice Battery K.K., Tokyo, Japan
- **Icons:** Font Awesome 6.5.0 (Free tier)
- **Fonts:** Google Fonts — Syne, DM Sans, DM Mono

---

*Built with precision. Designed for clarity. Deployed for impact.*
*— Afaq Ahmad*
