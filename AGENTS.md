# Devitai Project

## Commands
- `pnpm install` - Install dependencies
- `pnpm dev` - Start dev server at http://localhost:4321
- `pnpm build` - Build production site to `./dist/`
- `pnpm preview` - Preview production build

## Architecture
- **Framework**: Astro 5 (static site generator)
- **Styling**: Tailwind CSS 4 (via @tailwindcss/vite)
- **Package manager**: pnpm
- **i18n**: Default locale is Spanish (`es`), also supports English (`en`). Routing uses prefixDefaultLocale: false, so `/` = Spanish, `/en` = English.

## Project Structure
- `src/pages/` - Route definitions (index.astro = `/`, en/index.astro = `/en`)
- `src/components/` - UI components (common/, sections/)
- `src/i18n/` - Translation utilities and dictionaries
- `src/layouts/` - Page layouts
- `astro.config.mjs` - Astro and i18n configuration

## Design System & UI
- **Strict Guidelines**: ALWAYS read `DESIGN.md` before creating or modifying any UI component.
- **Aesthetic**: Adhere strictly to the "Retro-futurist Brutalist" aesthetic described in the design file. Do not invent new colors, border radiuses (`rounded-none` only), or shadows.
- **Assets**: Use `astro:assets` and `sharp` for all images. No raw `<img src="url">` tags.

## Development Notes
- No linting or typechecking scripts defined in package.json
- Build output goes to `./dist/`
- Theme uses Outfit font for headers, JetBrains Mono for technical accents
- Uses @lucide/astro for icons

## AI Behavior Guidelines

**Tradeoff:** These guidelines bias toward caution over speed. For trivial tasks, use judgment.

### 1. Think Before Coding
**Don't assume. Don't hide confusion. Surface tradeoffs.**
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

### 2. Simplicity First
**Minimum code that solves the problem. Nothing speculative.**
- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.
Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

### 3. Surgical Changes
**Touch only what you must. Clean up only your own mess.**
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.
When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

### 4. Goal-Driven Execution
**Define success criteria. Loop until verified.**
Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

## Context7 Documentation Search
Use the `ctx7` CLI to fetch current documentation whenever asked about a library, framework, SDK, API, CLI tool, or cloud service (e.g. Astro, Tailwind). Use even when you think you know the answer -- your training data may not reflect recent changes.
1. Resolve library: `npx ctx7@latest library <name> "<user's question>"`
2. Pick the best match (ID format: `/org/project`).
3. Fetch docs: `npx ctx7@latest docs <libraryId> "<user's question>"`
4. Answer using the fetched documentation.