# Repository Structure

## Top-Level Layout
- `README.md`: project vision, RF/RNF and intended full-stack plan.
- `docs/`: supplemental project docs (`TAREFAS.md`, `WIKI.md`).
- `frontend/`: active React + TypeScript + Vite app.
- `frontend-esboco/`: HTML prototype reference pages and assets.
- `.github/`: Copilot and GSD workflow assets.

## Frontend App Layout (`frontend/`)
- `index.html`: root shell and theme bootstrap script.
- `package.json`: scripts and dependencies.
- `src/main.tsx`: app bootstrap.
- `src/App.tsx`: router mount.
- `src/index.css`: Tailwind v4 theme tokens and dark variant.

## Frontend Domain Folders
- `src/routes/`: route tree and page registration.
- `src/layouts/`: `AuthLayout`, `MainLayout` wrappers.
- `src/contexts/`: auth context and user session handling.
- `src/components/`: reusable route guards and layout/ui pieces.
- `src/pages/`: feature screens by actor flow.
- `src/pages/public/`: public auth screens (`Login`, `Registro`).
- `src/pages/admin/`: admin migration target (currently includes dashboard).

## Prototype Layout (`frontend-esboco/`)
- `assets/css`, `assets/js`, `assets/images`, `assets/icons`.
- `pages/`: static source of truth for migration.
- `pages/admin/`: static admin pages to be ported.

## Naming and Organization Patterns
- Page files use PascalCase (`DashboardDono.tsx`, `MinhaAgenda.tsx`).
- Role-specific URL namespace appears in route paths (`/dashboard/cuidador`, `/admin`).
- Public page namespace uses folder segmentation (`pages/public`).

## Structural Observations
- Migration status is mixed: many user/caregiver pages exist in React, admin subset still incomplete.
- Backend folder described in README is absent in current workspace.
- Repository acts as product workspace containing implementation plus prototype.
