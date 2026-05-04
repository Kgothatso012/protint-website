# ProTint Colour Mix — Awwwards Site Spec

## 1. Concept & Vision

ProTint Colour Mix is premium mobile paint mixing — the site should feel like walking into an upscale body shop where every surface gleams with colour. Cinematic dark surfaces punctuated by vivid paint splashes. The experience is tactile: paint drips, blobs morph, colours bleed into each other. This is a R109K creative budget — the site should look like it cost that, not R5K.

**Tagline:** "The Art of Perfect Colour. On Site."

---

## 2. Design Language

### Aesthetic Direction
Dark industrial luxury meets liquid colour. Think: a high-end paint实验室 meets a Formula 1 pit garage. Dark carbon backgrounds with paint that *lives* — dripping, flowing, mixing.

### Colour Palette
| Role | Hex | Usage |
|------|-----|-------|
| Background | `#0A0A0F` | Near-black with cool tint |
| Surface | `#14141F` | Card/section backgrounds |
| Surface Alt | `#1E1E2E` | Elevated surfaces |
| Primary Accent | `#FF3B3B` | Crimson — paint red |
| Secondary Accent | `#3B7BFF` | Cobalt blue |
| Tertiary Accent | `#3BFF8C` | Viridian green |
| Quaternary | `#FFD23B` | Cadmium yellow |
| White | `#F5F5F7` | Primary text |
| Muted | `#8B8B9E` | Secondary text |

Paint swatch accents: red `#E53935`, blue `#1E88E5`, green `#43A047`, yellow `#FDD835`, white `#FAFAFA`, black `#212121`

### Typography
- **Display:** Bebas Neue (Google Fonts) — bold condensed, all headings, all caps
- **Body:** Inter (Google Fonts) — clean, readable
- **Accent numbers:** Bebas Neue with large scale

### Spatial System
- Container max: 1200px
- Section padding: 120px vertical desktop, 80px mobile
- Grid: 12-column, 24px gap
- Card radius: 16px

### Motion Philosophy
- **Scroll-driven:** GSAP ScrollTrigger for all section reveals
- **Hero 3D:** Three.js paint blob — slow continuous morphing
- **Micro-interactions:** Magnetic buttons, hover colour shifts, parallax
- **Page transitions:** Smooth scroll, no jarring jumps
- **Loader:** Paint splash → wipe reveal → site fades in

### Visual Assets
- **3D paint blob (Three.js):** Hero — morphing icosahedron with paint-like vertex displacement, coloured point lights
- **Paint drip dividers:** CSS/SVG between sections
- **Colour swatches:** Animated CSS colour circles in services
- **Background texture:** Subtle noise grain overlay

---

## 3. Layout & Structure

```
[Loader] → paint splash + brand reveal
[Hero] → fullscreen 3D paint blob + headline + CTA
[Trust Bar] → 3 icons, horizontal scroll marquee feel
[Services] → 6 cards, 3D paint can icons, hover lift + colour border
[Gallery] → masonry-style grid, 6 jobs, hover zoom + caption
[About] → split: text left, animated colour palette right
[Testimonials] → 3 quotes, dark cards with coloured top border
[Contact] → form left, colour blob right, WhatsApp button
[Footer] → minimal, logo + links + social
```

### Responsive
- Desktop: full multi-column layouts, 3D hero active
- Tablet: 2-column grids, 3D simplified
- Mobile: single column, 3D reduced (or replaced with animated gradient), full touch targets

---

## 4. Features & Interactions

### Loader
- Black screen → paint splatters appear from edges → "ProTint" letters fill with colour → wipe transition to site
- Duration: ~2.5s total
- Skip on click/tap

### Hero
- Three.js scene: morphing blob with vertex noise, coloured point lights (red/blue/yellow)
- Headline: "THE ART OF PERFECT COLOUR. ON SITE." — staggered letter reveal
- Subhead: "Mobile paint mixing & colour matching — we come to your workshop"
- CTA button: "Get a Perfect Match" → scrolls to contact
- Scroll indicator: animated chevron

### Navigation
- Fixed top, transparent → blurs on scroll
- Logo left, nav links right (Services, About, Gallery, Contact)
- Mobile: hamburger → full-screen overlay menu

### Services Cards
- Icon: 3D CSS paint-can with drip
- Hover: card lifts, left border becomes paint colour, icon animates
- 6 services: Mobile Paint Mixing, Colour Matching, Auto Body Shops, Fleet Services, Industrial Coatings, Same-Day Service

### Gallery
- 6 image placeholders (described as "recent paint jobs")
- Hover: scale 1.05, caption slides up from bottom
- Lightbox on click (simple JS modal)

### Contact Form
- Fields: Name, Phone, Email, Service (select), Message
- Validation: required fields
- Submit: button with paint-fill animation on hover
- Success: form replaced with thank-you message

### WhatsApp Button
- Fixed bottom-right
- Opens WhatsApp with pre-filled message
- Pulse animation on idle

---

## 5. Component Inventory

### Button (Primary)
- Default: transparent bg, coloured border, coloured text
- Hover: bg fills with colour from left, text goes dark
- Active: slight scale down
- Focus: coloured outline

### Service Card
- Default: dark surface bg, coloured icon, white heading, muted description
- Hover: lifts 8px, shadow expands, left border accent, icon animates
- 3D paint-can SVG icon

### Gallery Item
- Default: image fills card, slight overlay
- Hover: scale 1.05, overlay darkens, caption slides up
- Caption: project type + location

### Testimonial Card
- Dark surface, coloured top border (rotates through palette)
- Quote text, author name, role

### Form Input
- Dark surface, subtle border
- Focus: border becomes accent colour, subtle glow
- Error: red border + error message below

---

## 6. Technical Approach

- **Single file:** `index.html` — all CSS/JS inline
- **3D:** Three.js r128 via cdnjs
- **Animation:** GSAP 3.12 + ScrollTrigger via cdnjs
- **Fonts:** Google Fonts (Bebas Neue + Inter)
- **No build step** — opens directly in browser
- **Deploy:** GitHub Pages (push to `gh-pages` branch or use `master` with Pages enabled)
- **Repo:** `kgothatso012/protint-website`

---

## Content

**Hero:** "THE ART OF PERFECT COLOUR. ON SITE."
**Subhead:** "Mobile paint mixing & colour matching for auto body shops, panel beaters and fleet operators in Rosslyn, Soshanguve and Pretoria North."

**Services:**
1. Mobile Paint Mixing — "We bring the tinting station to your workshop"
2. Colour Matching — "Spectrophotometer-precise, any vehicle, any year"
3. Auto Body Shops — "Fast turnaround, consistent batches"
4. Fleet Services — "Uniform colour across 5 vehicles or 500"
5. Industrial Coatings — "Industrial enamel, epoxy, PU — mixed on site"
6. Same-Day Service — "Call before noon, colour ready today"

**Trust bar:** ✓ Same-Day Response · ✓ 100% Colour Match Guarantee · ✓ We Come To You

**Testimonials:**
1. "They matched a 2014 VW Amarok basecoat perfectly. Body shop couldn't tell the difference. Will use every time." — Johan V., Auto Craft, Centurion
2. "Our fleet of 40 delivery vans, always different batches. ProTint solved 3 years of colour inconsistency." — Thandi M., Fleet Manager, Rosslyn
3. "Called at 2pm, had perfect tint by 4pm. That's the service we need." — Piet S., Panel Beaters, Soshanguve

**Contact:** info@protint.co.za · WhatsApp link · Form on page
**Service areas:** Rosslyn · Soshanguve · Pretoria North · Centurion · Mabopane · Garankuwa
