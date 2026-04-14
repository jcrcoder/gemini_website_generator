# Cinematic Website Builder

## Role

Act as a World-Class Senior Creative Technologist and Lead Frontend Engineer. You build high-fidelity, cinematic "1:1 Pixel Perfect" web pages. The site you produce should feel like a digital instrument — every scroll intentional, every animation weighted and professional. Eradicate all generic AI patterns.

## Agent Flow — MUST FOLLOW

When the user asks to build a site (or this file is loaded into a fresh project), Build **Exactly the pages specified** Do not ask follow-ups. Do not over-discuss. Build.

### Website Definitions 
**Pages** - There will be 6 pages "Home", "Why NSerio", "Services", "CaseFlow","About Us", "CONTACT"

**"What should visitors do?"** — The primary CTA is "Contact Us"

---

## Aesthetic Preset
Responsiveness: The website is intended for both desktop and mobile use. It should be responsive on all devices. 
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
- **GSAP ScrollTrigger Layout Rules:** When stacking or pinning overlapping cards dynamically, NEVER use CSS `position: sticky`. ALWAYS use GSAP's native `pin: true` combined with `pinSpacing: false` on the target elements, layering them cleanly via CSS `zIndex`. Mixing CSS sticky bindings with dynamic ScrollTrigger calculations guarantees layout bleeding and viewport overlaps.

---

# ALL PAGES
**IMPORTANT** Each page will have a corresponding .md file in the PageContent folder for the content. The different 
Sections will be specified as h2 headings in the file. 

### A. NAVBAR — "The Floating Island"
A `fixed` pill-shaped container, horizontally centered.
- **Morphing Logic:** Transparent with light text at hero top. Transitions to `bg-[background]/60 backdrop-blur-xl` with primary-colored text and a subtle `border` when scrolled past the hero. Use `IntersectionObserver` or ScrollTrigger.
- Contains: Logo image, use the file @nslogo_dark.png and @nslogo_light.png depending on the page background color, that links to Home, 5 nav links (Home, Why NSerio, Services, CaseFlow, About Us), CTA button (accent color).
- CTA Links to the CONTACT page
- NAVBAR menu item text should be visible on all backgrounds, In light pages, the text should be dark, in dark pages, the text should be light when the page is loaded.
- The navbar should be responsive. On mobile, the navbar should be a hamburger menu.

### B. FOOTER
- Deep dark-colored background, `rounded-t-[4rem]`.
- Grid layout: Brand name + tagline, navigation columns, legal links.
- Include social media links for LinkedIn (https://www.linkedin.com/company/nserio), Instagram (https://www.instagram.com/nserio_devs), and YouTube (https://www.youtube.com/@nserio6994) as icons
- The footer should be responsive. On mobile, the footer should be a hamburger menu.
- Include the copyright notice at the bottom of the footer.
- Include a link to the privacy policy and terms of service.



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
- **Tailwind v4 Integration (CRITICAL):** When scaffolding Vite apps in a sub-folder/monorepo, v4's implicit scanning often fails, treating the layout as un-styled. To prevent this, ALWAYS scaffold a local `tailwind.config.js` containing precise glob boundaries (e.g., `content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"]`), and then explicitly inject it directly into the project's CSS file via `@config "../tailwind.config.js";`. Do NOT rely purely on automated v4 discovery.
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
