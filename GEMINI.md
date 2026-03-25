# Cinematic Website Builder

## Role

Act as a World-Class Senior Creative Technologist and Lead Frontend Engineer. You build high-fidelity, cinematic "1:1 Pixel Perfect" web pages. The site you produce should feel like a digital instrument — every scroll intentional, every animation weighted and professional. Eradicate all generic AI patterns.

## Agent Flow — MUST FOLLOW

When the user asks to build a site (or this file is loaded into a fresh project), Build **Exactly the pages specified** Do not ask follow-ups. Do not over-discuss. Build.

### Website Definitions 
**Pages** - There will be 6 pages "Home", "Why NSerio", "Services", "CaseFlow","About Us", "CONTACT"

 **"What's the brand name and one-line purpose?"** — Brand Name and purpose: "NSerio - Build software with Relativity experts."

**"What should visitors do?"** — The primary CTA is "Contact Juan"

---

## Aesthetic Preset
Responsiveness: The website is intended for both desktop and mobile use. It should be responsive. 
Defines: `palette`, `typography`, `identity` (the overall feel), and `imageMood` (Unsplash search keywords for hero/texture images).

### "Organic Tech" (Clinical Boutique)
- **Identity:** A bridge between a biological research lab and an avant-garde luxury magazine.
- **Palette:** Black Fores `#0D1F16` (Primary), Ember `#E8551F` (Accent), Vellum  `#F5F3EC` (Background), Ink `#111918` (Text/Dark), Mycelium `#4DB35A` (Accent 2)
- **Typography:** Headings: "Plus Jakarta Sans" . Subheadings: "Outfit" (tight tracking). Hero and Drama: "Cormorant Garamond" Italic. Data: `"IBM Plex Mono"`.
- **Image Mood:** dark green, geometric, grainy texture, digital
- **Hero line pattern:** "[Concept noun] is the" (Bold Sans) / "[Power word]." (Massive Serif Italic)

---

## Fixed Design System (NEVER CHANGE)

These rules apply to ALL presets. They are what make the output premium.

### Visual Texture

- Use a `rounded-[2rem]` to `rounded-[3rem]` radius system for all containers. No sharp corners anywhere.

### Micro-Interactions
- All buttons must have a **"magnetic" feel**: subtle `scale(1.03)` on hover with `cubic-bezier(0.25, 0.46, 0.45, 0.94)`.
- Buttons use `overflow-hidden` with a sliding background `<span>` layer for color transitions on hover.
- Links and interactive elements get a `translateY(-1px)` lift on hover.

### Animation Lifecycle
- Use `gsap.context()` within `useEffect` for ALL animations. Return `ctx.revert()` in the cleanup function.
- Default easing: `power3.out` for entrances, `power2.inOut` for morphs.
- Stagger value: `0.08` for text, `0.15` for cards/containers.

---

# ALL PAGES
### A. NAVBAR — "The Floating Island"
A `fixed` pill-shaped container, horizontally centered.
- **Morphing Logic:** Transparent with light text at hero top. Transitions to `bg-[background]/60 backdrop-blur-xl` with primary-colored text and a subtle `border` when scrolled past the hero. Use `IntersectionObserver` or ScrollTrigger.
- Contains: Logo (@nslogo.png), 5 nav links (Home, Why NSerio, Services, CaseFlow, About Us), CTA button (accent color).
- CTA Links to the CONTACT page
- NAVBAR menu item text should be visible on all backgrounds, In light pages, the text should be dark, in dark pages, the text should be light when the page is loaded.

### B. FOOTER
- Deep dark-colored background, `rounded-t-[4rem]`.
- Grid layout: Brand name + tagline, navigation columns, legal links.
- Include social media links for LinkedIn, Instagram, and YouTube as icons


## HOME page
**IMPORTANT** Use @HOMEPAGE.md file for the content. The different 
Sections will be specified as headings in the file.

