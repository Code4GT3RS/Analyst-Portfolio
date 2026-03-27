# Design System Strategy: The Analytical Architect

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"Precision Noir."** 

In the world of Data & Business Analytics, clarity is the ultimate luxury. This system rejects the cluttered, "dashboard-style" aesthetic in favor of a high-end editorial experience. We move beyond the template look by using intentional asymmetry—where data visualizations might break the grid—and a sophisticated tonal depth that mimics the interface of a premium, custom-built analytical tool. The goal is to make the analyst’s work feel like a curated gallery of insights rather than a spreadsheet.

## 2. Colors & Surface Philosophy
The palette is a deep, monochromatic spectrum of obsidian and slate, punctuated by "Teritary Blue" for moments of critical insight.

### The "No-Line" Rule
To achieve a high-end feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined through background color shifts. For example, a content block using `surface-container-low` (#0e141c) should sit directly on the `background` (#0a0e14). The transition should be felt, not seen.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use the MD3 surface tiers to create "nested" depth:
*   **Base Layer:** `surface` (#0a0e14) for the main page background.
*   **Section Layer:** `surface-container-low` (#0e141c) for large content groupings.
*   **Object Layer:** `surface-container-high` (#16202e) for individual cards or data modules.
*   **Interactive Layer:** `surface-bright` (#1e2d41) for hover states or active selection.

### The "Glass & Gradient" Rule
Floating navigation bars or modal overlays must use **Glassmorphism**. Combine `surface-variant` (#1a2637) at 60% opacity with a `backdrop-blur` of 12px. To provide "visual soul," use a subtle linear gradient on primary CTAs transitioning from `tertiary` (#44a5ff) to `tertiary-container` (#2498f5) at a 135-degree angle.

## 3. Typography: The Editorial Edge
While the request suggested Montserrat or Roboto, we have elevated this to **Manrope** (Headings) and **Inter** (Body) to provide a more contemporary, technical, and high-end aesthetic.

*   **Display (Manrope):** Massive scale shifts. Use `display-lg` (3.5rem) for hero statements to create an immediate impact. The tracking should be tightened slightly (-0.02em) to feel "locked in."
*   **Headline (Manrope):** Reserved for project titles. Use `headline-lg` (2rem) with a semi-bold weight.
*   **Body (Inter):** The workhorse. Use `body-md` (0.875rem) for project descriptions. Inter’s high x-height ensures readability against dark backgrounds.
*   **Labels (Inter):** Use `label-md` (0.75rem) in all-caps with increased letter spacing (+0.1em) for metadata like "Date" or "Industry" to give it a technical, "scanned" feel.

## 4. Elevation & Depth
We eschew traditional drop shadows for **Tonal Layering** and **Ambient Glows.**

*   **The Layering Principle:** Depth is achieved by "stacking." A `surface-container-highest` card placed on a `surface` background creates a soft, natural lift without the need for a shadow.
*   **Ambient Shadows:** If a "floating" element (like a filter menu) is required, use a shadow with a 40px blur, 0px offset, and 6% opacity using the `on-surface` color. This creates a soft atmospheric glow rather than a muddy grey shadow.
*   **The Ghost Border:** If a container requires definition against a similar tone, use the `outline-variant` (#3c495b) at **15% opacity**. This "Ghost Border" provides just enough hint of a container without breaking the minimalist flow.

## 5. Components

### Buttons
*   **Primary:** A solid `tertiary` (#44a5ff) fill. No border. Radius `sm` (0.125rem) to maintain a sharp, professional edge.
*   **Secondary:** `surface-container-highest` fill with `on-surface` text. This feels integrated into the UI.
*   **Tertiary:** Text-only with an underline that appears on hover, using the `primary` (#bfc7ce) token.

### Data Cards
**Strict Rule:** No divider lines. Use vertical white space (Spacing `8` or `10`) to separate the header from the data visualization. The card itself should use `surface-container-low` with a subtle hover transition to `surface-container-high`.

### Input Fields & Search
*   **Background:** `surface-container-lowest` (#000000).
*   **Active State:** Instead of a thick border, use a 1px `tertiary` underline and a soft glow using the `tertiary-container` token at low opacity.

### Analytical Chips
*   Used for "Tools" (e.g., Python, SQL, Tableau).
*   **Style:** `surface-variant` background, `on-surface-variant` text. Sharp corners (Radius `none` or `sm`).

### Custom Component: The "Insight Highlight"
A bespoke component for portfolios: a vertical bar using the `tertiary` color (2px width) placed to the left of a `body-lg` quote or key finding. This creates an editorial "pull-quote" feel that highlights the analyst's value.

## 6. Do’s and Don’ts

### Do:
*   **Embrace the Void:** Use Spacing `16` (5.5rem) or `20` (7rem) between major sections to let the data breathe.
*   **Use Subtle Animation:** Fade-in-up transitions for cards should be extremely fast (200ms) and use a subtle cubic-bezier easing to feel "snappy" and high-performance.
*   **Tinted Imagery:** Any photography or screenshots of dashboards should be slightly de-saturated or tinted with the `primary-container` color to ensure they match the dark aesthetic.

### Don’t:
*   **Don't use pure white:** Never use #FFFFFF. Always use `on-surface` (#d9e6fd) for text to reduce eye strain and maintain the premium dark-mode feel.
*   **Don't use heavy rounding:** Avoid `xl` or `full` rounding for anything other than specific UI icons. This is a professional analytical tool; keep corners sharp (`sm` or `md`).
*   **Don't use standard blue:** Avoid default browser or "Bootstrap" blues. Always use the specified `tertiary` (#44a5ff) which has been tuned for high-contrast legibility on dark surfaces.