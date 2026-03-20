# Design System Strategy: Kinetic Precision

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Kinetic Court."** 

Badminton is a sport of extreme contrasts: the feather-light shuttlecock versus the explosive smash; the rigid geometry of the court versus the fluid movement of the athlete. This design system moves away from the "data-heavy spreadsheet" aesthetic of traditional tournament software. Instead, it adopts an editorial, high-performance feel. 

We break the "template" look by using **intentional asymmetry**—large display typography overlapping subtle athletic textures—and a **"No-Line" philosophy**. By relying on tonal shifts and layered surfaces rather than rigid borders, the UI feels expansive and energetic, mirroring the agility required on the court.

---

## 2. Colors: The Crimson-Rose Tension
The palette balances the high-energy `primary` (a vibrant crimson, e.g., `#c83431`) with the authoritative `secondary` (a muted rose, e.g., `#c35167`).

*   **Primary (Crimson):** Used for momentum. It signifies action, progress, and victory.
*   **Secondary (Rose):** Used for stability. It anchors the navigation and high-level tournament data.
*   **Tertiary (Violet):** An additional accent color (e.g., `#945fc4`) for highlights, badges, or decorative elements.
*   **Neutral (Grayish Red):** A neutral base color (e.g., `#a1676f`) for backgrounds, surfaces, and non-chromatic elements.
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. To separate the "Tournament Bracket" from "Player Stats," use a background shift from `surface` to `surface-container-low`.
*   **Surface Hierarchy & Nesting:** Treat the UI as physical layers. A player's "Score Entry" card should be `surface-container-lowest` sitting atop a `surface-container` dashboard. This "stacking" creates a natural, soft depth.
*   **The "Glass & Gradient" Rule:** Main CTAs (like "Start Match") should use a linear gradient from `primary` to `primary_container`. For floating score overlays, use a Glassmorphic effect: `surface` color at 70% opacity with a 16px backdrop-blur.

---

## 3. Typography: Editorial Performance
We pair **Manrope** (Display/Headline) for athletic character with **Inter** (Title/Body) for technical precision.

*   **Display-LG (3.5rem):** Reserved for tournament titles or winning scores. Use tight letter-spacing (-0.02em) to create a "headline" feel.
*   **Headline-SM (1.5rem):** Used for card titles (e.g., "Player Ranking").
*   **Body-MD (0.875rem):** The workhorse for player stats and match history.
*   **Label-SM (0.6875rem):** Used for technical metadata (e.g., "Match Duration," "Seed Number").

The hierarchy is designed to be "scannable under pressure." In the heat of a tournament, the `display` and `headline` tiers tell the user *what* is happening, while the `body` tiers provide the *how*.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are too heavy for a "shuttlecock-light" aesthetic. We define depth through color, not darkness.

*   **The Layering Principle:** 
    *   Level 0: `surface` (Base background)
    *   Level 1: `surface-container-low` (Secondary content areas)
    *   Level 2: `surface-container-lowest` (Active cards/modals)
*   **Ambient Shadows:** For "floating" elements like a score-entry popover, use a shadow with a 32px blur, 4% opacity, using the `on-surface` color as the tint. This mimics natural light reflecting off a court surface.
*   **The "Ghost Border" Fallback:** If a border is required for a form field, use `outline-variant` at 20% opacity. Never use a 100% opaque stroke.
*   **Athletic Patterns:** Apply a subtle 5% opacity "court line" grid or "shuttlecock weave" pattern to `surface-variant` sections to add textural soul without distracting from the data.

---

## 5. Components: Fluid & Functional

### Cards & Stats
Cards must never have dividers. Group "Player Name," "Win/Loss Ratio," and "Rank" using generous vertical white space. Use a `surface-container-highest` accent bar on the left of a card to indicate the "Leading Player."

### Buttons
*   **Primary:** Gradient (Primary to Primary-Container), `pill-shaped` corners, `title-sm` typography.
*   **Secondary:** `secondary` with `on-secondary` text. No border.
*   **Tertiary:** Transparent background with `primary` text. Use for "Cancel" or "View Details."

### Score Entry Inputs
Inputs should feel tactile. Use `surface-container-low` with moderately rounded corners. Upon focus, the background shifts to `surface-container-lowest` with a subtle `primary` glow.

### Ranking Tables
Eliminate row lines. Use zebra-striping with `surface` and `surface-container-low`. Use `label-md` in `on-surface-variant` for headers to keep the focus on the player data.

### Tournament Brackets
Use "Ghost Borders" (20% opacity `outline-variant`) for the connector lines. This keeps the bracket light and prevents the UI from looking like a spiderweb.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use generous spacing to create significant "breathing room" between major modules.
*   **Do** use maximum roundedness for major dashboard containers to maintain a friendly, modern feel.
*   **Do** use color-coded chips (`tertiary` for "In Progress", `primary` for "Completed") to provide instant status recognition.

### Don’t:
*   **Don’t** use pure black (#000000) for text. Always use `on-surface` to maintain the color-toned professional harmony.
*   **Don’t** use sharp 90-degree corners. Everything in this system should feel fluid and aerodynamic.
*   **Don’t** use standard "drop shadows" on cards. Rely on the surface color hierarchy to define the edges of the content.