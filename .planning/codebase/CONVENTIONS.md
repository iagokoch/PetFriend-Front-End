# Code Conventions

## Language and Typing
- TypeScript is used across app source (`frontend/src/**`).
- Strict mode is enabled in `frontend/tsconfig.app.json`.
- Common pattern: explicit type aliases/interfaces for structured UI data.

## Component Style
- Functional React components only (no class components found).
- Hooks usage pattern:
  - Local state with `useState` in pages/layouts.
  - Side effects with `useEffect` where needed (theme handling in home).
- Props are typed inline or through local interfaces.

## Routing and Access Control
- Routing centralization in `frontend/src/routes/index.tsx`.
- Protected route pattern:
  - `ProtectedRoute` returns redirect to `/login` when unauthenticated.
  - Main app pages are nested under a common layout shell.

## State Conventions
- Global session state via context (`AuthContext`).
- Persistent state through `localStorage` keys (`user`, `theme`).
- No shared reducer/store abstractions currently.

## Styling Conventions
- Utility-first styling with Tailwind classes in JSX.
- Theme token definitions in `frontend/src/index.css` using Tailwind v4 directives.
- Material Icons are used through class names (`material-icons`, `material-icons-round`).

## Linting and Quality Rules
- ESLint flat config in `frontend/eslint.config.js`.
- Base rule sets: JS recommended + TypeScript recommended + React hooks + react-refresh.
- Dist output ignored by lint (`globalIgnores(['dist'])`).

## Current Coding Signals
- TODO markers exist in auth pages for real API hookup:
  - `frontend/src/pages/public/Login.tsx`
  - `frontend/src/pages/public/Registro.tsx`
- Mock datasets are used heavily for dashboard and listing pages.
- Code tends to keep concerns close to page components for speed of iteration.
