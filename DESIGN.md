# Design System Strategy: 



## Colors

The palette is anchored by a rejuvenating teal-mint, supported by deep slate tones that provide the necessary "weight" and trustworthiness for a medical service.

### Palette Strategy
*   **Primary (#4DB6AC):** Used for restorative actions and brand identity. This primary color is directly reflected in the technical specification.
*   **Secondary (#2C3E50):** Provides the professional, "dark slate" contrast required for less prominent UI elements, chips, and secondary actions.
*   **Tertiary (#80CBC4):** An additional accent for highlights, badges, or decorative elements.
*   **Neutral (#F5F7F7):** A neutral base color for backgrounds, surfaces, and non-chromatic elements.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to separate sections. Boundaries must be defined solely through background color shifts. A section using `surface_container_low` should sit adjacent to a `surface` section to create a natural, "no-line" break.

### The Glass & Gradient Rule
To move beyond a generic healthcare look, use **Glassmorphism** for floating UI elements (e.g., info chips over hero images). 
*   **Effect:** Apply `surface_container_lowest` at 70% opacity with a 12px backdrop-blur. 
*   **Soulful Gradients:** For primary CTAs or high-impact hero sections, use a subtle linear gradient from the `primary` color (#4DB6AC) to the `tertiary` color (#80CBC4) at a 135-degree angle.

---

## Typography

The system employs a dual-font strategy: **Manrope** for authoritative, modern expression and **Inter** for clinical precision and readability.

*   **Display & Headlines (Manrope):** Chosen for its geometric purity and "premium" feel. Use `display-lg` (3.5rem) for hero statements to establish immediate market leadership.
*   **Body & Labels (Inter):** A workhorse typeface that ensures accessibility in medical documentation. `body-lg` (1rem) is the standard for patient information to reduce cognitive load.
*   **Hierarchy as Identity:** The massive scale jump between `display-sm` (2.25rem) and `body-md` (0.875rem) creates an editorial look that feels curated rather than computer-generated.

---

## Elevation & Depth

We reject traditional drop-shadows in favor of **Tonal Layering**.

### The Layering Principle
Depth is achieved by "stacking" the surface-container tiers. 
*   **Example:** Place a `surface_container_lowest` (#FFFFFF) card on a `surface_container_low` (#F2F4F4) section. This creates a soft, natural lift that mimics fine paper without the "dirtiness" of a shadow.

### Ambient Shadows
If a floating effect is vital (e.g., a "Book Now" floating action button):
*   **Blur:** 24px - 40px.
*   **Opacity:** 4% to 6%.
*   **Color:** Use a tinted version of `on_surface` (a deep slate-grey) rather than pure black to keep the UI "airy."

### The "Ghost Border" Fallback
If a border is required for accessibility:
*   **Token:** `outline_variant`.
*   **Opacity:** 15%.
*   **Rule:** Never use 100% opaque borders. They clutter the visual field and break the "Restoration Gallery" aesthetic.

---

##  Components

### Buttons (The "Action" Primitives)
*   **Primary:** Filled with the `primary` color, no border, maximum (`3`) roundedness. 
*   **Secondary:** Outlined with the "Ghost Border" (15% opacity `outline_variant`). 
*   **Interaction:** On hover, the primary button should shift to `on_primary_fixed_variant` for a subtle, professional darkening.

### Cards & Lists
*   **Constraint:** Forbid the use of divider lines. 
*   **Alternative:** Separate list items using 16px of vertical white space or a subtle `surface_container_highest` background on hover.
*   **Styling:** Use maximum (`3`) roundedness for cards to feel approachable and modern.

### Input Fields
*   **Background:** Use `surface_container_highest` (#E1E3E3) for the input track.
*   **Active State:** A 2px bottom-bar in the `primary` color (#4DB6AC) rather than a full-box highlight to maintain a "clean clinical" look.

### Specialist Component: The "Therapist Profile Card"
*   **Layout:** Overlap the therapist's portrait (circular or organic shape) 20px outside the card boundary to break the grid.
*   **Background:** `surface_container_lowest` with an Ambient Shadow (4% opacity).

---

##  Do's and Don'ts

### Do:
*   **Do** use moderate (`2`) spacing. If you think there is enough padding, add 24px more.
*   **Do** use high-quality, warm-toned photography of humans. The teal palette handles warm skin tones beautifully.
*   **Do** nest containers using the surface tiers (e.g., a `surface_container_high` search bar inside a `surface_container_low` header).

### Don't:
*   **Don't** use standard "Web Blue" for links. Use the `primary` teal for all interactive text.
*   **Don't** use sharp 90-degree corners. Everything must feel "softened" (maximum roundedness) to align with a healing service.
*   **Don't** use pure black (#000000) for text. Always use `on_surface` (#191C1D) to maintain the "Dark Slate" professional tone.