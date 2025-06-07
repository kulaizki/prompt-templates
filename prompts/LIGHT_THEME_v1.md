# Prompt Template: Modern SaaS Landing Page (Light Theme)

## 1. Project Overview

**Objective:** Build a responsive, modern landing page for a SaaS product using a **light and airy theme**.
**Core Principles:**
- **Technology Stack:** SvelteKit, Svelte 5, Tailwind CSS, `svelte-inview`.
- **Design:** Clean, spacious, professional, and fully mobile-responsive aesthetic with a light base background.
- **Layout:** Immersive, full-screen sections (`min-h-screen`) for a step-by-step scrolling experience.
- **Theme:** A consistent color scheme using `white`, light grays, and a dynamic `[PrimaryColor]` (e.g., sky, green, indigo).
- **Animation:** Subtle on-scroll fades for all sections (triggered using `svelte-inview`) and an animated separator.

## 2. Global Styles & Configuration
- **Tailwind:** Configure `tailwind.config.js` to include the dynamic `[PrimaryColor]` palette.
- **Backgrounds:** Alternate section backgrounds between `bg-white` and a very light tint of the primary color (e.g., `bg-[PrimaryColor]-50`).

## 3. Page Structure & Components

- **`Header.svelte`**:
  - **Layout:** Sticky, with a blurred, semi-transparent dark background (e.g., `bg-gray-950/90`) for contrast against the light page. Accented with a `border-b-2 border-[PrimaryColor]-600`. Includes a hamburger menu for mobile.
  - **Navigation:** Text is `text-white`, with a `hover:text-[PrimaryColor]-400` effect.

- **`Hero.svelte`**:
  - **Layout:** Full-screen on a `bg-white` base.
  - **Background:** Can feature a subtle, light background image with a strong semi-transparent white overlay (`bg-white/80`) to ensure text readability.
  - **Headline:** Use a gradient text effect from a darker gray to the `[PrimaryColor]`.

- **`ProblemSolution.svelte`**:
  - **Layout:** Full-screen, two-column layout on an alternating background (e.g., `bg-[PrimaryColor]-50`).
  - **Content:**
    - **Left Column (The Problem):** A headline stating a relatable problem (e.g., "Struggling with Compliance?") followed by text detailing the user's pain points.
    - **Right Column (The Solution):** A headline presenting the solution (e.g., "The Simple Path to Privacy"), followed by text explaining how the product resolves those specific pain points.

- **`AnimatedBorder.svelte`**:
  - **Styling:** The animated line and circle should use the `[PrimaryColor]` (e.g., `text-[PrimaryColor]-500` and `text-[PrimaryColor]-400`).

- **`Features.svelte`**:
   - **Layout:** Full-screen, centered content on an alternating background (e.g., `bg-white`).
   - **Content:** A main headline, a descriptive sub-headline, and a 3-column grid of feature cards. Each card has an icon, title, and description.

- **`HowItWorks.svelte`**:
  - **Card Accent:** Use a colored top-border accent: `border-t-4 border-[PrimaryColor]-400`.

- **`CTA.svelte`**:
  - **Background:** Can use a subtle gradient from a light gray to a light tint of the `[PrimaryColor]`.

- **`Footer.svelte`**:
  - **Layout:** A multi-column layout on a dark background based on the primary color (e.g., `bg-[PrimaryColor]-900`).
  - **Text:** Use a light, contrasting color (e.g., `text-[PrimaryColor]-100` or `text-white`).

*(Other components like `Features`, `Benefits`, `Pricing`, and `SEO` should follow the same structural principles, adapting their specific styles based on the sections above.)* 