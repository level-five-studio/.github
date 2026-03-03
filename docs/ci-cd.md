# CI/CD & Automation

All quality gates, deployments, and releases run automatically via **GitHub Actions**.  
No one clicks "deploy" or "publish" manually.

---

## Pipeline Overview

Every push to `main` triggers the following staged pipeline:

```
push to main
  └─ 1. validate       (lint · typecheck · commitlint)
  └─ 2. test           (Vitest unit/integration · coverage threshold)
  └─ 3. build          (Turborepo build · size-limit check)
  └─ 4. e2e            (Playwright on built artefacts)
  └─ 5. release gate   (Changesets / Semantic Release — only on passing pipeline)
  └─ 6. deploy         (environment-specific deployment workflows)
```

Stages run in order. A failure at any stage blocks everything downstream.

---

## Workflows

| Workflow | Trigger | What It Does |
|---|---|---|
| `ci.yml` | push / PR to `main` | Lint, typecheck, test, build |
| `e2e.yml` | after `ci.yml` passes | Playwright E2E suite |
| `release.yml` | after `e2e.yml` passes on `main` | Versioning, changelog, npm publish |
| `dependabot-auto-merge.yml` | Dependabot PR | Auto-merge minor/patch dependency updates |
| `org-automation.yml` | schedule / webhooks | Org-wide housekeeping (stale issues, label sync, etc.) |

Learn more: [GitHub Actions Docs](https://docs.github.com/en/actions)

---

## Dependency Updates

[Dependabot](https://docs.github.com/en/code-security/dependabot) monitors all `package.json` files and opens PRs for outdated dependencies.  
Minor and patch updates are auto-merged once CI passes. Major updates require a human review.

---

## Release Flow

1. Developers include a **changeset file** (`pnpm changeset`) alongside code changes.
2. On merge to `main`, the release workflow collects all pending changesets, bumps versions, updates `CHANGELOG.md` files, and publishes packages.
3. Packages are published to **GitHub Packages** (private) and/or **npm** (public) depending on the package config.

Learn more: [Changesets](https://github.com/changesets/changesets) · [Semantic Release](https://semantic-release.gitbook.io)

---

## Organisation Automation

We use GitHub Actions to automate org-level maintenance:

- Label synchronisation across repositories
- Stale issue / PR management
- Repository settings enforcement
- Onboarding automations for new repositories

---

> Next: [AI-Driven Development →](ai-driven-development.md)
