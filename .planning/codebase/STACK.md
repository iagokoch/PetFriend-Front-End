# Codebase Stack

## Overview
- Current implementation is a frontend-first monorepo with two main folders: `frontend/` (React app) and `frontend-esboco/` (static HTML prototypes).
- No runtime backend source is present in this workspace despite backend references in documentation.
- Main executable app is in `frontend/`.

## Languages
- TypeScript: primary app language in `frontend/src/**/*.tsx` and `frontend/src/**/*.ts`.
- CSS: Tailwind v4 via `frontend/src/index.css`.
- HTML: Vite host page in `frontend/index.html` and static prototypes in `frontend-esboco/pages/**/*.html`.
- JavaScript config files: `frontend/eslint.config.js`, `frontend/vite.config.ts`.

## Runtime and Build
- Node.js runtime expected (README references Node 18+).
- Vite 7 used for dev server and production build (`frontend/package.json` scripts).
- TypeScript project references enabled (`frontend/tsconfig.json`).

## Frameworks and Core Libraries
- React 19 (`react`, `react-dom`) from `frontend/package.json`.
- Router: `react-router-dom` used in `frontend/src/routes/index.tsx`.
- Styling: `tailwindcss` + `@tailwindcss/vite` from `frontend/package.json`.
- No state management framework (Redux/Zustand) detected.

## Tooling
- Linting: ESLint 9 flat config in `frontend/eslint.config.js`.
- Type checking: strict TS settings in `frontend/tsconfig.app.json`.
- Compiler plugin: SWC-based React plugin via `@vitejs/plugin-react-swc`.
- Package manager: npm implied by scripts and lockfile conventions.

## Execution Commands
- Dev: `npm run dev` in `frontend/`.
- Build: `npm run build` in `frontend/`.
- Lint: `npm run lint` in `frontend/`.
- Preview: `npm run preview` in `frontend/`.

## Configuration Files
- `frontend/package.json`
- `frontend/vite.config.ts`
- `frontend/tsconfig.json`
- `frontend/tsconfig.app.json`
- `frontend/eslint.config.js`
- `frontend/src/index.css`

## Current Stack Maturity
- UI and navigation are active and compile successfully.
- Admin feature migration is in progress (new `frontend/src/pages/admin/DashboardAdmin.tsx`).
- Data layer is still mock-driven and local state based.
