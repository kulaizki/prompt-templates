# Prompt Template: Modern SaaS Landing Page (Light Theme)

This template provides a comprehensive blueprint for creating a responsive, animated, and professional SaaS landing page with a **light and airy theme**.

## 1. Project Initialization & Structure

### 1.1. Dependencies
Ensure the following dependencies are installed in your SvelteKit project:
- `tailwindcss`
- `svelte-inview`: For triggering animations on scroll.
- `autoprefixer`, `postcss`

```json
"devDependencies": {
  "tailwindcss": "^3.4.1",
  "svelte-inview": "^4.0.2",
  // ... other SvelteKit dependencies
}
```

### 1.2. Folder Structure
Organize your project with a component-based architecture.

```
/src
├── /lib
│   └── /components
│       ├── Header.svelte
│       ├── Footer.svelte
│       ├── SEO.svelte
│       ├── Hero.svelte
│       ├── Features.svelte
│       ├── HowItWorks.svelte
│       ├── Benefits.svelte
│       ├── Pricing.svelte
│       ├── CTA.svelte
│       └── BackToTop.svelte
├── /routes
│   ├── +layout.svelte
│   └── +page.svelte
└── app.css
```

## 2. Global Configuration & Layout

### 2.1. Tailwind Configuration (`tailwind.config.js`)
Set up a dynamic theme using a placeholder `[PrimaryColor]` (e.g., `sky`, `indigo`, `teal`).

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ['./src/**/*.{html,js,svelte,ts}'],
  theme: {
    extend: {
      colors: {
        primary: { // Example using 'sky'
          50: '#f0f9ff',
          100: '#e0f2fe',
          // ... add all shades 50 through 950
          950: '#082f49',
        }
      },
    },
  },
  plugins: [],
};
```

### 2.2. Root Layout (`src/routes/+layout.svelte`)
This file wraps every page, ensuring consistent layout and including global components.

```svelte
<script lang="ts">
  import '../app.css';
  import Header from '$lib/components/Header.svelte';
  import Footer from '$lib/components/Footer.svelte';
  import SEO from '$lib/components/SEO.svelte';
</script>

<SEO />

<div class="flex flex-col min-h-screen bg-white">
  <Header />
  <main class="flex-1">
    <slot />
  </main>
  <Footer />
</div>
```

### 2.3. SEO Component (`src/lib/components/SEO.svelte`)
Centralize metadata management for better search engine optimization.

```svelte
<script lang="ts">
  // Props for dynamic metadata
  export let title = 'ConsentPro - Simplified Data Privacy Compliance';
  export let description = 'A default description for your awesome SaaS product.';
</script>

<svelte:head>
  <title>{title}</title>
  <meta name="description" content={description} />
  <!-- Add other tags like Open Graph, Twitter Cards, etc. -->
</svelte:head>
```

## 3. Core Component Implementation

### 3.1. `Header.svelte`
- **Objective:** Provide clear, persistent navigation.
- **Styling:**
  - A sticky header with a light, blurred background: `sticky top-0 z-50 bg-white/80 backdrop-blur-md`.
  - A subtle bottom border: `border-b border-gray-200`.
  - Navigation links should be dark: `text-gray-700`, with a hover effect: `hover:text-primary-600`.
  - The primary CTA button should be prominent: `bg-primary-600 text-white hover:bg-primary-700`.
- **Functionality:**
  - Implement a `smoothScroll` function to handle anchor links (`/#features`). This function should navigate to the homepage if the user is on another page, then scroll.
  - The logo should link to `/` and use `smoothScroll` to scroll to the top of the page.
  - A hamburger menu for mobile that toggles a full-width dropdown.

### 3.2. `Footer.svelte`
- **Objective:** Provide secondary navigation, legal links, and company information.
- **Styling:**
  - A dark, contrasting background: `bg-gray-800`.
  - Text should be light: `text-gray-300`, with `text-white` for headings.
  - Links have a subtle hover effect: `hover:text-white`.
- **Functionality:**
  - Re-use the `smoothScroll` function for any anchor links.

### 3.3. Section Components (`Features`, `Benefits`, `HowItWorks`, etc.)
- **Objective:** Showcase product information in visually distinct, full-screen sections.
- **Layout:**
  - Each component should have a root `<section>` with `min-h-screen` and `flex items-center justify-center` for vertical centering.
  - Alternate section backgrounds for visual separation: `bg-white` and `bg-primary-50` (or `bg-gray-50`).
- **Animation:**
  - Use `svelte-inview` on the main section container.
  - When the section enters the viewport (`on:inview_change`), trigger fade-in and slide-up animations on child elements (headings, cards, etc.).
  - Apply staggered delays to list items or grid elements for a sequential animation effect.
  - **Example:** `class="transition-all duration-700 {isInView ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-10'}" style="transition-delay: {i * 150}ms"`.
- **Styling Details:**
  - **Headings:** Use a dark, bold font: `text-4xl font-bold text-gray-900`.
  - **Subheadings:** Lighter text: `text-lg text-gray-600`.
  - **Cards:** Use `bg-white`, `rounded-lg`, `shadow-lg`, and a subtle `border border-gray-200`. On hover, increase the shadow and add a slight lift: `hover:-translate-y-1`.

### 3.4. `Pricing.svelte`
- **Objective:** Clearly present pricing tiers.
- **Styling:**
  - Highlight the "Most Popular" plan.
  - Use a border: `border-2 border-primary-500`.
  - Add a "badge": `absolute top-0 -translate-y-1/2 ... bg-primary-500 text-white`.
  - Make this plan physically larger or have a stronger shadow to draw attention.

### 3.5. `BackToTop.svelte`
- **Objective:** Improve navigation on long pages.
- **Functionality:**
  - Use `svelte:window on:scroll` to track scroll position.
  - Show the button only when the user has scrolled past a certain point (e.g., `window.innerHeight / 2`).
  - Use a Svelte transition (`fly` or `fade`) for smooth appearance/disappearance.
  - On click, use `window.scrollTo({ top: 0, behavior: 'smooth' })`.
- **Styling:**
  - A floating button with `fixed bottom-6 right-6`.
  - Circular shape (`rounded-full`) with an icon.
  - Use the primary color for the background: `bg-primary-500 hover:bg-primary-600`.

This detailed prompt ensures the generated landing page is modern, consistent, and adheres to best practices for UX and design. 
