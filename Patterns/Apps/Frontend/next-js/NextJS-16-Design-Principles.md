# Next.js 16 Design Principles & Architecture Standards

This document outlines the core architectural principles, recommended conventions, and design patterns for building web applications using Next.js 16. It serves as the authoritative guide for frontend development within the eSynergy ecosystem.

## 1. Core Architecture: The App Router

Next.js 16 heavily relies on the App Router (`app/` directory). All new development **must** use the App Router. The `pages/` directory is deprecated for new features.

### 1.1 Server Components by Default (RSC)
- **Principle**: Default to React Server Components (RSC).
- **Why**: RSCs reduce the client-side JavaScript bundle size, improve initial page load (FCP, LCP), and allow direct access to backend resources securely.
- **Rule**: Only use `'use client'` when interactivity (hooks like `useState`, `useEffect`, `useRouter`) or browser APIs (like `window`) are strictly required.
- **Pattern**: Keep Client Components as leaf nodes in the component tree. Pass data down from Server Components to Client Components as props.

### 1.2 Data Fetching & Mutations
- **Fetching**: Perform data fetching in Server Components. Avoid `useEffect` for data fetching.
- **Mutations**: Use **Server Actions** (`'use server'`) for all form submissions and data mutations. This ensures secure execution on the server and progressive enhancement.
- **API Routes**: Use Route Handlers (`app/api/route.ts`) only when you need to expose a public API or integrate with external webhooks. For internal app logic, prefer Server Actions.

## 2. Directory Structure & Layering

A strict separation of concerns must be maintained to ensure the codebase remains scalable and testable.

```text
src/
├── app/                  # App Router entry points (pages, layouts, loading, errors)
├── components/           # Reusable React components
│   ├── ui/               # Atomic UI primitives (e.g., Shadcn/Radix components)
│   └── [feature]/        # Domain-specific components grouped by feature
├── actions/              # Server Actions (mutations)
├── hooks/                # Custom React hooks (client-side logic)
├── services/             # API clients to interact with external/backend services
├── lib/                  # Shared utilities, fetch wrappers, configuration
└── types/                # TypeScript interfaces and Zod schemas
```

### 2.1 Component Architecture constraints
- **`app/` (Pages/Layouts)**: Responsible only for routing, reading URL parameters/search parameters, initiating data fetches, and composing UI feature components.
- **`services/`**: Pure TypeScript functions. Unaware of React. Responsible for making HTTP requests to external APIs and throwing typed errors.
- **`actions/`**: The glue between the UI and `services/`. Responsible for Zod validation, calling services, and triggering Next.js cache revalidation (`revalidatePath`, `revalidateTag`).

## 3. Caching & Performance (Next.js 16 Specifics)

Next.js 16 fundamentally changes how caching is managed, introducing Cache Components and the `'use cache'` directive to replace older experimental PPR flags and `unstable_cache`.

### 3.1 Enabling Cache Components
Ensure `cacheComponents: true` is set in `next.config.ts`.

### 3.2 The `'use cache'` Directive
Use the `'use cache'` directive at the file, component, or function level to cache expensive operations or data fetches that do not need to be calculated on every request.

```typescript
// Example: Function level caching
export async function getDashboardStats() {
  'use cache'
  cacheLife('hours') // Pre-defined profile or custom object: { revalidate: 3600 }
  cacheTag('dashboard-stats')
  
  return fetch('/api/stats').then(res => res.json())
}
```

### 3.3 Dynamic vs. Cached Data
- **Static**: Synchronous code, pure computations. Prerendered instantly at build.
- **Cached (`'use cache'`)**: Async data that can be stale. Use `cacheLife` to define TTL and `cacheTag` for invalidation.
- **Dynamic (Suspense)**: Data that must be fresh per request (e.g., user-specific data reading cookies).

**Rule**: Wrap dynamic data components in `<Suspense fallback={<Skeleton />}>` so they stream in without blocking the static or cached shell (Partial Prerendering).

### 3.4 Runtime Constraint for Caching
You **cannot** access dynamic request information (like `cookies()`, `headers()`, or `searchParams`) inside a `'use cache'` boundary.
If a cached component depends on user state, extract the cookie *outside* the cache boundary and pass it as an argument:

```typescript
// Correct Pattern
async function UserProfile() {
  const sessionId = (await cookies()).get('session')?.value
  return <CachedAvatar sessionId={sessionId} />
}

async function CachedAvatar({ sessionId }: { sessionId: string }) {
  'use cache'
  // sessionId automatically becomes part of the cache key
  const user = await fetchUser(sessionId)
  return <img src={user.avatar} />
}
```

## 4. UI Aesthetics & Design System
- **Styling**: Use Vanilla CSS or modern CSS-in-JS solutions tailored to the project requirements. If Tailwind CSS is used, ensure semantic class naming and consistent utility usage.
- **Visual Excellence**: prioritize modern aesthetics:
  - Utilize curated, harmonious color palettes (avoid generic primary colors).
  - Implement smooth micro-animations for interactive elements (hover states, modal transitions).
  - Use high-quality typography (e.g., Inter, Roboto).
  - Ensure interfaces feel responsive and premium.

## 5. Error Handling & Validation
- **Runtime Validation**: Use Zod for validating all incoming data (form arguments in Server Actions and API responses in Services).
- **Error Boundaries**: Implement `error.tsx` at the layout level to gracefully catch and display unexpected rendering or data fetching errors without crashing the entire app.
- **Not Found**: Use `notFound()` when a resource doesn't exist to trigger the nearest `not-found.tsx` boundary.

## 6. Migration & Upgrades
When upgrading (e.g., from v14/15 to v16), always utilize the official Next.js codemods (e.g., `npx @next/codemod@latest`) to automate the transition of breaking changes (like the async nature of `params`, `searchParams`, `cookies`, and `headers` introduced in v15).
