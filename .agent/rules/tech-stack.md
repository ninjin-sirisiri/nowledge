# Technology Stack & Rules

## Core Stack

- **Framework**: SolidStart (Vinxi)
- **Runtime**: Bun
- **Database**: Neon (Postgres)
- **ORM**: Drizzle ORM
- **Auth**: Better Auth
- **UI**: Tailwind CSS (v4) + Shadcn Solid
- **Deployment**: Cloudflare Workers
- **Data Fetching**: TanStack Query + oRPC
- **State Management**: SolidJS Stores (Context API)

## Specific Rules

### Database

- Use **Drizzle ORM**.
- Push schema changes via `bun run drizzle-kit push`.

### Styling

- Use **Tailwind CSS v4**.
- Define combined styles in `src/app.css` or use utility classes.

### Authentication

- Use **Better Auth**.

### Environment Variables

- Setup `.env` with `DATABASE_URL`, `BETTER_AUTH_SECRET`, etc.

### Data Fetching & State Management

- **Primary Strategy**: **TanStack Query (A-Plan)**.
  - Use `createQuery` for client-side fetching, caching, and revalidation.
  - Use `oRPC` client as the `queryFn`.
- **SSR/Loading**:
  - **Render-as-Access**: Call data fetching hooks directly inside components.
  - Use `<Suspense>` to handle loading states.
- **Global/Feature State**:
  - Use **Fine-grained Stores** (SolidJS `createStore` + Context).
  - **Colocation**: Place stores in `src/features/<feature-name>/model`. Avoid a single global store unless necessary.
