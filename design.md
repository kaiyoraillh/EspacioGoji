```markdown
# Design System Strategy: High-End Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Brutalist Gallery"**

This design system is built to transform a physical event space into a digital landmark. We are moving away from the "template" aesthetic of local business sites and toward a high-end, editorial experience. The system leverages **Organic Brutalism**: a juxtaposition of raw, bold typography against a soft, creamy canvas.

The strategy breaks the grid through **Intentional Asymmetry**. Large-scale display type should feel "anchored" to the edges of the viewport, while content blocks float with generous, breathing whitespace. We don't just present information; we curate an architectural journey.

## 2. Color & Surface Architecture
The palette is a high-contrast dialogue between the warmth of a sun-drenched patio and the electric energy of a premium event.

### The Palette
- **The Canvas (`surface` / #fffad9):** Our primary environment. It’s a soft, light cream that feels more tactile and premium than a sterile white.
- **The Pulse (`primary` / #b30069):** A sophisticated Fucsia. Use this sparingly for high-impact moments: CTAs, active states, and key highlights.
- **The Ink (`on-surface` / #1e1c00):** A deep, olive-toned black. Never use pure #000000; this near-black provides better legibility and a more "printed" feel.

### The "No-Line" Rule
To maintain an avant-garde editorial look, **1px solid borders for sectioning are strictly prohibited.** Do not use lines to separate "Home" from "About."
- **The Solution:** Boundaries must be defined solely through background color shifts. Use `surface-container-low` (#fcf7ae) for secondary sections sitting on the main `surface`.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of fine paper.
- **Level 0 (Base):** `surface` (#fffad9)
- **Level 1 (Sections):** `surface-container-low` (#fcf7ae)
- **Level 2 (Cards/Interaction):** `surface-container-highest` (#eae59e)

### The "Glass & Gradient" Rule
Flat is boring. To add "soul," apply a subtle linear gradient to the `primary` buttons, transitioning from `#b30069` to `#df0e84` at a 135-degree angle. For floating navigation or overlays, use **Glassmorphism**: a background of `surface_container_lowest` at 80% opacity with a `20px` backdrop-blur.

## 3. Typography
Typography is our primary brand asset. It should feel loud but disciplined.

| Level | Token | Font Family | Size | Case | Letter Spacing |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Space Grotesk (Bold) | 3.5rem | ALL CAPS | -0.02em |
| **Headline**| `headline-lg`| Space Grotesk (Bold) | 2.0rem | ALL CAPS | 0.05em |
| **Title** | `title-lg` | Inter (Medium) | 1.375rem| Sentence | 0 |
| **Body** | `body-lg` | Inter (Regular) | 1.0rem | Sentence | 0 |
| **Label** | `label-md` | Inter (Bold) | 0.75rem | ALL CAPS | 0.1em |

**Editorial Note:** Headlines should often be "broken" across lines to create rhythmic tension. Large `display-lg` elements can overlap section color shifts to "stitch" the layout together.

## 4. Elevation & Depth
We eschew traditional drop shadows in favor of **Tonal Layering**.

- **The Layering Principle:** Depth is achieved by "stacking." A `surface-container-lowest` card placed on a `surface-dim` section creates a soft, natural lift without the need for a shadow.
- **Ambient Shadows:** Only for floating elements (like a Modals). Use a large blur (32px) at 6% opacity using the `on-surface` color. It should feel like a soft glow, not a dark smudge.
- **The Ghost Border:** If a border is required for a form input, use `outline-variant` (#e1bdc8) at 20% opacity. It should be barely visible—an "afterimage" of a line.

## 5. Components

### Buttons (The "Statement" Component)
- **Primary:** Background `primary`, Text `on-primary`. 0px border radius. Padding: `1rem 2.75rem` (Spacing 3 / 8).
- **Hover State:** Shift background to `primary_container`. Transition: `200ms cubic-bezier(0.4, 0, 0.2, 1)`.
- **Secondary:** Transparent background, `primary` text, with a 2px `primary` underline. No box.

### Cards & Lists (The "Gallery" Style)
- **Rules:** Forbid all divider lines.
- **Spacing:** Separate list items using `spacing-6` (2rem).
- **Interaction:** On hover, a card should shift from `surface-container` to `surface-bright`.

### Input Fields
- **Style:** Underline only. Use `outline` token (#8d6f79) for the bottom border (1px).
- **Focus:** The border becomes `primary` and thickens to 2px. Label moves to `label-sm` above the input.

### Signature Component: The "Event Ledger"
A vertical list for event dates where the date is `display-md` (Space Grotesk) and the event description is `body-md` (Inter). No borders—only a subtle background shift on the active item.

## 6. Do’s and Don’ts

### Do:
- **Use "Extreme" Spacing:** Use `spacing-24` (8.5rem) between major sections. If it feels like "too much" space, it’s probably just right.
- **Embrace the Corner:** Keep all `border-radius` at `0px`. Sharp corners convey precision and architectural intent.
- **Align to the Left:** Use a strong left-aligned axis for all text to mimic high-end magazine layouts.

### Don't:
- **No Emojis:** They dilute the premium nature of the brand. Use custom SVG icons with 1.5px stroke weight if needed.
- **No Pure Greys:** All neutrals must be tinted with the cream (`surface`) or fucsia (`primary`) tones to avoid a "default" look.
- **No Centered Body Text:** Centered text is for greeting cards. We are a gallery. Keep body text aligned left or justified with high-end kerning.
- **No 1px Dividers:** If you need a divider, use a `4px` tall block of `primary` color that only spans 10% of the container width. It’s a "mark," not a line.