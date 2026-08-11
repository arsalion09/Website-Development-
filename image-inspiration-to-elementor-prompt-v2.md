# Image Inspiration → HTML / Tailwind CSS / JS (Elementor-Ready Build)

## 0. Required Inputs (fill in before running — do not proceed with any bracket unfilled)

**Reference image:** Attach the design mockup/inspiration image directly to this prompt. If no image is attached, stop and ask for one before generating anything.

**Business details:**
- Business name: [Use Unique Business Name]
- Business type / industry: [Decide from Image Provided e.g. plumbing company, law firm, restaurant, SaaS product]
- Sections to include: [e.g. Home, Services, About, Service Areas, Reviews, Contact]
- Sections to exclude: [e.g. Financing, Blog — write "none" if not applicable]
- Page structure (choose one):
  - [ ] ONE scrollable one-page landing site with anchor nav
  - [ ] Multi-page site with separate URLs (list pages: [ ])

**Tailwind delivery method (choose one):**
- [ ] CDN `<script src="https://cdn.tailwindcss.com">` — fast, no build step, correct default for a static handoff file
- [ ] Compiled build (only if the user has a build pipeline — state this explicitly if chosen, since it changes portability)

**CSS naming convention:** [default: BEM — `.block__element--modifier`, e.g. `.hero-card__title--large`]

**Accessibility target:** [default: WCAG 2.1 AA]

**Stock photo sourcing method (choose one):**
- [ ] Hotlink directly from Pexels/Unsplash CDN URLs (acceptable for prototypes; flag as fragile for production)
- [ ] Download images into an `/assets/images/` folder and reference locally (recommended for anything beyond a demo)

---

## 1. Design System Extraction (mandatory first step — output this before any code)

Before writing a single line of HTML, analyze the attached image and produce a written design system spec covering:

- **Color palette**: exact hex values for background, primary/accent, secondary accent, body text, heading text, card/section backgrounds, border colors. Note which colors repeat as CTAs vs decorative accents.
- **Typography**: heading font family + fallback stack, body font family + fallback stack, font weights used (e.g. 400/600/700), a full sizing scale (h1 through h6, body, small/caption), and line-height/letter-spacing if distinctive.
- **Component patterns**: button shapes (radius, padding, border treatment, hover behavior), card styles (shadow depth, radius, border), icon treatment (line vs filled, size, color), spacing rhythm (base spacing unit, section padding), and any recurring decorative motifs (blobs, gradients, dividers, patterns).
- **Layout structure**: header (height, logo placement, nav style, sticky behavior), hero (layout type, image/copy split, CTA placement), and the structural pattern of each repeating section type (e.g. "3-column icon-card grid," "alternating image/text rows").

Present this as a short structured spec (table or bullet list) before generating code, so the design system can be reviewed/corrected before build.

---

## 2. Build Requirements

Build the site as **HTML + Tailwind CSS + vanilla JS**, structured for later conversion into a **native Elementor JSON template** using only free/native Elementor elements — never the HTML widget, with one exception: any contact/dummy form is static HTML wrapped in what will become a Text Editor widget, not a functional form.

### Elementor element mapping (use HTML comments; expand beyond this list as needed)
Wrap every structural block in a comment naming its target Elementor element:

`<!-- EL:SECTION -->`, `<!-- EL:INNER-SECTION -->`, `<!-- EL:COLUMN -->`,
`<!-- EL:WIDGET:Heading -->`, `<!-- EL:WIDGET:Text Editor -->`, `<!-- EL:WIDGET:Button -->`,
`<!-- EL:WIDGET:Icon Box -->`, `<!-- EL:WIDGET:Icon List -->`, `<!-- EL:WIDGET:Image -->`,
`<!-- EL:WIDGET:Image Box -->`, `<!-- EL:WIDGET:Star Rating -->`, `<!-- EL:WIDGET:Testimonial -->`,
`<!-- EL:WIDGET:Google Maps -->`, `<!-- EL:WIDGET:Accordion -->`, `<!-- EL:WIDGET:Tabs -->`,
`<!-- EL:WIDGET:Counter -->`, `<!-- EL:WIDGET:Progress Bar -->`, `<!-- EL:WIDGET:Video -->`,
`<!-- EL:WIDGET:Divider -->`, `<!-- EL:WIDGET:Social Icons -->`, `<!-- EL:WIDGET:Nav Menu -->`

If a section doesn't map cleanly to any listed widget, choose the nearest native widget and add `<!-- EL:NOTE: reason for choice -->` immediately after so the manual conversion step knows it was a judgment call.

### CSS classes
Give every element needing custom styling a unique, descriptive class name following the naming convention chosen in Section 0 (e.g. BEM) — not just Tailwind utilities. These named classes are what `custom.css` targets.

### Photography
Use placeholder photography per the sourcing method chosen in Section 0. Every image gets an HTML comment noting the photographer/source and a direct link to the original listing, e.g.:
`<!-- Photo by [Name] on Unsplash: https://unsplash.com/photos/xxxx -->`

### custom.css
All non-Tailwind-expressible styling — decorative shapes, floating cards, custom animations, parallax, hover/transition states, glassmorphism — goes here, meant to be pasted into WordPress Customizer → Additional CSS.

### script.js (vanilla JS only, no framework dependencies)
- Mobile menu toggle
- Smooth-scroll anchor navigation
- Scrollspy for nav highlighting
- Any simple demo interactivity implied by the design (accordions, tabs, counters, etc.)

### Responsiveness & accessibility
Fully responsive across mobile/tablet/desktop breakpoints. Meet the accessibility target from Section 0, minimum:
- Visible focus states on all interactive elements
- Descriptive alt text on every image
- Skip-to-content link
- ARIA labels on icon-only buttons/nav toggles
- Sufficient color contrast for body text and CTAs (4.5:1 minimum for normal text)
- Mobile menu fully operable by keyboard

### Premium feel — concrete specs (not vibes)
Interpret "premium" as these specific, testable behaviors:
- **Parallax**: subtle only — hero background/foreground moving at a ~0.3–0.5x scroll-speed differential, not full-page parallax scenes
- **Scroll reveals**: elements fade/slide in (translateY 20–30px, opacity 0→1) once per element as they enter viewport, staggered ~80–120ms between siblings in a group
- **Hover micro-interactions**: buttons/cards scale 1.02–1.05 or lift with shadow change on hover, 150–250ms ease-out transition — no jarring or slow (>400ms) transitions
- **Glassmorphism**: applied selectively (e.g. sticky header, floating cards over hero image) using backdrop-blur + semi-transparent background, not applied globally
- **Performance guardrail**: lazy-load all below-the-fold images (`loading="lazy"`), keep total custom.css animation rules performant (prefer `transform`/`opacity`, avoid animating layout properties like `width`/`top`)

---

## 3. Output

Three separate files, delivered as a downloadable zip:
- `index.html` (or multiple HTML files if multi-page was selected in Section 0)
- `custom.css`
- `script.js`
- `the design inspiration image Provided`

Before the code, include the design system spec from Section 1 as a short written summary so it can be reviewed independently of the code output.
