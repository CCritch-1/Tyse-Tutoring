# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Artifacts

### Tyse Tutoring — Marketing Website
- **Location**: `artifacts/tyse-tutoring/`
- **Entry point**: `artifacts/tyse-tutoring/index.html` (single static HTML file)
- **Stack**: Vanilla HTML/CSS/JS only — no framework
- **Preview path**: `/` (root)
- **Served by**: Vite dev server
- **Purpose**: Single-page marketing website for Tyse Tutoring, Boulder CO

#### Design System (in `index.html`)
- **Fonts**: Playfair Display (headings), Inter (body) via Google Fonts
- **Colors**: Navy blue (`--color-primary`), gold (`--color-secondary`), teal accent (`--color-accent`), neutral grays
- **Breakpoints**: mobile-first, 768px (tablet), 1200px (desktop)
- **Spacing**: 4px base scale (`--space-1` through `--space-32`)
- **Border radii**: `--radius-sm` through `--radius-full`
- **Shadows**: `--shadow-xs` through `--shadow-2xl`
- **Typography classes**: `.heading-display`, `.heading-h1`–`.heading-h4`, `.body-lg`, `.body-base`, `.body-sm`, `.label-sm`
- **Button classes**: `.btn`, `.btn-primary`, `.btn-secondary`, `.btn-outline`, `.btn-outline-white`, `.btn-ghost`, `.btn-sm`, `.btn-lg`
- **Layout utilities**: `.container`, `.section`, `.flex`, `.grid`, etc.

#### Components
- **Navbar**: Sticky, scrolled shadow, desktop links + mobile hamburger dropdown
- **Footer**: 3-column grid (brand, quick links, contact) + copyright bar

#### Current State
Foundation only — navbar and footer visible, blank white `<main>` area between them ready for future content sections.

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
