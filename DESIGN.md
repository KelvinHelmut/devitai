# Devitai Design System

## 1. Core Aesthetic
**Theme**: Retro-futurist Brutalism
**Vibe**: High-end boutique agency, "Intelligence Engineered", premium and sharp geometry.

### Key Principles
- **No Curves**: All interactive elements (buttons, cards, inputs, switchers) must use `rounded-none`. No exceptions.
- **Glassmorphism**: Use translucent backgrounds (`bg-slate-900/5` or `bg-white/5`) with `backdrop-blur` for structural depth.
- **Micro-interactions**: Elements should respond to hover states (e.g., `hover:scale-110`, `hover:-translate-y-1`) but must remain structurally rigid (brutalist).
- **Monochromatic Base**: The interface relies heavily on deep blacks (`#080810`), stark whites, and slate grays, allowing the accent colors to pop.

## 2. Color Palette & Theming

### Base Colors
- **Dark Mode Background**: Deep Black (`#080810` -> `--color-base` in `global.css`).
- **Light Mode Background**: Slate 50 (`#f8fafc`) with stark white components.

### Accent Colors (Tailwind Variables)
We use CSS variables mapped to Tailwind configuration (`primary` and `secondary`).
- **Dark Mode (Neon glowing effect)**:
  - `primary`: Electric Cyan (`#00F5FF`)
  - `secondary`: Neon Violet (`#9B5DE5`)
- **Light Mode (Deep contrast)**:
  - The accent colors strictly shift to `cyan-600` (`#0891b2`) and `purple-600` (`#9333ea`) in explicit graphical components (like the Logo and Favicon) to ensure WCAG accessibility and readability on white backgrounds.

## 3. Typography
- **Headings & Main Titles**: **Outfit** (`font-sans`). Used for bold, impactful statements (`font-black`, `font-bold`).
- **Technical Accents & Badges**: **JetBrains Mono** (`font-mono`). Used for small labels, navigation items, and tech-heavy information to reinforce the "engineering" aesthetic. Typically styled with `uppercase tracking-widest text-xs`.

## 4. Component Guidelines

### Buttons & Links
- Must be perfectly rectangular (`rounded-none`).
- Hover states should invert colors, shift borders, or apply a glowing shadow.
- *Example CTA*: `bg-slate-900 text-white hover:bg-primary transition-colors`.

### Cards (Services, Projects)
- **Borders**: 1px solid translucent borders (`border-slate-900/10 dark:border-white/10`).
- **Hover**: Slight background opacity shift or a reveal of a noise/grid texture.
- **Images**: Images inside cards must be optimized (`<Image />` from `astro:assets`) and should use subtle scale animations (`group-hover:scale-110`) coupled with opacity changes.

### Custom Cursor
- Replaces the default pointer for a premium feel.
- Dot and trailing glow effect.
- **Dark Mode**: Uses `dark:mix-blend-screen` with `dark:bg-primary` for a glowing neon effect.
- **Light Mode**: Uses `bg-slate-900` for stark visibility against light backgrounds.

## 5. Accessibility (a11y) & Performance
- **Contrast**: Ensure text passes WCAG contrast ratios. Pure cyan on white is strictly forbidden.
- **Screen Readers**: Icon-only links (like arrow buttons) MUST have descriptive `aria-label` tags mapped to translations.
- **Performance**: Always use `astro:assets` `<Image />` component with local images to leverage `sharp` for automatic WebP/AVIF generation. Never use raw large `<img>` tags.

## 6. Internationalization (i18n)
- **Rule**: Absolutely no hardcoded text in components.
- All strings must be extracted to `src/i18n/ui.ts` and rendered via the `t()` hook.
- Default routing is Spanish (`/`), with English mapped to (`/en`).
