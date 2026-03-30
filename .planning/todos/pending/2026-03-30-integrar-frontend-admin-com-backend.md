---
created: 2026-03-30T00:29:17.454Z
title: Integrar frontend admin com backend
area: api
files:
  - frontend/src/pages/admin/AdminUsuarios.tsx
  - frontend/src/pages/admin/AdminDenuncias.tsx
  - frontend/src/pages/admin/AdminLogs.tsx
  - frontend/src/pages/admin/AdminConfiguracoes.tsx
  - frontend/src/contexts/AuthContext.tsx
  - frontend/src/pages/public/Login.tsx
---

## Problem

As telas admin e parte da autenticacao ainda usam dados mockados e estado local, sem integracao real com backend. Isso impede validacao de fluxo completo, persistencia de status e controle real de autorizacao.

## Solution

Criar uma camada de servicos HTTP tipados para auth, usuarios, denuncias, logs e configuracoes; substituir mocks por chamadas API; alinhar contratos de request/response; implementar tratamento de loading/erro e fallback visual por pagina.
