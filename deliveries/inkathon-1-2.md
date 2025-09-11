# Milestone Delivery :mailbox:

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/use-inkubator/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**

**Application Document:** https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/inkathon.md

## Context

We're happy to finally deliver a complete rewrite of the [inkathon Boilerplate](https://inkathon.xyz/) now supporting ink! v6 and much more as it includes:

1. 🦑 A new **starterkit application**: https://inkathon.xyz
2. 📚 A new **standalone documentation**: https://docs.inkathon.xyz
3. ⚙️ A new **`create-inkathon-app`*** setup command: https://docs.inkathon.xyz/

New inkathon features:

- **Full ink! v6 support** with PolkaVM compatibility
- **Type-safe contract interactions** via PAPI
- **Modern stack**: Bun, Next.js 15, React 19, Tailwind CSS v4
- **Improved DX**: Better build- & deployment automation and contract management using Pop CLI
- **Production-ready**: Docker support, self-hosting optimized
- **New `create-inkathon-app` CLI** for setting up the boilerplate in seconds

### Note

\*The CLI **was not** part of the final application, but was included in our [first draft](https://github.com/scio-labs/inkubator-application/blob/2e5a4e6b5ba1e43b596b6401018c712580e28617/applications/inkathon.md#milestone-2-new-cli--alternative-client) which exceeded the available project budget. Nonetheless, we've decided to **build it proactively without compensation**, as it makes the setup experience 10x better and gets everyone started in seconds!

Also, after examining how to best approach the ink! v6-compatible rebuild, we came to the conclusion to discontinue `useInkathon` in favor of PAPI and ReactiveDOT. This is why the scope of Milestone 1 has slightly changed and now includes the new CLI and other adjustments that have a higher impact for inkathon compared to updating dependencies in a deprecated library. If required, we're still open to submit those, but we would rather use that time to further improve the boilerplate, documentation, and CLI with upcoming community feedback.

## Deliverables

### Milestone 1

| Number | Deliverable                      | Link                                                                                                                                                                                                                                                                    | Notes                                                                                                                         |
| -----: | -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
|     1. | Latest polkadot.js compatibility | https://github.com/scio-labs/inkathon/blob/0313066efa18c5b8bb8f193fe25b44b12670cf33/frontend/package.json#L37                                                                                                                                                           | Supports latest `polkadot-api` in favor of `polkadot.js`                                                                      |
|     2. | Improve AI-driven DX             | https://github.com/scio-labs/inkathon/blob/main/CLAUDE.md, https://github.com/scio-labs/inkathon/tree/main/.cursor/rules                                                                                                                                                | Added `CLAUDE.md` and `.cursor` rules                                                                                         |
|     3. | Switch to Bun                    | https://github.com/scio-labs/inkathon/blob/main/package.json, https://docs.inkathon.xyz/resources/commands                                                                                                                                                              | Everything is Bun-native now (the CLI even ensures that)                                                                      |
|     4. | Biome.js Linting & Formatting    | https://github.com/scio-labs/inkathon/blob/main/biome.json, https://docs.inkathon.xyz/resources/commands                                                                                                                                                                | Biome.js is the new default linter which falls back to Prettier if necessary                                                  |
|     5. | Support new Networks             | https://docs.inkathon.xyz/guides/add-network, https://github.com/scio-labs/inkathon/blob/main/frontend/src/lib/reactive-dot/config.ts                                                                                                                                   | Supports arbitrary networks now and even added a guide on it                                                                  |
|     6. | Integrate Pop CLI                | https://docs.inkathon.xyz/guides/contract-development, https://docs.inkathon.xyz/guides/add-contract                                                                                                                                                                    | Pop CLI is the recommended tool for setting up your environment and managing contracts.                                       |
|     7. | Tailwind CSS & shadcn/ui v4      | https://github.com/scio-labs/inkathon/blob/main/frontend/src/styles/globals.css, https://github.com/scio-labs/inkathon/tree/main/frontend/src/components, https://github.com/scio-labs/inkathon/blob/0313066efa18c5b8bb8f193fe25b44b12670cf33/frontend/package.json#L49 | Migrated configuration and upgraded each component                                                                            |
|     8. | Next.js v15                      | https://github.com/scio-labs/inkathon/blob/0313066efa18c5b8bb8f193fe25b44b12670cf33/frontend/package.json#L35                                                                                                                                                           | Upgraded Next.js, React, and all other dependencies. Also added an interactive update command.                                |
|     9. | New Dockerfile                   | https://github.com/scio-labs/inkathon/blob/main/Dockerfile, https://docs.inkathon.xyz/learn/hosting                                                                                                                                                                     | New improved Dockerfile, New hosting documentation, New self-hosted demo under [inkathon.scio.xyz](https://inkathon.scio.xyz) |
|    10. | New Connection Button            | https://github.com/scio-labs/inkathon/blob/main/frontend/src/components/web3/connect-button.tsx                                                                                                                                                                         | New multi-chain and multi-account connection button example even with "auto mapping" (for unmapped accounts).                 |
|    11. | Support custom Networks          | https://docs.inkathon.xyz/guides/add-network                                                                                                                                                                                                                            | Supports arbitrary networks now and even added a guide on it                                                                  |
|  Extra | New `create-inkathon-app` CLI    | https://www.npmjs.com/package/create-inkathon-app, https://github.com/scio-labs/inkathon/tree/main/create-inkathon-app                                                                                                                                                  | New `create-inkathon-app` command to scaffold ink!athon projects in seconds (Try it via `npx create-inkathon-app@latest`)     |

### Milestone 2

| Number | Deliverable                  | Link                                                                                                                                                                         | Notes                                                                                                           |
| -----: | ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
|     1. | ink! v6                      | https://inkathon.xyz, https://github.com/scio-labs/inkathon/tree/main/frontend, https://github.com/scio-labs/inkathon/tree/main/contracts                                    | Everything supports ink! `v6.0.0-alpha.1` and we're committed to ensuring compatibility with v6 stable as well  |
|     2. | ink! v6 example              | https://github.com/scio-labs/inkathon/blob/main/contracts/src/flipper/lib.rs, https://github.com/scio-labs/inkathon/blob/main/frontend/src/components/web3/contract-card.tsx | Updated example contracts and frontend contract interaction to v6                                               |
|     3. | New Standalone Documentation | https://docs.inkathon.xyz/                                                                                                                                                   | New Standalone Documentation with Quickstart, Learn Section, Step-by-Step Guides, Command Cheat Sheet, and more |
|  Extra | Demo App Redesigned          | https://inkathon.xyz/, https://github.com/scio-labs/inkathon/tree/main/frontend/src/components                                                                               | Redesigned and refactored all Demo App Components to be more modern and user-friendly.                          |
