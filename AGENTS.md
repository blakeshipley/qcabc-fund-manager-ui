# Repo

Scaffold-ETH 2 UI for the QCABC fund manager: deposits, redemptions, portfolio tracking, and wallet connect. Yarn workspaces, Next.js, wagmi, viem, and RainbowKit. Merging can deploy the Vercel app. Companion contracts are in `qcabc-fund-manager`. More detail lives in `CLAUDE.md`.

# Commands

- Install: `yarn`
- Dev: `yarn start` or `yarn dev`
- Typecheck: `yarn next:check-types`
- Build: `yarn next:build`
- Lint: `yarn lint`

Do not run `yarn vercel` or `yarn vercel:yolo` unless Blake asked to deploy.

# Verify

`standard` (default when the change touches wallets, contracts, deposits, redemptions, or portfolio/oracle data): `yarn next:check-types` plus any existing checks for the touched area, and the diff matches the ask. Use `light` (`yarn next:check-types` only) for copy or layout-only work. Do not add tests.

# Ship mode

`ship_mode: pr`. Open a PR and wait for Blake. If Blake says "commit to main" or "ship it direct" for a task, the agent may commit to `main` once the verify command passes.

# Task sizing

Small is the default and needs no planning step. Large means multi-area features, schema or migrations, auth, payments or money, about 300 lines or more or about 8 files or more, or Blake saying "plan this". Large tasks get a plan split into small PRs.

# Don'ts

- No new tests, CI workflows, or dependencies unless asked.
- Do not read real `.env` files or print secrets or API keys. Agents never commit secrets.
- Do not merge or deploy without Blake's go-ahead.
- Keep monetary values at the correct decimal precision (USDC is 6).
- Do not weaken admin restrictions, staleness checks, or wallet/network requirements.

# Review

One pass, blockers only, at most 2 fix rounds. Do not nitpick small improvements or get stuck in a loop.
