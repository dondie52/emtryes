# Technical Specification: Industrial Editorial Design System

## 1. Overview & Creative North Star
**Creative North Star: The Tectonic Blueprint**

This design system moves away from the ephemeral nature of modern SaaS and anchors itself in the weight, precision, and permanence of heavy industry. It is inspired by the structured chaos of a mining site and the mathematical exactitude of an engineering schematic. 

The aesthetic is "Industrial Editorial." We treat the interface not as a collection of widgets, but as a high-end technical publication. We break the "template" look by utilizing intentional asymmetry—where large, heavy typography anchors the page, and content is organized into rigid, tectonic slabs. Every element must feel like it was machined, not grown. There are no "bubbles" here; only structural integrity.

## 2. Colors & Surface Architecture
The color palette is derived from the raw materials of the transport and mining industries: oxidized steel, deep trench shadows, and high-visibility safety markers.

### The Palette (Token Implementation)
*   **Primary (Deep Navy):** `primary` (#051125) / `primary_container` (#1B263B). Used for foundational structural elements and deep-focus backgrounds.
*   **Secondary (Steel/Charcoal):** `secondary` (#47607e). Used for supplementary UI elements and technical iconography.
*   **Neutral (Light Grey/White):** `surface` (#f9faf5) and `on_surface` (#1a1c1a).
*   **Accent (Safety Amber):** `tertiary_fixed_dim` (#ffb95f). This is our "Safety Amber." It is to be used with extreme restraint—only for critical calls to action or alert states.

### The "No-Line" Rule & Tectonic Layering
Standard UI uses 1px borders to separate content. This system forbids it for general sectioning. Instead, we use **Tectonic Layering**:
*   **Background Shifts:** Define boundaries solely through background color shifts. A `surface_container_low` section should sit against a `surface` background to create a visible but borderless edge.
*   **Nesting:** Treat the UI as stacked sheets of metal. An inner card should move from `surface_container` to `surface_container_high` to indicate depth.
*   **Signature Textures:** For hero sections, move beyond flat fills. Use a subtle linear gradient from `primary` to `primary_container` at a 45-degree angle to mimic the sheen of industrial paint.

## 3. Typography: The Authoritative Voice
We utilize **Inter** as our single source of truth. Its neutral, structured geometry mirrors the legibility required in engineering environments.

*   **Display Scales (High-Impact):** Use `display-lg` (3.5rem) and `display-md` (2.75rem) for high-end editorial layouts. These should be set with tight letter-spacing (-0.02em) to feel "heavy" and authoritative.
*   **Headlines & Titles:** Use `headline-lg` (2rem) for section headers. Always align these to a rigid grid; do not center-align headline text.
*   **Body & Labels:** Use `body-md` (0.875rem) for technical descriptions. Use `label-sm` (0.6875rem) in all-caps for metadata, mimicking the "stamped" text found on heavy machinery components.

## 4. Elevation & Depth
In this system, "elevation" does not mean "floating." It means "stacking."

*   **Tonal Layering:** Avoid drop shadows for standard cards. Achieve hierarchy by placing a `surface_container_lowest` element on top of a `surface_dim` background. 
*   **Ambient Shadows:** If an element must float (e.g., a critical modal), use an ultra-diffused shadow: `blur: 40px`, `opacity: 6%`, using a tint of `on_surface` (#1a1c1a). It should feel like a soft ambient occlusion, not a "web shadow."
*   **The "Ghost Border" Exception:** If accessibility requires a border, use the `outline_variant` token at 15% opacity. This creates a "Ghost Border" that suggests a boundary without breaking the minimalist industrial flow.
*   **Glassmorphism (Industrial Grade):** For navigation overlays or floating menus, use `surface` colors at 85% opacity with a `20px backdrop-blur`. This simulates frosted safety glass.

## 5. Components

### Buttons
*   **Sharpness:** All buttons have a `0px` border-radius.
*   **Primary:** `primary_container` background with `on_primary` text. High-contrast, heavy.
*   **CTA (Safety Amber):** `tertiary_fixed_dim` background. Use only once per view.
*   **State:** Hover states should not use "lightening" effects; instead, shift the background color to the next tier in the surface scale (e.g., from `primary` to `secondary`).

### Input Fields
*   **Structure:** Rectangular, sharp-edged boxes. 
*   **Borders:** Use a `1px` solid `outline` (#75777d) for the resting state. Upon focus, the border weight should increase to `2px` using the `secondary` color, never rounded.
*   **Labels:** Use `label-md` placed strictly above the input, never floating inside.

### Cards & Data Lists
*   **No Dividers:** Forbid the use of horizontal rules. Separate list items using `16px` or `24px` of vertical white space or by alternating background tones between `surface_container_low` and `surface_container_lowest`.
*   **Asymmetric Layouts:** For cards, place the heavy typography (`title-lg`) at the top left and the metadata/labels at the bottom right to create a "Technical Drawing" feel.

### Specialized Components: The "Status Gauge"
Given the industrial context, use heavy horizontal bars for progress or status. Use `surface_variant` for the track and `primary` or `tertiary_fixed_dim` (for warnings) for the fill. Avoid thin, spindly lines.

## 6. Do’s and Don’ts

### Do:
*   **Embrace the Grid:** Align every element to a strict 8px/16px grid.
*   **Use Hard Edges:** Ensure every corner—from buttons to images—is a perfect 90-degree angle (`0px` radius).
*   **Leverage Negative Space:** Use large gaps between sections to convey a sense of scale and "Premium Industrial" quality.

### Don’t:
*   **No Rounded Bubbles:** Never use the `full` or `xl` roundedness tokens.
*   **No SaaS Pastels:** Avoid soft purples, pinks, or "friendly" gradients.
*   **No Center Alignment:** Avoid centering text for long-form content. Industrial blueprints are left-aligned and structured; the UI should be too.
*   **No Standard Shadows:** Do not use the default "Drop Shadow" presets in design tools. Use Tonal Layering first.