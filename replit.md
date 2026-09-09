# MARSA — Saudi Marine Hospitality

MARSA is a premium bilingual Saudi Red Sea yacht provisioning and marine hospitality experience.

## Run & Operate

- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/marsa run dev` — run the Angular frontend
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- Required env: `DATABASE_URL` — Postgres connection string

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- API: Express 5
- DB: PostgreSQL + Drizzle ORM
- Validation: Zod (`zod/v4`), `drizzle-zod`
- API codegen: Orval (from OpenAPI spec)
- Build: Angular 20 application builder

## Where things live

- Frontend: `artifacts/marsa/src/`
- Content model and bilingual copy: `artifacts/marsa/src/app/data/content.ts`
- Theme and layout tokens: `artifacts/marsa/src/styles.css`
- Local visual assets: `artifacts/marsa/public/assets/`
- App routes: `artifacts/marsa/src/app/app.routes.ts`

## Architecture decisions

- Angular standalone components are used so the frontend stays modular without a heavyweight state layer.
- Language and theme preferences live in one service and persist through browser refreshes.
- The first release is intentionally frontend-only; request submission is represented as a polished local interaction until backend contracts are defined.

## Product

Visitors can explore MARSA services, provisioning steps, onboard products, Saudi Red Sea destinations, marina support, and submit a provisioning request in English or Arabic. The interface also supports RTL layout, mobile navigation, reduced motion, and light/dark themes.

## User preferences

_Populate as you build — explicit user instructions worth remembering across sessions._

## Gotchas

_Populate as you build — sharp edges, "always run X before Y" rules._

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details
