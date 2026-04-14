# Design System Specification: The Ethereal Productivity Framework

## 1. Overview & Creative North Star: "The Digital Sanctuary"
This design system moves away from the rigid, boxed-in layouts of traditional SaaS and toward a philosophy of **The Digital Sanctuary**. The goal is to transform productivity from a source of stress into a state of flow. 

To achieve a "high-end editorial" feel, we prioritize **Atmospheric Depth** over structural rigidity. We break the "standard template" look by utilizing intentional asymmetry, expansive whitespace, and a "No-Line" architectural philosophy. The UI should feel like a series of fine paper layers floating in a light-filled room—organized, breathable, and premium.

---

## 2. Color & Surface Philosophy
The palette is rooted in soft whites and luminous blues, designed to reduce cognitive load and eye strain.

### The "No-Line" Rule
**Borders are a legacy of physical constraints.** In this system, 1px solid borders for sectioning are strictly prohibited. Boundaries must be defined through:
*   **Tonal Shifts:** Placing a `surface-container-lowest` card on a `surface-container-low` background.
*   **Soft Geometry:** Using the `xl` (1.5rem) corner radius to create distinct shapes that "nest" into one another.

### Surface Hierarchy & Nesting
Treat the interface as a physical stack. Use the `surface-container` tiers to create logical grouping:
*   **Base:** `background` (#f8f9fb)
*   **Sections:** `surface-container-low` (#f0f4f7)
*   **Primary Cards:** `surface-container-lowest` (#ffffff)
*   **Interactions (Hover/Active):** `surface-container-high` (#e3e9ed)

### The "Glass & Gradient" Rule
To elevate the experience beyond "flat," use **Glassmorphism** for floating navigation and modal overlays. Use `surface-container-lowest` with a 70% opacity and a `24px` backdrop blur. 
*   **Signature Textures:** For high-impact CTAs, use a subtle linear gradient from `primary` (#0061aa) to `primary-container` (#429efd) at a 135-degree angle. This adds "soul" and a sense of light source to the UI.

---

## 3. Typography: The Editorial Voice
We use a dual-typeface system to balance authority with approachability.

*   **Display & Headline (Manrope):** A geometric sans-serif that feels modern and architectural. Use `display-lg` (3.5rem) with tighter letter-spacing (-0.02em) for hero sections to create a bold, editorial impact.
*   **Body & Labels (Inter):** Chosen for its exceptional legibility. Maintain generous line-heights (1.6 for body-lg) to ensure the "Zen" vibe is maintained even in text-heavy areas.
*   **Hierarchy Note:** Use `on-surface-variant` (#596064) for secondary body text to create a soft contrast that guides the eye toward the primary `on-surface` (#2c3437) headlines.

---

## 4. Elevation & Depth: Tonal Layering
We do not use shadows to simulate height; we use light to simulate presence.

*   **The Layering Principle:** Depth is achieved by "stacking." A `surface-container-lowest` element (White) naturally "pops" against a `surface-container-low` background without a single pixel of shadow.
*   **Ambient Shadows:** For elements that truly float (e.g., Popovers, Modals), use the **Ambient Shadow**:
    *   `box-shadow: 0 12px 40px rgba(44, 52, 55, 0.06);`
    *   Note: The shadow color is a tinted version of `on-surface`, never pure black.
*   **The "Ghost Border" Fallback:** If accessibility requires a stroke, use `outline-variant` (#acb3b7) at **15% opacity**. It should be felt, not seen.

---

## 5. Component Logic

### Buttons: The Tactile Point
*   **Primary:** Gradient fill (`primary` to `primary-container`), white text, `full` (pill) roundedness.
*   **Secondary:** `surface-container-highest` background with `on-secondary-container` text. No border.
*   **Interaction:** On hover, primary buttons should subtly scale (1.02) rather than just changing color.

### Cards & Lists: Organic Grouping
*   **Rule:** Forbid the use of divider lines.
*   **Execution:** Separate list items using 12px of vertical whitespace. For high-density data, use alternating background tints (`surface` vs `surface-container-lowest`) instead of lines.
*   **Rounding:** All cards must use `xl` (1.5rem) corners to maintain the "approachable" vibe.

### Input Fields: Soft Focus
*   **State:** Default inputs use `surface-container-highest` with no border.
*   **Focus State:** Transition to a `primary` "Ghost Border" (2px at 20% opacity) and a slight inner glow. This avoids the "heavy" look of standard input focus states.

### Floating Action Navigation (New Component)
Instead of a top-pinned bar, use a floating navigation dock using the **Glassmorphism** rule. This allows content to bleed behind the navigation, increasing the sense of "plenty of whitespace."

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace Asymmetry:** Offset your hero text to the left while floating a glass-morphic card to the right. Symmetry is for templates; asymmetry is for design.
*   **Use White as a Color:** Treat whitespace as a functional element that separates ideas, not just "empty space."
*   **Contextual Coloring:** Use `tertiary-container` for subtle success states or "calm" notifications instead of aggressive greens.

### Don’t:
*   **Don't use 100% Black:** Pure black (#000000) is too harsh for this system. Use `on-background` (#2c3437) for all dark elements.
*   **Don't use Default Corners:** Avoid the `sm` or `none` rounding scales unless designing for technical data tables.
*   **Don't "Box" Content:** Avoid wrapping every section in a container with a background. Let the typography and spacing define the sections.