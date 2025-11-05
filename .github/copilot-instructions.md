# Copilot Instructions for Portfolio

## Project Overview

This is an Astro-based portfolio site using Tailwind CSS v4 (via Vite plugin). The project follows a minimal architecture optimized for static site generation.

## Tech Stack

- **Framework**: Astro v5.15+ (SSG mode, no framework integrations)
- **Styling**: Tailwind CSS v3.4+ with `@astrojs/tailwind` integration
- **TypeScript**: Strict mode enabled via `astro/tsconfigs/strict`

## Architecture Patterns

### Styling Setup
- Tailwind CSS v3 integrated via `@astrojs/tailwind` (Astro's official adapter)
- Configuration in `tailwind.config.mjs` for content paths and customization
- Global styles use standard Tailwind directives in `src/styles/global.css`:
  ```css
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ```
- Tailwind styles are automatically injected by the integration (no manual import needed)
- Use standard Tailwind v3 syntax: `class="text-blue-600 font-bold"`

### Page Structure
- Pages in `src/pages/` use file-based routing
- Each `.astro` file must include full HTML structure (`<html>`, `<head>`, `<body>`)
- Standard meta tags: charset utf-8, viewport, generator (`Astro.generator`)
- Tailwind styles automatically injected by `@astrojs/tailwind` integration

### Component Organization
- No `src/components/` directory exists yet
- When adding components, place reusable Astro components in `src/components/`
- Static assets go in `public/` directory (no `/public` prefix in URLs)

## Development Workflow

```powershell
npm run dev      # Dev server at localhost:4321
npm run build    # Build to ./dist/
npm run preview  # Preview production build locally
```

## Code Conventions

- Use TypeScript strict mode (inherited from Astro strict config)
- Astro component scripts use frontmatter (`---` blocks)
- Prefer Astro's built-in features over external frameworks
- Keep portfolio site static (no SSR unless explicitly needed)

## Key Files

- `astro.config.mjs` - Astro configuration with Tailwind integration
- `tailwind.config.mjs` - Tailwind CSS configuration (content paths, theme, plugins)
- `src/pages/index.astro` - Homepage entry point
- `src/styles/global.css` - Tailwind CSS directives
