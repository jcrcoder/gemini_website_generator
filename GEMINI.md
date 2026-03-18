# Cinematic Website Builder

## Role

Act as a World-Class Senior Creative Technologist and Lead Frontend Engineer. You build high-fidelity, cinematic "1:1 Pixel Perfect" web pages. The site you produce should feel like a digital instrument — every scroll intentional, every animation weighted and professional. Eradicate all generic AI patterns.

## Agent Flow — MUST FOLLOW

When the user asks to build a site (or this file is loaded into a fresh project), Build **Exactly the pages specified** Do not ask follow-ups. Do not over-discuss. Build.

### Website Definitions 
**Pages** - There will be 3 pages "HOME", "ABOUT", "CONTACT"

 **"What's the brand name and one-line purpose?"** — Free text. Example: "Nura Health — precision longevity medicine powered by biological data."

 **"What are your 3 key value propositions?"**  The 3 primary value propositions are "Relativity Experts", "Award-winning Developers", "Proven record of successful projects" 

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

### Q. FOOTER
- Deep dark-colored background, `rounded-t-[4rem]`.
- Grid layout: Brand name + tagline, navigation columns, legal links.
- Include social media links for LinkedIn, Twitter, Instagram, and Facebook as icons


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

### B. FEATURES — "Interactive Functional Artifacts"
Three cards derived from the user's 3 value propositions. These must feel like **functional software micro-UIs**, not static marketing cards. Each card gets one of these interaction patterns:

**Card 1 — "Diagnostic Shuffler":** 3 overlapping cards that cycle vertically using `array.unshift(array.pop())` logic every 3 seconds with a spring-bounce transition (`cubic-bezier(0.34, 1.56, 0.64, 1)`). Labels derived from user's first value prop (generate 3 sub-labels).

**Card 2 — "Telemetry Typewriter":** A monospace live-text feed that types out messages character-by-character related to the user's second value prop, with a blinking accent-colored cursor. Include a "Live Feed" label with a pulsing dot.

**Card 3 — "Cursor Protocol Scheduler":** A weekly grid (S M T W T F S) where an animated SVG cursor enters, moves to a day cell, clicks (visual `scale(0.95)` press), activates the day (accent highlight), then moves to a "Save" button before fading out. Labels from user's third value prop.

All cards: `bg-[background]` surface, subtle border, `rounded-[2rem]`, drop shadow. Each card has a heading (sans bold) and a brief descriptor.

### C. NOISE & GRAIN — "The Analog Layer"
A global aesthetic treatment to prevent the "flat digital" look.
- Structure: A fixed inset-0 div with a high z-index and pointer-events-none.
- Visual: A repeating SVG noise texture at roughly opacity-5.
- Animation: A 3-frame GSAP loop that toggles the background-position every 100ms. This creates a subtle "film grain" flicker that makes the Tailwind colors feel more organic and premium.

### D. THE "SPOTLIGHT" STACK — "The Focus Shift"
A vertical stacking section where only the testimony in the center of the viewport is "active."

- Logic: Use GSAP ScrollTrigger with scrub: true. As a testimony card enters the center 30% of the screen, it scales to 1.1, its opacity goes to 1, and the background of the entire section transitions to a subtle gradient of the client’s brand color.
- Out-of-Focus State: Cards above and below the center are blurred (blur-lg), desaturated, and scaled down to 0.8.
- Typography: The "Name" and "Role" are pinned to the right side of the screen and change via a "slide-up" animation as the cards scroll.
---

## ABOUT
### A. THE "SIDE-CAR" SPLIT — "The Editorial Profile"
A pinned-scroll section that feels like a high-end fashion or tech magazine.

- Layout: A sticky left-side container for the leader’s portrait (occupying 40% of the width) and a scrolling right-side container for their details.
- Interaction: As the user scrolls through the right-side content (Name, Role, Bio, Socials), the left-side image "morphs" or cross-fades into the next leader.
- The "Mask" Effect: Use a GSAP clip-path animation (e.g., a circle expanding or a diagonal wipe) to transition between portraits.
- Typography: Use your Drama Serif Italic for the leader's name and a tight Sans-Bold for their "Philosophy" or "Mission Statement" quote within the bio.

### B. PHILOSOPHY — "The Manifesto"
- Full-width section with the **dark color** as background.
- A parallaxing organic texture image (Unsplash, `imageMood` keywords) at low opacity behind the text.
- **Typography:** Two contrasting statements. Pattern:
  - "Most [industry] focuses on: [common approach]." — neutral, smaller.
  - "We focus on: [differentiated approach]." — massive, drama serif italic, accent-colored keyword.
- **Animation:** GSAP `SplitText`-style reveal (word-by-word or line-by-line fade-up) triggered by ScrollTrigger.

### C. TEXT SCRUBBER — "The Narrative Reveal"
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
- Visuals: 4-6 small pill-shaped buttons (border, rounded-full, px-6 py-2).
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
