# Design System Specification: The Digital Atelier

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Atelier."** 

Unlike standard "Utility AI" apps that feel cold and clinical, this system is designed to feel like a private, high-end dressing room. We are blending the precision of artificial intelligence with the tactile, sensory world of personal styling. To move beyond the "template" look, we employ **Intentional Asymmetry**—where editorial-style imagery overlaps container boundaries—and **Extreme White Space**, treating negative space not as "empty," but as a luxury material. The interface does not "command"; it "curates."

---

## 2. Colors & Surface Philosophy

The palette is rooted in warmth, moving away from the "tech blue" status quo to embrace corals, soft golds, and warm pinks.

### The "No-Line" Rule
**Explicit Instruction:** You are prohibited from using 1px solid borders for sectioning or grouping content. Boundaries must be defined solely through background color shifts or tonal transitions.
*   **The Logic:** Physical lines create "boxes." We want "flow." 
*   **Implementation:** A section using `surface_container_low` (#f4f3f2) should sit against a `background` (#faf9f8) to define its area.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers, like stacked sheets of fine vellum paper. 
*   **Base Layer:** `surface` (#faf9f8).
*   **Sectional Layer:** `surface_container_low` (#f4f3f2) or `surface_container` (#eeeeed).
*   **Interactive Layer (Cards):** Use `surface_container_lowest` (#ffffff) to create a soft, natural lift against darker backgrounds.

### The "Glass & Gradient" Rule
To inject high-tech "soul" into the premium aesthetic:
*   **Glassmorphism:** For floating navigation bars or overlays, use `surface` at 80% opacity with a `backdrop-blur` of 16px–24px.
*   **Signature Textures:** Main CTAs and high-impact moments should utilize a subtle linear gradient from `primary` (#a43c12) to `primary_container` (#ea6f42). This mimics the way light hits silk or polished coral.

---

## 3. Typography: The Editorial Voice

We pair two distinct sans-serifs to balance technical precision with high-fashion elegance.

*   **Display & Headlines (Plus Jakarta Sans):** These are our "editorial" voices. Use `display-lg` and `headline-lg` with generous letter spacing (-0.02em) to create a sense of authority and breath. 
*   **Body & Labels (Manrope):** Chosen for its modern, geometric clarity. Manrope handles the "AI data" (color analysis results, measurements) with high legibility.
*   **Hierarchy Tip:** Contrast a `display-sm` headline with a `label-md` in all-caps (tracked out +10%) for a premium, magazine-style layout.

---

## 4. Elevation & Depth: Tonal Layering

Traditional drop shadows are often too "heavy" for a feminine, modern aesthetic. We achieve depth through light and tone.

*   **The Layering Principle:** Stack `surface_container_lowest` (#ffffff) on top of `surface_dim` (#dadad9) to create a crisp, shadowless elevation.
*   **Ambient Shadows:** If a floating element (like a FAB or Tooltip) requires a shadow, it must be "Ambient."
    *   **Shadow Specs:** `0px 12px 32px rgba(88, 65, 66, 0.06)`. Note the use of `on_surface_variant` (#584142) as the shadow tint rather than pure black.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use the `outline_variant` (#e0bfc0) at **15% opacity**. It should be felt, not seen.

---

## 5. Components

### Buttons
*   **Primary:** Gradient of `primary` to `primary_container`. Text color `on_primary`. Roundedness: `full`.
*   **Secondary:** Solid `secondary_container` (#fed65b) with `on_secondary_container` text.
*   **Interaction:** On hover, apply a `surface_bright` inner-glow (0.5px white top-border) to simulate a physical button catching the light.

### Cards & Lists
*   **The Card Rule:** Never use dividers. Use vertical whitespace (refer to `xl` spacing) to separate thoughts. 
*   **Imagery:** Use `lg` (1rem) corner radius for images. Silhouette-style illustrations should "break the box," partially overlapping the card edge to create depth.

### Input Fields
*   **Style:** Minimalist. No bottom line. No full border. 
*   **Container:** Use `surface_container_high` (#e9e8e7) with a `sm` (0.25rem) radius. 
*   **State:** On focus, the background transitions to `surface_container_lowest` (#ffffff) with a 1px "Ghost Border" of `primary` at 20% opacity.

### Selection Chips
*   **Action Chips:** High-pill shape (`full`). 
*   **Unselected:** `surface_container` with `on_surface_variant`.
*   **Selected:** `tertiary_container` (#c2828f) with `on_tertiary_container` text. This soft mauve provides a sophisticated, feminine "pop" without being aggressive.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical margins (e.g., 24px left, 40px right) for hero sections to create an editorial feel.
*   **Do** use `tertiary` (#864e5a) for "Insight" moments—where the AI provides a personal style tip.
*   **Do** embrace the "soft gold" of the `secondary` scale for premium/loyalty features.

### Don’t
*   **Don’t** use 100% black (#000000) for text. Use `on_surface` (#1a1c1c) to maintain warmth.
*   **Don’t** use "Alert Red" for errors if possible. Use `error` (#ba1a1a) sparingly, and consider a soft `error_container` background to keep the interface feeling approachable.
*   **Don’t** crowd the screen. If a screen feels "busy," increase the padding to the `xl` (1.5rem) or `full` scale.

---

## 7. Special Visual Elements: Elegant Silhouettes
When using silhouettes or illustrations:
*   **Color:** Use `outline` (#8c7071) for thin-line illustrations.
*   **Weight:** Keep line weights consistent with the `label-sm` font weight to ensure visual harmony across text and icons.
*   **Motion:** Elements should fade in with a "Slight Rise" (y-axis shift of 10px) to mimic the lightness of fabric.