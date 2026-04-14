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