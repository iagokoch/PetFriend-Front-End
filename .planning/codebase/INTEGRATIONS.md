# Integrations Map

## External Services in Use

### Browser Storage
- `localStorage` is used for:
  - Theme persistence (`frontend/src/pages/Home.tsx`, `frontend/index.html` bootstrap script).
  - Auth user persistence (`frontend/src/contexts/AuthContext.tsx`).
- Risk: no schema/versioning for stored values.

### External Asset Hosts
- Unsplash image URLs across multiple pages:
  - `frontend/src/pages/Home.tsx`
  - `frontend/src/pages/MeusPets.tsx`
  - `frontend/src/pages/EncontrarCuidadores.tsx`
  - `frontend/src/pages/Agendamento.tsx`
- Pravatar image URLs across dashboard/profile views:
  - `frontend/src/layouts/MainLayout.tsx`
  - `frontend/src/pages/DashboardDono.tsx`
  - `frontend/src/pages/PerfilCuidador.tsx`
  - `frontend/src/pages/admin/DashboardAdmin.tsx`

### Font and Icon CDNs
- Google Fonts and Material Icons via `<link>` in `frontend/index.html`.
- Dependencies on external network availability for icon/font rendering.

## Integrations Not Yet Implemented
- No REST API client detected (`fetch`/`axios` absent in `frontend/src/**`).
- No database integration in the current codebase.
- No OAuth providers (Google/Facebook buttons are UI-only in `frontend/src/pages/public/Login.tsx`).
- No payment provider SDK integration.
- No analytics/telemetry SDK detected.

## Auth Boundary
- Route protection is local and client-side only:
  - `frontend/src/components/ProtectedRoute.tsx` checks auth from context.
  - `frontend/src/contexts/AuthContext.tsx` stores session in `localStorage`.
- No token validation or server-side session verification.

## Webhooks and Async Messaging
- No webhook endpoints present.
- No message queue or event bus integration found.

## Env Configuration
- No use of `import.meta.env` or runtime secrets in `frontend/src/**`.
- No environment-specific integration wiring detected.

## Integration Readiness Summary
- Current stage: prototype-to-MVP frontend integration readiness.
- Next integration milestone: add a typed API layer and replace mock auth/data flows.
