# Design System Strategy: The Living Canvas

## 1. Creative North Star: "The Living Canvas"
This design system moves away from the rigid, boxed-in layouts of traditional administrative portals. Instead, it adopts a "Living Canvas" philosophy—an editorial-inspired framework where community energy meets ecological stewardship. 

By utilizing intentional asymmetry, high-contrast typography scales, and overlapping organic layers, we create a digital environment that feels breathable and premium. We don't just "list" volunteer opportunities; we curate an inspiring narrative of impact. The goal is to move beyond "standard" UI into a space that feels custom-built, authoritative, and deeply rooted in the natural world.

---

## 2. Colors & Atmospheric Depth
Our palette is a sophisticated interplay of deep forest greens, invigorating teals, and stable sky blues. These are not merely decorative; they define the functional architecture of the interface.

### The "No-Line" Rule
To maintain a high-end editorial feel, **explicitly prohibit the use of 1px solid borders for sectioning.** Physical boundaries must be defined solely through background color shifts or tonal transitions.
*   **Sectioning:** A section using `surface-container-low` should sit directly against a `surface` background to define its territory.
*   **Depth through Nesting:** Treat the UI as a series of stacked sheets. An inner card should use `surface-container-lowest` (the brightest white) to "float" atop a `surface-container-low` section, creating natural depth without visual clutter.

### The "Glass & Gradient" Rule
To avoid a "flat" or "template" look, use glassmorphism for floating elements (like navigation bars or hovering action cards). 
*   **Technique:** Apply a semi-transparent `surface` color with a 12px–20px backdrop-blur. 
*   **Signature Textures:** For primary CTAs and Hero backgrounds, use a subtle linear gradient (135°) transitioning from `primary` (#0f5238) to `primary-container` (#2d6a4f). This adds a "soul" to the interface that flat fills cannot achieve.

---

## 3. Typography: Editorial Authority
The system utilizes a dual-font strategy to balance professional clarity with energetic community focus.

*   **Display & Headlines (Manrope):** This is our "Editorial" voice. Use `display-lg` and `headline-lg` with generous letter-spacing (-0.02em) to create moments of inspiration. The geometric nature of Manrope conveys modern professionalism.
*   **Body & Titles (Plus Jakarta Sans):** This is our "Human" voice. Plus Jakarta Sans offers incredible legibility at smaller scales. Use `body-lg` for storytelling and `label-md` for metadata.
*   **Intentional Contrast:** Pair a `display-sm` headline in `primary` with a `body-md` description in `on-surface-variant`. The massive scale shift is what creates a premium, "designed" feel.

---

## 4. Elevation & Tonal Layering
We reject the standard "drop shadow" approach in favor of **Tonal Layering**. Depth is a result of light and material, not artificial lines.

*   **Layering Principle:** 
    1.  **Level 0 (Base):** `surface`
    2.  **Level 1 (Sections):** `surface-container-low`
    3.  **Level 2 (Interaction Cards):** `surface-container-lowest`
*   **Ambient Shadows:** If a floating effect is required (e.g., a modal or a primary action button), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(15, 82, 56, 0.06)`. Note the tint—the shadow should use a whisper of our `primary` color, never pure grey.
*   **The Ghost Border:** If a boundary is strictly required for accessibility, use `outline-variant` at 15% opacity. It should be felt, not seen.

---

## 5. Components & Interaction Patterns

### Buttons
*   **Primary:** Rounded `lg` (1rem). Background is a gradient of `primary` to `primary-container`. Text is `on-primary`.
*   **Secondary:** No fill. `surface-container-high` background on hover. Use `title-sm` for the label to ensure it feels substantial.
*   **Tertiary:** `tertiary` text with a `surface-tint` soft glow on interaction.

### Cards & Discovery Modules
*   **Forbid Dividers:** Never use a horizontal line to separate content within a card. Use vertical whitespace (32px+) or a subtle shift to `surface-container-high` for footer areas.
*   **Asymmetric Layout:** Experiment with "Hero Cards" where the image bleeds off one edge, breaking the container's symmetry to create a dynamic, energetic vibe.

### Input Fields
*   **Style:** Use `surface-container-low` as the field background. No bottom line. On focus, transition to `surface-container-lowest` with a 1px `primary` ghost-border (20% opacity).
*   **Feedback:** Error states use `error` and `error-container` sparingly, ensuring they don't break the calming eco-aesthetic.

### Signature Component: The Impact Node
A custom component for "Num Volunteer" that displays community stats. Use a large `display-md` number in `tertiary` color, nested within a `full` rounded (pill) container of `tertiary-fixed`. This creates an energetic "pulse" on the page.

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace the Void:** Use 80px+ margins between major sections to let the "eco-friendly" vibe breathe.
*   **Layer with Intent:** Always place lighter surfaces on darker ones to create "lift."
*   **Use Organic Shapes:** Utilize the `full` roundedness scale for chips and tags to mimic smooth river stones.

### Don’t:
*   **No "Heavy" Containers:** Avoid dark, solid backgrounds for large areas; they feel oppressive rather than energetic.
*   **No Sharp Corners:** Never use `none` or `sm` roundedness for cards. It contradicts the community-focused, approachable brand.
*   **No Default Grids:** Don't force every element to align to a rigid 12-column grid. Let some elements (like pull-quotes or decorative imagery) sit offset to create an editorial flow.