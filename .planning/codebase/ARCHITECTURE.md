# Architecture Overview

## System Shape
- Architecture is a single-page application centered in `frontend/src/`.
- Composition pattern: app shell + nested routes + role-aware layout.
- Main execution entrypoint: `frontend/src/main.tsx`.

## Entry Flow
1. `frontend/index.html` loads root and applies theme class from `localStorage`.
2. `frontend/src/main.tsx` mounts React and wraps app with `AuthProvider`.
3. `frontend/src/App.tsx` renders router provider.
4. `frontend/src/routes/index.tsx` resolves route tree and page components.

## Route Layers
- Public layer:
  - `/` home page.
  - `/login`, `/registro` under auth layout.
- Protected layer:
  - Wrapped by `ProtectedRoute` and `MainLayout`.
  - Role-specific destinations in a single route tree.
- Admin area currently includes `/admin` and nav targets for future routes.

## State and Session Pattern
- Global auth state via React Context in `frontend/src/contexts/AuthContext.tsx`.
- Session source of truth is browser `localStorage` key `user`.
- Most page-level state is local `useState` with static mocks.

## UI Composition
- Shared layout shell in `frontend/src/layouts/MainLayout.tsx`.
- Feature pages in `frontend/src/pages/`.
- Public auth pages in `frontend/src/pages/public/`.
- New admin pages in `frontend/src/pages/admin/`.

## Data Flow
- UI events mutate local state directly inside each page component.
- Context state controls access and role navigation labels.
- No asynchronous remote calls currently in active code.

## Architectural Strengths
- Clear separation between route registration and page implementation.
- Consistent use of typed TSX components.
- Good basis for phased HTML-to-React migration.

## Architectural Gaps
- No service/data-access layer abstraction yet.
- No backend contract enforcement in the frontend code.
- Business logic remains embedded in UI components.
