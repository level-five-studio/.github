# Day 1 Bootstrap

Follow these steps in order to go from zero to a running local monorepo.

---

## Prerequisites

Make sure you have the following installed before you begin:

- [Git](https://git-scm.com)
- [nvm](https://github.com/nvm-sh/nvm#installing-and-updating) (Node Version Manager)
- [pnpm](https://pnpm.io/installation)

---

## Step-by-Step

### 1. Clone the monorepo

```sh
git clone git@github.com:level-five-studio/<repo-name>.git
cd <repo-name>
```

### 2. Switch to the correct Node version

The repo ships an `.nvmrc` file that pins the exact Node version.

```sh
nvm use
# If the version isn't installed yet:
nvm install
```

### 3. Enable pnpm (if using corepack)

```sh
corepack enable
```

### 4. Install all dependencies

```sh
pnpm install
```

Turborepo caches build artefacts — subsequent installs and builds will be significantly faster.

### 5. Set up environment variables

Each app/package that needs env vars ships a `.env.example` file. Copy and fill in the values:

```sh
# Repeat for each app/package that has an .env.example
cp apps/web/.env.example apps/web/.env.local
```

Ask a team member in **WhatsApp → General** for the secret values — never commit them.

### 6. Start the development server

```sh
pnpm dev
# or, using the Taskfile:
task dev
```

This uses Turborepo to start all apps and packages in watch mode simultaneously.

---

## Useful Commands

| Command | Description |
|---|---|
| `pnpm dev` | Start all dev servers |
| `pnpm build` | Build all packages and apps |
| `pnpm test` | Run all unit and integration tests |
| `pnpm lint` | Lint and typecheck everything |
| `pnpm test:e2e` | Run Playwright E2E tests |
| `pnpm changeset` | Create a changeset for your current work |
| `task clean` | Remove all caches and build outputs |

---

## Verify Your Setup

Once `pnpm dev` is running:

1. Open the URL printed in the terminal (usually `http://localhost:5173`).
2. You should see the app running locally.
3. Make a small change to a component — Vite HMR should hot-reload instantly.

If something isn't working, check the **#general** WhatsApp group or open a GitHub issue.

---

> You're set up! Start with [Development Philosophy](development-philosophy.md) to understand how we work day-to-day.