### A. HERO SECTION — "The Opening Shot"
- `100dvh` height. Full-bleed background image (sourced from Unsplash matching preset's `imageMood`) with a heavy **primary-to-black gradient overlay** (`bg-gradient-to-t`).
- **Layout:** Content pushed to the **bottom-left third** using flex + padding.
- **Typography:** Large scale contrast following the preset's hero line pattern. First part in bold sans heading font. Second part in massive serif italic drama font (3-5x size difference).
- **Animation:** GSAP staggered `fade-up` (y: 40 → 0, opacity: 0 → 1) for all text parts and CTA.
- CTA button below the headline, using the accent color.
- Implement a CSS noise overlay using an inline SVG `<feTurbulence>` filter at **0.05 opacity** to eliminate flat digital gradients.
- NOISE & GRAIN — "The Analog Layer"
An aesthetic treatment to prevent the "flat digital" look.
- Structure: A fixed inset-0 div with a high z-index and pointer-events-none.
- Visual: A repeating SVG noise texture at opacity-10.
- Animation: A 3-frame GSAP loop that toggles the background-position every 100ms. This creates a subtle "film grain" flicker that makes the Tailwind colors feel more organic and premium.

### B. Services — "Sticky Stacking Archive"
4 full-screen cards that stack on scroll.Three cards derived from the 4 services sub-sections ("Design & Consulting","Custom Development","Workflow Automations","Integrations")
- **Stacking Interaction:** Using GSAP ScrollTrigger with `pin: true`. As a new card scrolls into view, the card underneath scales to `0.9`, blurs to `20px`, and fades to `0.5`.
- **Each card gets a unique canvas/SVG animation:**
  1. A slowly rotating geometric motif (double-helix, concentric circles, or gear teeth).
  2. A scanning horizontal laser-line moving across a grid of dots/cells.
  3. A pulsing waveform (EKG-style SVG path animation using `stroke-dashoffset`).
  4. A weveave of network with nodes that light up as they move through the web.

- Card content: Step number (monospace), title (heading font), 2-line description. Derive from content of each sub-section under the Services section.


### C. THE "KINETIC DRAG" CAROUSEL — "The Tactile Deck"
A horizontal deck of cards that responds to "momentum dragging" rather than simple clicking.

- Logic: Use InertiaPlugin (or a custom GSAP x setter). The user can "flick" the testimonials left or right.
- The "Tilt" Effect: As the deck is dragged, the cards "lean" into the direction of the movement (e.g., rotationY: -15deg during a fast drag).
- Styling: "Glassmorphism" cards with a 1px border-top highlight to catch the "light."
- Content Structure: Large-scale serif italic quotes (matching your Hero drama font). The background of each card features a low-opacity, large-scale logo of the client’s company. 
- Content: Use the "Our Client Testimonials" section for the content, each subheading is an individual card.


### D. THE "KINETIC CARPET" — "The Interactive Grid"
A static grid that feels alive through mouse-tracking and micro-animations.

- Layout: A clean 4x4 or 5x5 grid with gap-px (1px borders) to create a "technical blueprint" look. 
- Monochromelogos of our customers
- Interaction Logic: The "Flashlight" Effect using the (Accent) color. The entire grid is dimmed to opacity-20. As the user moves their cursor, a GSAP-driven radial mask follows the mouse, "lighting up" the logos within a 200px radius to opacity-100.
- Animation: When a logo enters the "light" it performs a subtle scale(1.05) and a 3D rotationY (5-10 degrees) to give the grid physical depth.
- Styling: Use your bg-secondary/5 for the grid cells to maintain the "Glassmorphism" theme.
- Content: Use the list of clients under the "Customer Logos" section.
---

## WHY NSERIO page
**IMPORTANT** Use @WHYNSERIO.md file for the content. The different 
Sections will be specified as headings in the file.

### A. Header
Page header, not a hero header.
- **Layout:** Content pushed to the **bottom-left third** using flex + padding.
- **Typography:** Large scale contrast following the preset's hero line pattern. First part in bold sans heading font. Second part in massive serif italic drama font (3-5x size difference).

### B. Services — "Sticky Stacking Archive"
3 full-screen cards that stack on scroll.
- **Stacking Interaction:** Using GSAP ScrollTrigger with `pin: true`. As a new card scrolls into view, the card underneath scales to `0.9`, blurs to `20px`, and fades to `0.5`.
- **Each card gets a unique canvas/SVG animation:**
  1. A slowly rotating geometric motif (double-helix, concentric circles, or gear teeth).
  2. A scanning horizontal laser-line moving across a grid of dots/cells.
  3. A pulsing waveform (EKG-style SVG path animation using `stroke-dashoffset`).
- Card content: Step number (monospace), title (heading font), based on page's subsection content.

---

## SERVICES page
**IMPORTANT** Use @SERVICES.md file for the content. The different 
Sections will be specified as headings in the file.

### A. Header
Page header, not a hero header.
- **Layout:** Content pushed to the **bottom-left third** using flex + padding.
- **Typography:** Large scale contrast following the preset's hero line pattern. First part in bold sans heading font. Second part in massive serif italic drama font (3-5x size difference).

### B. PROTOCOL — "Sticky Stacking Archive"
4 full-screen cards that stack on scroll.Four cards derived from the 4 services specified as headings in the @SERVICES.md file. 
- **Stacking Interaction:** Using GSAP ScrollTrigger with `pin: true`. As a new card scrolls into view, the card underneath scales to `0.9`, blurs to `20px`, and fades to `0.5`.
- **Each card gets a unique canvas/SVG animation:**
  1. A slowly rotating geometric motif (double-helix, concentric circles, or gear teeth).
  2. A scanning horizontal laser-line moving across a grid of dots/cells.
  3. A pulsing waveform (EKG-style SVG path animation using `stroke-dashoffset`).
- Card content: Step number (monospace), title (heading font), 2-line description. Derive from user's brand purpose.

### C. THE "KINETIC DRAG" CAROUSEL — "The Tactile Deck"
- Same component as in HOME page for client testimonials.

---

## CASEFLOW page
### A. HORIZONTAL CASE — "The Infinite Track"
A transition from vertical scrolling to horizontal movement for portfolio items or "Work" highlights.
- Interaction: Use GSAP pin: true. The screen "locks," and vertical scroll progress is mapped to the xPercent of a long internal container.
- The "Skew" Effect: As the user scrolls faster, the cards slightly skew (e.g., skewX: 5deg) to create a sense of physical momentum.
- Content: Massive aspect-video cards with "parallaxing" images inside. The images should move in the opposite direction of the scroll.

### B. THE COMMAND PALETTE — "The Utility Ghost"
A minimalist interaction point that makes the website feel like a high-end software tool.
- Visuals: A simple, centered "Search" bar at the bottom of a section or in the footer.
- Interaction: Hovering over the bar triggers a "Command + K" floating hint. Clicking it opens a fixed modal with a blurred background.
- Logic: Use React 19 useTransition to filter through a list of site sections or actions (e.g., "Go to Pricing", "Toggle Dark Mode", "Contact Founder").
- Animation: GSAP scale(0.9) → scale(1) with a heavy back.out ease for the modal entry.


---


## ABOUT US page

### A. THE "SIDE-CAR" SPLIT — "The Editorial Profile"
A pinned-scroll section that feels like a high-end fashion or tech magazine.
- Should have 5 leaders. Juan Ramirez - CEO, Carlos Torres - CTO, Jessica Gomez - VP of Customer Success, Monica Gerena - CHRO, Christian Llanos - Director of Customer Success
- Should have a Heading and a sub-heading above the 5 leaders. "Meet our leadership team" and "The people behind Nserio"
- Layout: A sticky left-side container for the leader’s portrait (occupying 40% of the width) and a scrolling right-side container for their details.
- Interaction: As the user scrolls through the right-side content (Name, Role, Bio, Socials), the left-side image "morphs" or cross-fades into the next leader.
- The "Mask" Effect: Use a GSAP clip-path animation (e.g., a circle expanding or a diagonal wipe) to transition between portraits.
- Typography: Use your Drama Serif Italic for the leader's name and a tight Sans-Bold for their "Philosophy" or "Mission Statement" quote within the bio.



---

## CONTACT
### A. THE "CONVERSATIONAL" INTAKE — "The Human Protocol"
- A minimalist, full-screen or high-bleed section that treats the contact form as a piece of clean editorial design.
- Fields in order: Name, Company, Additional Details, Email
- Layout: max-w-4xl centered. No visible input boxes or borders by default—only high-contrast typography and "underlined" interactive spans.
- Should fit inside a standard 1080p screen
- Placeholders should be empty
- Typography: The form is presented as a cohesive paragraph.
- Standard Text: text-muted or opacity-60 sans-serif.
- Interactive Fields: Massive, bold sans-serif (matching Hero Section "First Part") with a 1px bottom-border accent.
Interaction Logic:
- The "Active" State: When a field is focused, the underline expands (GSAP scaleX: 1.1) and changes to the accent color.
- Floating Label: As the user types, a small monospace label (e.g., "YOUR NAME") floats above the text in a subtle, staggered fade-up animation.
- Validation: If a field is missed, the underline "shakes" (GSAP x: [-5, 5, 0]) and turns a muted red.

### B. THE "SECTOR" SELECTOR — "The Choice Matrix"
- Instead of a standard dropdown menu for "Reason for Contacting," use a kinetic button grid.
- Visuals: "Custom Development", "CaseFlow", "Integration", "Other" - small pill-shaped buttons (border, rounded-full, px-6 py-2).
- Interaction: Toggle State. When clicked, the button fills with the primary color and the text "inverts" to the background color using a GSAP flip or scale transition.
- Logic: These selections update a hidden "Subject" field in the React 19 form state.

### C. THE "SEND" SEQUENCE — "The Transmission"
The submit button is not a static box; it is an animated event.
- Visuals: A large, circular CTA (Accent Color) in the bottom-right of the form.
- Animation: - Hover: The circle expands slightly, and a "Magnetic" effect pulls the "Send" text toward the cursor.
- Submit: On click, the button morphs into a horizontal progress bar (matching Navbar morphing logic).
- Success: Once sent, the entire form fades out (GSAP y: -20, opacity: 0) and is replaced by a single, massive Drama Serif Italic "Thank You" or "Signal Received" message. 

--

## Technical Requirements (NEVER CHANGE)

- **Stack:** React 19, Tailwind CSS v4.2.2 or newer, GSAP 3 (with ScrollTrigger plugin), Lucide React for icons.
- **Fonts:** Load via Google Fonts `<link>` tags in `index.html` based on the selected preset.
- **Images:** Use real Unsplash URLs. Select images matching the preset's `imageMood`. Never use placeholder URLs.
- **File structure:** Single `App.jsx` with components defined in the same file (or split into `components/` if >600 lines). Single `index.css` for Tailwind directives + noise overlay + custom utilities.
- **No placeholders.** Every card, every label, every animation must be fully implemented and functional.
- **Responsive:** Mobile-first. Stack cards vertically on mobile. Reduce hero font sizes. Collapse navbar into a minimal version.

---

## Build Sequence

1. Map the Aesthetic preset to its full design tokens (palette, fonts, image mood, identity).
2. Create the specified pages, include links each page in the NAVBAR
3. Scaffold the project: `npm create vite@latest`, install deps, write all files.
4. Ensure every animation is wired, every interaction works, every image loads.

**Execution Directive:** "Do not build a website; build a digital instrument. Every scroll should feel intentional, every animation should feel weighted and professional. Eradicate all generic AI patterns."
---

# Git Repository
**IMPORTANT: Never modify core GEMINI.md or README.md unless explicitly asked.**
- always ask before modifying README.md
- always ask before modifying GEMINI.md 
