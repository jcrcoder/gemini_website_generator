# Home

## Hero Section
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



_Heading_ e-Discovery Development Experts

_Subheading_ NSerio is your one-stop shop for custom e-discovery applications and workflows.

## Services "The Manifesto"
- Full-width section with the **dark color** as background.
- A parallaxing organic texture image (Unsplash, `imageMood` keywords) at low opacity behind the text.
- **Typography:** Two contrasting statements. Pattern:
  - "Most [industry] focuses on: [common approach]." — neutral, smaller.
  - "We focus on: [differentiated approach]." — massive, drama serif italic, accent-colored keyword.
- **Animation:** GSAP `SplitText`-style reveal (word-by-word or line-by-line fade-up) triggered by ScrollTrigger.

We build best-in-class custom applications, integrations, and automated workflows on Relativity. Our engineering practice has fully embraced agentic AI — not as a shortcut, but as a force multiplier. We still design the architecture, own the software development lifecycle, and deliver with the rigor your mission-critical workflows demand. The result: faster delivery, smarter solutions, and outcomes legal teams can rely on.

## Our Services "Sticky Stacking Archive"
_heading_ Our Services
- 4  full-screen cards that stack on scroll. Cards derived from each of the services sub-sections ("Design & Consulting","Custom Development","Workflow Automations","Integrations")
- **Stacking Interaction:** Using GSAP ScrollTrigger with `pin: true`. As a new card scrolls into view, the card underneath scales to `0.9`, blurs to `20px`, and fades to `0.5`.
- **Each card gets a unique canvas/SVG animation:**
- The SVG animation should be large and animated and should be on the right side of the card.

- Card content: section title (heading font), 2-line description. canvas/SVG animation on the right side of the card.

### Design & Consulting
Share your biggest operational challenges and we'll craft solutions that work for you.
_animation_   
Animate a series of overlapping semi-transparent strokes that rotate and converge into a single, perfectly aligned geometric shape to represent the clarity and focus brought by strategic design and expert consulting.

### Custom Development
Bring your applications to life without the startup costs and get the most out of your e-discovery investments.
_animation_   
Trace a single, right-angled SVG path across a rigid grid that triggers the staggered "pop-in" of geometric module blocks to simulate the architectural assembly of a custom application.

### Integrations
We'll help you connect Relativity to your most important systems for a more seamless flow of data.
_animation_ 
Animate two monolithic blocks snapping together via parallel horizontal tracks that facilitate a rhythmic, bidirectional flow of geometric "data packets" to symbolize seamless synchronization.

### Workflow Automations
Save time and boost productivity by automating your most repetitive workflows.
_animation_  
Animate a chaotic scatter of geometric squares into a rigid linear sequence via a high-speed expo.inOut transition, followed by a single synchronized pulse that flows through the line to signify the transition from manual repetition to automated efficiency

## Awards & Recognitions

Our custom solutions have been recognized year over year for improving the lives of legal teams everywhere. 
- 2 column grid
- col 1: Center the awards logo @InnovAward_12.png
- col 2: counter box with "Over 14 years of experience"

## CaseFlow
_subheading_ One of our custom applications is now available out of the box. CaseFlow continuously monitors user activity and automatically transitions your cases to different lifecycle stages in Relativity.

Include CaseFlow Logo @caseflow_logo.png

_canvas/SVG animation_ Documents moving from a database on the left to a zip file on the right loop animation

A non-uniform CSS grid (grid-template-areas) that houses benefits like "featurettes."
- Grid Logic: 4 tiles of varying spans (e.g., col-span-2, row-span-2). Use gap-4.
- Interaction: Magnetic tiles. On mousemove, the tile's content (text or icon) translates slightly toward the cursor using GSAP, while a subtle radial-gradient glow follows the mouse position on the border.
- Styling: bg-secondary/5 with a 1px border that looks like etched glass.

_tiles_
1. Cloud to cloud data transfers
2. Set it and forget it monitoring
3. Automated workflows
4. Collaborative Notifications

[CTA: Learn more] — link to CaseFlow page

## Our Clients - "The Kinetic Matrix"
Trusted by the Biggest Names in e-Discovery and Legal Tech

A high-density grid that activates logos only as they enter the viewport, keeping the UI clean and focusing user attention.

- Use all of the files in the PageContent/client_logos. Use the company name as the alt text for each logo. e.g. if the file is "acme_corp.png" the alt text should be "Acme Corp".

- Rounded corners for all logos

- Structure: 12-column grid (grid grid-cols-4 md:grid-cols-8 lg:grid-cols-12 gap-px). Each logo sits in a precise square bg-secondary/5 cell.

- Animation Logic — GSAP ScrollTrigger + stagger:

- The initial state: Logos are opacity-0 and scale(0.8).

- The Reveal: When the grid (or individual rows) enter the viewport, logos fade-in and scale-to-1 in a tight, randomized stagger (stagger: { amount: 0.8, from: "random" }). This makes the logos appear to "crystallize" onto the grid.

- Interaction — The "Glow" Cursor: A global GSAP-driven radial-gradient glow (accent color) follows the cursor behind the grid, briefly illuminating the logos as the user moves their mouse.

- Styling: All logos are strict grayscale. Active/Hovered logo transitions to grayscale-0 with a subtle drop-shadow.

## Testimonials

What our clients say about us

_Testimonial Component_
A component that mimics a Slack or Discord DM thread, making the testimony feel like a real-time conversation.

- Logic: As the user scrolls into view, "messages" (testimonies) pop in one by one with a "typing..." indicator that lasts 0.5s to 1.0s at random to feel natural.
- Animation: A slight y: 20 bounce as each message appears.
- Visuals: Dark mode "bubbles" with the accent color used for the client's name. A "Recently Sent" pulsing green dot in the corner of the component.


_client testimonials_ 
### Phil Saunders - Relativity CEO

- NSerio has proven to be a trusted partner by consistently delivering customer-ready applications that extend our platform in meaningful, real-world ways. Their ability to translate complex needs into practical, scalable solutions makes them an invaluable part of our ecosystem.

### Jon Lavinder - Senior Director of Product Management

- After comparing options, I decided to go with NSerio to develop the app. Their level of talent and knowldege is extremely high and allowed us to smoothly build and deploy on-time and within budget.

### Jim Design - Foley & Lardner Director of Lit Support

- These guys are just amazing at what they do. They are always ready to support us.

### Adam Smith - Troutman Sanders & Pepper VP of Client Services

- The impact we've had on our clients and our business as a result of the applications we've built with NSerio is invaluable.
