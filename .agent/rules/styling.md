# Styling Rules & Design System

## 1. Design Theme

**Concept**: Minimalist, Achromatic Base with Light Blue Accent.
**Reference**: [Notly-Web](https://ninjin-sirisiri.github.io/Notly-Web/)

### Color Palette

- **Base Colors (Achromatic)**:
  - Text & Backgrounds: `Zinc` or `Slate` scale.
  - **Light Mode**:
    - Background: White (`#ffffff` / `zinc-50`)
    - Text: `zinc-950`
    - Borders: `zinc-200`
  - **Dark Mode**:
    - Background: `zinc-950`
    - Text: `zinc-50`
    - Borders: `zinc-800`

- **Accent Color (Light Blue)**:
  - **Light Mode**: `#2563eb` (Blue-600)
  - **Dark Mode**: `#3b82f6` (Blue-500)
  - **Usage**: Primary buttons, active states, link highlights, hover effects.

## 2. Dark Mode Strategy

- **Implementation**: Class-strategy (Tailwind `darkMode: 'class'`).
- **Behavior**:
  - Must match **System Preference** by default.
  - Must provide a **Toggle Switch** for manual override.

## 3. CSS & Tailwind Config (v4)

- **Utility-First**: Use Tailwind utility classes for 90% of styling.
- **Global/Complex Styles**:
  - Use `src/app.css` for complex animations or global styles (e.g., the hover effect).
  - Use `@apply` sparingly, prefer standard CSS within these blocks.
- **Variables**: Use CSS variables for colors to ensure seamless dark mode switching (e.g., `--background`, `--foreground`, `--primary`).

## 4. Component Architecture

- **`src/components/ui/`**:
  - Reusable, atomic components (Buttons, Inputs, Cards).
  - Styling should be headless-first (Shadcn-like) and heavily reusable.
- **Feature/Page Components**:
  - Place in `src/features/<feature>/components` or locally within page folders if unique.
  - Avoid globalizing specific business-logic components.

## 5. Responsive Design

- **Strategy**: **Mobile-First**.
  - Write base styles for mobile (`<640px`).
  - Use `md:` (Tablet) and `lg:`/`xl:` (Desktop) prefixes for larger screens.
- **Breakpoints**:
  - Mobile: Default
  - Tablet: `md` (768px)
  - Desktop: `lg` (1024px)

## 6. Animations & Interactions

- **Tone**: Understated, smooth, "Quiet".
- **Hover Effect (Standard Link)**:
  - **Behavior**: A line draws from left to right at the bottom of the element.
  - **Implementation**:
    ```css
    .hover-underline-animation {
      position: relative;
    }
    .hover-underline-animation::after {
      content: '';
      position: absolute;
      width: 0;
      height: 2px;
      bottom: 0;
      left: 0;
      background-color: var(--color-primary); /* Accent Color */
      transition: width 0.3s ease-out;
    }
    .hover-underline-animation:hover::after {
      width: 100%;
    }
    ```
- **Transitions**: Use `duration-200` or `duration-300` with `ease-in-out` for general UI interactions.
