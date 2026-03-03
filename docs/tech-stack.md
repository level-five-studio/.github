# Tech Stack

This document gives a concise overview of every technology in our stack and why we chose it.  
Follow the links to go deeper on anything that's new to you.

---

## Language

| Technology | Role | Learn More |
|---|---|---|
| **TypeScript** | Primary language across all packages and apps | [TypeScript Docs](https://www.typescriptlang.org/docs/) |

We run TypeScript in strict mode. Type coverage is treated the same as test coverage — gaps are flagged in CI.

---

## Frontend

| Technology | Role | Learn More |
|---|---|---|
| **React** | UI library | [React Docs](https://react.dev) |
| **Base UI (`@base-ui/react`)** | Unstyled, accessible headless components | [Base UI Docs](https://base-ui.com) |
| **SCSS Modules** | Scoped component styles | [SCSS Docs](https://sass-lang.com/documentation) · [CSS Modules](https://github.com/css-modules/css-modules) |
| **React Router** | Routing for SPA, SSG, and SSR | [React Router Docs](https://reactrouter.com) |

---

## Data Fetching & State Management

| Technology | Role | Learn More |
|---|---|---|
| **TanStack Query** | Server-state, data fetching, caching | [TanStack Query Docs](https://tanstack.com/query) |
| **Zustand** | Lightweight global client-state | [Zustand Docs](https://zustand-demo.pmnd.rs) |
| **React Context** | Localised / shared UI state | [React Context Docs](https://react.dev/reference/react/createContext) |

Use TanStack Query for anything that comes from a server or API. Reach for Zustand when client state needs to be shared across distant parts of the tree. React Context for everything else (themes, locale, etc.).

---

## CMS

We use a **headless CMS** with content stored in Git and managed through GitHub. This keeps content versioned, reviewable, and deployable alongside code.

---

## Build & Test

| Technology | Role | Learn More |
|---|---|---|
| **Vite** | Dev server and bundler | [Vite Docs](https://vitejs.dev) |
| **Vitest** | Unit and integration testing | [Vitest Docs](https://vitest.dev) |
| **Playwright** | End-to-end testing | [Playwright Docs](https://playwright.dev) |

---

## Monorepo

| Technology | Role | Learn More |
|---|---|---|
| **Turborepo** | Task orchestration and caching across the monorepo | [Turborepo Docs](https://turbo.build/repo/docs) |
| **pnpm Workspaces** | Package management and workspace linking | [pnpm Workspaces](https://pnpm.io/workspaces) |

---

## Packages & Versioning

| Technology | Role | Learn More |
|---|---|---|
| **GitHub Packages** | Hosting private packages | [GitHub Packages Docs](https://docs.github.com/en/packages) |
| **npm** | Hosting public packages | [npm Docs](https://docs.npmjs.com) |
| **Changesets** | Changelog and version management | [Changesets Docs](https://github.com/changesets/changesets) |
| **Semantic Release** | Automated release publishing | [Semantic Release Docs](https://semantic-release.gitbook.io) |

---

> Next: [Development Philosophy →](development-philosophy.md)
