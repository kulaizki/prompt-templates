# Prompt Template: Modern SaaS Landing Page (Dark Theme)

## 1. Project Overview

**Objective:** Build a responsive, modern landing page for a SaaS product using a **sleek, premium dark theme**.
**Core Principles:**
- **Technology Stack:** SvelteKit, Svelte 5, Tailwind CSS, `svelte-inview`.
- **Design:** Elegant, modern, and fully mobile-responsive aesthetic with a dark base background.
- **Layout:** Immersive, full-screen sections (`min-h-screen`).
- **Theme:** A consistent color scheme using dark grays or blues (e.g., `bg-gray-950`) and a vibrant, dynamic `[PrimaryColor]` (e.g., cyan, lime, rose).
- **Animation:** Subtle on-scroll fades for all sections (triggered using `svelte-inview`) and an animated separator.

## 2. Global Styles & Configuration
- **Tailwind:** Configure `tailwind.config.js` to include the dynamic `[PrimaryColor]` palette.
- **Backgrounds:** Alternate section backgrounds between a base dark color (e.g., `bg-gray-950`) and a slightly lighter variant (e.g., `bg-gray-900`).

## 3. Page Structure & Components

- **`Header.svelte`**:
  - **Layout:** Sticky, with a blurred background that's slightly lighter than the page (e.g., `bg-gray-900/80`) to create depth. Accented with a `border-b-2 border-[PrimaryColor]-500`. Includes a hamburger menu for mobile.
  - **Navigation:** Text is a light gray (e.g., `text-gray-200`), with a `hover:text-[PrimaryColor]-400` effect.

- **`Hero.svelte`**:
  - **Layout:** Full-screen on the base dark background.
  - **Background:** Can feature a subtle, dark background image with a semi-transparent dark overlay (`bg-black/50`) to enhance text contrast.
  - **Headline:** Use a gradient text effect from a light gray to the vibrant `[PrimaryColor]`.

- **`ProblemSolution.svelte`**:
  - **Layout:** Full-screen, two-column layout on an alternating background (e.g., `bg-gray-900`).
  - **Content:**
    - **Left Column (The Problem):** A headline in a light color stating a relatable problem, followed by text detailing user pain points.
    - **Right Column (The Solution):** A headline styled with the `[PrimaryColor]` presenting the solution, followed by text explaining how the product resolves those pain points.

- **`AnimatedBorder.svelte`**:
  - **Styling:** The animated line and circle should use the `[PrimaryColor]`, ensuring they have a glow/drop-shadow effect to pop against the dark background.

- **`Features.svelte`**:
  - **Layout:** Full-screen, centered content on an alternating background (e.g., `bg-gray-950`).
  - **Content:** A main headline, a descriptive sub-headline, and a 3-column grid of feature cards. Cards should have a slightly lighter background than the page (e.g., `bg-gray-900`).

- **`HowItWorks.svelte`**:
  - **Card Styling:** Cards should have a slightly lighter background than the page (e.g., `bg-gray-900`) and a top-border accent: `border-t-4 border-[PrimaryColor]-500`.

- **`CTA.svelte`**:
  - **Background:** Can use a subtle gradient, for instance from the base dark color to a dark shade of the `[PrimaryColor]`.

- **`Footer.svelte`**:
  - **Layout:** A multi-column layout on a deep, dark background (e.g., `bg-black/50`).
  - **Text:** Use a light gray or off-white color for readability.

*(Other components like `Features`, `Benefits`, `Pricing`, and `SEO` should follow the same structural principles, adapting their specific styles based on the sections above.)* 