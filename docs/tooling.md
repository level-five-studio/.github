# Tooling & DX

Strong tooling is a force multiplier. This page lists every tool in our standard setup and what it does.

---

## Package Management

| Tool | Purpose | Learn More |
|---|---|---|
| **pnpm** | Fast, disk-efficient package manager with workspace support | [pnpm Docs](https://pnpm.io) |
| **syncpack** | Keep dependency versions consistent across workspace packages | [syncpack Docs](https://github.com/JamieMason/syncpack) |
| **nvm** | Switch Node versions per project via `.nvmrc` | [nvm Docs](https://github.com/nvm-sh/nvm) |

---

## Code Quality

| Tool | Purpose | Learn More |
|---|---|---|
| **oxlint** | Ultra-fast JavaScript/TypeScript linter | [oxlint Docs](https://oxc.rs/docs/guide/usage/linter) |
| **Prettier** | Opinionated code formatter — no debates | [Prettier Docs](https://prettier.io/docs/en/index.html) |
| **TypeScript (strict)** | Type checking across the entire monorepo | [TS Strict Mode](https://www.typescriptlang.org/tsconfig#strict) |
| **knip** | Find unused exports, files, and dependencies | [knip Docs](https://knip.dev) |
| **size-limit** | Enforce bundle-size budgets in CI | [size-limit Docs](https://github.com/ai/size-limit) |

---

## Git Hooks & Commit Standards

| Tool | Purpose | Learn More |
|---|---|---|
| **lefthook** | Fast, cross-platform Git hooks runner | [lefthook Docs](https://github.com/evilmartians/lefthook) |
| **commitlint** | Enforce [Conventional Commits](https://www.conventionalcommits.org) on every commit | [commitlint Docs](https://commitlint.js.org) |

Hooks run `oxlint`, `prettier --check`, and `tsc --noEmit` before every commit. Pushes trigger the full CI pipeline.

---

## Task Runners

We use a **`Taskfile`** (or `Makefile` as fallback) at the monorepo root to standardise common operations:

```sh
task install       # install all dependencies
task dev           # start all dev servers
task build         # build all packages and apps
task test          # run all tests
task lint          # lint and typecheck
task clean         # clean all caches and build outputs
```

Learn more: [Task (Taskfile)](https://taskfile.dev) · [GNU Make](https://www.gnu.org/software/make/)

---

## Environment Variables

Every package that needs environment variables ships a `.env.example` file.  
Copy it to `.env.local` and fill in the values. `.env.local` is always git-ignored.

```sh
cp .env.example .env.local
```

---

> Next: [CI/CD & Automation →](ci-cd.md)
