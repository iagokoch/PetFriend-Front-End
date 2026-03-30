# Concerns and Risk Map

## High Priority Concerns

### 1) Backend mismatch with docs

- `README.md` describes a full-stack architecture with backend and database.
- Workspace currently lacks a `backend/` implementation folder.
- Risk: planning assumptions may diverge from current executable reality.

### 2) Auth is client-side simulation

- `frontend/src/pages/public/Login.tsx` has TODO for real API.
- `frontend/src/contexts/AuthContext.tsx` stores user role directly in browser storage.
- Risk: role spoofing in local state and no true authorization boundary.

### 3) Admin route completeness gap

- Navigation includes `/admin/usuarios`, `/admin/denuncias`, `/admin/logs`, `/admin/configuracoes`.
- Only `/admin` page is currently wired in router.
- Risk: broken admin navigation and perceived incomplete feature surface.

## Medium Priority Concerns

### 4) Data layer is absent

- No API client or service abstraction in `frontend/src/**`.
- Feature pages contain local mock arrays and local state transitions.
- Risk: migration to real backend can require broad refactors across many pages.

### 5) External image/font dependency

- Heavy use of external image URLs and Google font/icon CDNs.
- Risk: degraded UI in restricted/offline networks, rate-limits, and privacy constraints.

### 6) Testing coverage gap

- No automated tests detected in repository.
- Risk: regressions during iterative migration and role-based routing changes.

## Low Priority Concerns

### 7) Prototype drift

- `frontend-esboco/` and React implementation can diverge as migration continues.
- Risk: design inconsistencies and uncertainty about source of truth.

### 8) Copy and localization consistency

- Mixed language and occasional inconsistent labels in prototype-derived content.
- Risk: UX quality debt and additional cleanup cycles later.

## Recommended Near-Term Mitigations

1. Finish admin route/page wiring before new feature expansion.
2. Introduce minimal API service layer contract (even mocked) to decouple UI.
3. Add baseline tests for auth context and protected routes.
4. Define authoritative source for UI during migration (React vs static templates).
