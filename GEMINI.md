# Cinematic Website Builder

## Role

Act as a World-Class Senior Creative Technologist and Lead Frontend Engineer. You build high-fidelity, cinematic "1:1 Pixel Perfect" web pages. The site you produce should feel like a digital instrument — every scroll intentional, every animation weighted and professional. Eradicate all generic AI patterns.

## Agent Flow — MUST FOLLOW

When the user asks to build a site (or this file is loaded into a fresh project), Build **Exactly the pages specified** Do not ask follow-ups. Do not over-discuss. Build.

### Website Definitions 
**Pages** - There will be 3 pages "HOME", "ABOUT", "CONTACT"

 **"What's the brand name and one-line purpose?"** — Brand Name and purpose: "NSerio - Build software with Relativity experts."

 **"What are your 3 key value propositions?"**  The 3 primary value propositions are "Relativity Experts", "Award-winning Developers", "Modern, Fast, & Accurate AI-Enabled Software Development" 

**"What should visitors do?"** — The primary CTA is "Contact Juan"

---

## Aesthetic Preset

Defines: `palette`, `typography`, `identity` (the overall feel), and `imageMood` (Unsplash search keywords for hero/texture images).

### "Organic Tech" (Clinical Boutique)
- **Identity:** A bridge between a biological research lab and an avant-garde luxury magazine.
- **Palette:** Moss `#2E4036` (Primary), Clay `#CC5833` (Accent), Cream `#F2F0E9` (Background), Charcoal `#1A1A1A` (Text/Dark)
- **Typography:** Headings: "Plus Jakarta Sans" + "Outfit" (tight tracking). Drama: "Cormorant Garamond" Italic. Data: `"IBM Plex Mono"`.
- **Image Mood:** dark forest, organic textures, moss, ferns, laboratory glassware.
- **Hero line pattern:** "[Concept noun] is the" (Bold Sans) / "[Power word]." (Massive Serif Italic)

---

## Fixed Design System (NEVER CHANGE)

These rules apply to ALL presets. They are what make the output premium.

### Visual Texture
- Implement a global CSS noise overlay using an inline SVG `<feTurbulence>` filter at **0.05 opacity** to eliminate flat digital gradients.
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
- Contains: Logo (brand name as text), 3-4 nav links, CTA button (accent color).
- CTA Links to the CONTACT page
- Make sure it is visible on all backgrounds

### B. FOOTER
- Deep dark-colored background, `rounded-t-[4rem]`.
- Grid layout: Brand name + tagline, navigation columns, legal links.
- Include social media links for LinkedIn, Instagram, and YouTube as icons


## HOME page
1. Generate hero copy using the brand name + purpose + preset's hero line pattern.
2. Map the 3 value props to the 3 Feature card patterns (Shuffler, Typewriter, Scheduler).
3. Generate Philosophy section contrast statements from the brand purpose.
4. Generate Protocol steps from the brand's process/methodology.

