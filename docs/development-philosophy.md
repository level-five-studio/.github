# Development Philosophy

Our engineering culture is built on a small set of strong convictions. This document explains what they are and how they show up day-to-day.

---

## Trunk-Based Development

We commit directly to `main` — no long-lived feature branches.  
New or risky work is hidden behind **feature flags** so it can ship without being visible to users.

- Feature flag providers: [PostHog](https://posthog.com/docs/feature-flags/creating-feature-flags) · [StatSig](https://docs.statsig.com/feature-flags/working-with)
- Read more: [Trunk-Based Development](https://trunkbaseddevelopment.com)

### When to open a Pull Request

PRs are for changes with a **large blast radius** — things that affect shared infrastructure, cross-cutting APIs, or the release pipeline.  
Everything else goes straight to `main` behind a toggle. Our CI acts as the quality gate.

---

## Code Comments

We treat comments as a first-class deliverable:

- **Top-level comments** on every module, component, and exported function explaining *what* it does and *why* it exists.
- **Inline comments** on any logic that isn't immediately obvious.

The bar is: *a new team member should be able to understand this file without asking anyone.*

---

## First-Class Developer Experience (DX)

If the toolchain is slow, painful, or inconsistent, quality suffers. We invest in:

- Fast feedback loops (Vite HMR, Vitest watch, Turborepo caching)
- Consistent formatting and linting enforced automatically (no debates, no drift)
- `Taskfile` / `Makefile` tasks for every common operation — one command to rule them all
- Scripts that fail loudly and early rather than silently producing bad output

See [Tooling & DX](tooling.md) for the full setup.

---

## Automation-First

If a process can be automated, it should be.  
Manual steps in a release or setup process are bugs — they will eventually be skipped or done wrong.

- All quality gates run in CI: lint, typecheck, test, build, size-limit
- Releases are fully automated — no human clicks "publish"
- Dependency updates are automated via [Dependabot](https://docs.github.com/en/code-security/dependabot)

---

## Test Coverage

| Layer | Tool | Target |
|---|---|---|
| Unit & Integration | Vitest | >75% coverage |
| End-to-End | Playwright | Critical user journeys |

Coverage is enforced in CI. A failing threshold blocks the merge or push.

---

## AI-Driven Development

We actively rely on AI assistance in every phase of development — from design to code to review.  
See [AI-Driven Development](ai-driven-development.md) for how we structure this.

---

> Next: [Tooling & DX →](tooling.md)
