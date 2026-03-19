
# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.


# gemini_website_generator
This is a GEMINI.md file that is used to generate a website using AI. There are several components that the site can create. I will make several variants of the site md file to include different components. 

This is based on my Notion doc 
https://www.notion.so/Gemini-3-1-Pro-Antigravity-Site-Design-e56ea1eb76514375956974d60c95cf1c?source=copy_link

# Phases
This variant will be the base component that the original md file came with.

1. Original
2. Select the components that I want to include in my website
3. Experiment with creating multiple pages
4. Experiment with creating content based on another md file.
5. Adapt the md to actually create my website based on another MD file with the content

# Final goal
Create a website that is based on the content of another md file. The website should be created using the components that I have selected.

- Prompt the user to select the components that they want to include in their website. 
- Prompt the user to select the aesthetic direction that they want to use. 
- Prompt the user to select the content that they want to use. 

# Experiments

## Experiment 1 - Build site from scratch :
Answeres to prompt: "1) Business Gen Pro 2) C Butalist Signal 3) A-Z of creating a business , Marketing and social media, Legal incorporation 4) Sign up Now"

- Time: Start 5:10 PM End: 5:30 PM
    - Run npm install of several compoenents the first time through
    - 

## Experiment 2
1) Business Gen Pro 2) D Vapor Clinic 3) A-Z of creating a business , Marketing and social media, Legal incorporation 4) Sign up Now"

- Time: Start 8:00 PM End: 8:15 PM
    - Created implementation plan to approve
    - Asked permision to create and change each file 

- The social media icons are not showing up. 
- The Message Log isn't great for showing testimonials. 
- Still using older version of tailwind

## Experiment 3
1) Business Gen Pro 2) B Midnight Luxe 3) A-Z of creating a business , Marketing and social media, Legal incorporation 4) Sign up Now"

- Deleted all previous site files
- Changed to Tailwind 4
- Added Leadership team section
- Gave it more laxed approval config


- Time: Start 1:17 PM End: 1:28 PM
    - Ran with less prompots
    - First run, didn't show any content. Migrating to Tailwind 4 seems to have broken the engine
    - Prompted to fix the code. It fixed the HorizontalCase component in React
    - Tailwind 4 seems to be the issue, most components are not showing up like they did before.
    - I prompted to review some of the non-functioning components. .

## V1 Multipage
Made some basic components for 3 pages. No longer asking the user for input about the site. 

- Start 2:48 PM End: 2:55 PM
- All 3 pages were created. Menu bar and footer were created and work on all pages
    - Nav bar is difficult to see on light backgrounds

**To Update**
- FEATURES 
    -"Interactive Functional Artifacts" is not a good fit for this site. 
    - THE "SPOTLIGHT" STACK — "The Focus Shift" is hard to focus on it's always blurry, need a different testimonial section.
    - 

## Multipage V2
- Added a new testimonial section called "THE "KINETIC DRAG" CAROUSEL — "The Tactile Deck"
- Added a new section called "THE "CONVERSATIONAL" INTAKE — "The Human Protocol"
- Updated some of the content sections of home, added another leads section in about.
NOTE: Good to start a new conversation for each new website. Otherwise it assumes the objects you just cleaned up are still in the project.
- need to give access to .gitignore. Seems tailwind reads the file and skips creating style if I leave ignore all
- THE "SIDE-CAR" SPLIT — "The Editorial Profile" is the way to go for Leadership profiles
-  THE THE "KINETIC DRAG" CAROUSEL — "The Tactile Deck" — "The Interactive Grid" is good for awards
- THE "GRAVITY" LOGO CLOUD — "The Floating Ecosystem" is not great for client list, use the THE "KINETIC CARPET" — "The Interactive Grid"

## Multipage V3
- Added 6 pages and they were created successfully
- Footer doesn't look right with dark items next to them
- The leaders section is not full screen as it was before, also not changing images as I scroll, it only did it the first time.
- 
Keep:
- Tailwind.config.jr
- vite.config.js
- package.json
- node_modules

Full build - 6 pages took from 7:40 - 