### A. HERO SECTION — "The Opening Shot"
- `100dvh` height. Full-bleed background image (sourced from Unsplash matching preset's `imageMood`) with a heavy **primary-to-black gradient overlay** (`bg-gradient-to-t`).
- **Layout:** Content pushed to the **bottom-left third** using flex + padding.
- **Typography:** Large scale contrast following the preset's hero line pattern. First part in bold sans heading font. Second part in massive serif italic drama font (3-5x size difference).
- **Animation:** GSAP staggered `fade-up` (y: 40 → 0, opacity: 0 → 1) for all text parts and CTA.
- CTA button below the headline, using the accent color.


### B. PROTOCOL — "Sticky Stacking Archive"
3 full-screen cards that stack on scroll.Three cards derived from the user's 3 value propositions. 
- **Stacking Interaction:** Using GSAP ScrollTrigger with `pin: true`. As a new card scrolls into view, the card underneath scales to `0.9`, blurs to `20px`, and fades to `0.5`.
- **Each card gets a unique canvas/SVG animation:**
  1. A slowly rotating geometric motif (double-helix, concentric circles, or gear teeth).
  2. A scanning horizontal laser-line moving across a grid of dots/cells.
  3. A pulsing waveform (EKG-style SVG path animation using `stroke-dashoffset`).
- Card content: Step number (monospace), title (heading font), 2-line description. Derive from user's brand purpose.

### C. THE "SPOTLIGHT" STACK — "The Focus Shift"
A vertical stacking section where only the testimony in the center of the viewport is "active."

- Logic: Use GSAP ScrollTrigger with scrub: true. As a testimony card enters the center 30% of the screen, it scales to 1.1, its opacity goes to 1, and the background of the entire section transitions to a subtle gradient of the client’s brand color.
- Out-of-Focus State: Cards above and below the center are blurred (blur-lg), desaturated, and scaled down to 0.8.
- Typography: The "Name" and "Role" are pinned to the right side of the screen and change via a "slide-up" animation as the cards scroll.

### D. NOISE & GRAIN — "The Analog Layer"
A global aesthetic treatment to prevent the "flat digital" look.
- Structure: A fixed inset-0 div with a high z-index and pointer-events-none.
- Visual: A repeating SVG noise texture at roughly opacity-5.
- Animation: A 3-frame GSAP loop that toggles the background-position every 100ms. This creates a subtle "film grain" flicker that makes the Tailwind colors feel more organic and premium.

### E. THE "KINETIC CARPET" — "The Interactive Grid"
A static grid that feels alive through mouse-tracking and micro-animations.

- Layout: A clean 4x4 or 5x5 grid with gap-px (1px borders) to create a "technical blueprint" look. 
- 4 black and white logos of our customers
- Interaction Logic: The "Flashlight" Effect. The entire grid is dimmed to opacity-20. As the user moves their cursor, a GSAP-driven radial mask follows the mouse, "lighting up" the logos within a 200px radius to opacity-100.
- Animation: When a logo enters the "light," it performs a subtle scale(1.05) and a 3D rotationY (5-10 degrees) to give the grid physical depth.
- Styling: Use your bg-secondary/5 for the grid cells to maintain the "Glassmorphism" theme.

### F. THE "GRAVITY" LOGO CLOUD — "The Floating Ecosystem"
A more experimental, "Art-Gallery" approach for a boutique feel.

- Visuals: Logos are not in a grid; they are "floating" at different depths (z-index) and scales.
- 4 black and white logos of our customers
- Logic: Use a subtle GSAP yoyo animation on each logo (randomized duration between 3-6s) to create a "buoyant" floating effect.
- Parallax: Each logo has a different data-speed attribute. As the user scrolls, the logos move at different rates, creating a deep 3D field effect.
- Styling: High-transparency logos that "overlap" slightly, emphasizing the backdrop-blur of your UI.
---

## ABOUT
### A. THE "SIDE-CAR" SPLIT — "The Editorial Profile"
A pinned-scroll section that feels like a high-end fashion or tech magazine.

- Layout: A sticky left-side container for the leader’s portrait (occupying 40% of the width) and a scrolling right-side container for their details.
- Interaction: As the user scrolls through the right-side content (Name, Role, Bio, Socials), the left-side image "morphs" or cross-fades into the next leader.
- The "Mask" Effect: Use a GSAP clip-path animation (e.g., a circle expanding or a diagonal wipe) to transition between portraits.
- Typography: Use your Drama Serif Italic for the leader's name and a tight Sans-Bold for their "Philosophy" or "Mission Statement" quote within the bio.

### B. THE "DOSSIER" HOVER — "The Identity Reveal"
A minimalist list that expands into a rich visual experience.

- Visuals: A vertical list of names in a massive, outlined heading font (text-transparent border-text).
- Interaction Logic: As the user hovers over a name, the outline fills with the primary color, and a high-quality "floating" image of the leader appears, following the cursor's movement (GSAP quickTo for x/y).
- The Bio Reveal: A short, 2-line bio fades in next to the floating image in a clean, monospace font.
- Animation: Use a "staggered slide-up" for the bio text (SplitText or word-by-word) triggered by the hover event.
- Styling: grayscale images that transition to sepia or full-color based on the site's imageMood.

### C. PHILOSOPHY — "The Manifesto"
- Full-width section with the **dark color** as background.
- A parallaxing organic texture image (Unsplash, `imageMood` keywords) at low opacity behind the text.
- **Typography:** Two contrasting statements. Pattern:
  - "Most [industry] focuses on: [common approach]." — neutral, smaller.
  - "We focus on: [differentiated approach]." — massive, drama serif italic, accent-colored keyword.
- **Animation:** GSAP `SplitText`-style reveal (word-by-word or line-by-line fade-up) triggered by ScrollTrigger.

### D. TEXT SCRUBBER — "The Narrative Reveal"
A high-impact storytelling section where text "lights up" as the user scrolls. [User Testimonials]
- Typography: Large, high-contrast sans-serif. Centered or justified.
- Animation Logic: Wrap every word in a <span> using split-type. Set initial state to opacity-10 (or a dimmed color).
- ScrollTrigger: Use scrub: true. As the user scrolls, the words transition to opacity-100 and the accent color.
- Visual Hook: A "horizontal scanner" line (1px accent color) that moves down the screen at the same pace as the text illumination.

---

## CONTACT
### A. THE "CONVERSATIONAL" INTAKE — "The Human Protocol"
- A minimalist, full-screen or high-bleed section that treats the contact form as a piece of clean editorial design.
- Layout: max-w-4xl centered. No visible input boxes or borders by default—only high-contrast typography and "underlined" interactive spans.
- Typography: The form is presented as a cohesive paragraph.
- Standard Text: text-muted or opacity-60 sans-serif.
- Interactive Fields: Massive, bold sans-serif (matching Hero Section "First Part") with a 1px bottom-border accent.
Interaction Logic:
- The "Active" State: When a field is focused, the underline expands (GSAP scaleX: 1.1) and changes to the accent color.
- Floating Label: As the user types, a small monospace label (e.g., "YOUR NAME") floats above the text in a subtle, staggered fade-up animation.
- Validation: If a field is missed, the underline "shakes" (GSAP x: [-5, 5, 0]) and turns a muted red.

### V. THE "SECTOR" SELECTOR — "The Choice Matrix"
- Instead of a standard dropdown menu for "Reason for Contacting," use a kinetic button grid.
- Visuals: "Custom Development", "CaseFlow", "Integration", "Other" - small pill-shaped buttons (border, rounded-full, px-6 py-2).
- Interaction: Toggle State. When clicked, the button fills with the primary color and the text "inverts" to the background color using a GSAP flip or scale transition.
- Logic: These selections update a hidden "Subject" field in the React 19 form state.

### W. THE "SEND" SEQUENCE — "The Transmission"
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
**IMPORTANT: Never modify core GEMINI.md or .gitignore unless explicitly asked.**
- always ask before modifying .gitignore
- always ask before modifying README.md
- always ask before modifying GEMINI.md 
