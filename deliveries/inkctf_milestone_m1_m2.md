# Milestone Delivery :mailbox:

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/use-inkubator/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**

* **Application Document:** https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/InkCtf.md
* **Milestone Number:** 1 & 2 (Combined Delivery)

---

## Context

This delivery combines Milestone 1 (On-Chain Foundation) and Milestone 2 (Frontend Integration) into a single submission. The platform is now fully functional and deployed at [ctfs.ink](https://ctfs.ink).

### Strategic Architecture Change

We made a significant strategic decision to pivot from the originally proposed **centralized backend architecture** (Node.js/Express + PostgreSQL) to a **fully decentralized on-chain architecture**. This change delivers substantial benefits:

| Original Plan | What We Built | Benefit |
|---------------|---------------|---------|
| Backend server + PostgreSQL | Smart contracts as backend | Zero server maintenance costs |
| Session-based authentication | Wallet-native authentication | True Web3 experience |
| Server validates exploits | Cryptographic on-chain verification | Impossible to cheat |
| Centralized progress storage | On-chain Statistics contract | Immutable achievement records |

### Platform Overview

ink!Spector Gadget is an Ethernaut-inspired CTF platform where players exploit vulnerable ink! smart contracts to learn about security vulnerabilities. Each player receives their own unique contract instance deployed on-chain, ensuring a fair and verifiable learning experience.

**Live Demo:** [ctfs.ink](https://ctfs.ink)

---

## Milestone 1 Deliverables - On-Chain Foundation

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 0a. | License | [MIT License](https://github.com/Gmin2/InkCtf/blob/main/LICENSE) | MIT License applied to repository |
| 0b. | Documentation | [README.md](https://github.com/Gmin2/InkCtf/blob/main/README.md) | Deployment guide with step-by-step instructions, contract architecture documentation |
| 0c. | Testing Guide |  |
| 0d. | Docker | Deferred to M3 | Not required for on-chain architecture - contracts are deployed to Paseo testnet |
| 1. | Smart Contract Architecture | [lib.rs (Coordinator)](https://github.com/Gmin2/InkCtf/blob/main/lib.rs), [traits/lib.rs](https://github.com/Gmin2/InkCtf/blob/main/traits/lib.rs) | InkSpector coordinator with trait-based Level interface enabling polymorphic cross-contract calls |
| 2. | Level Contracts (All 6) | [instance/](https://github.com/Gmin2/InkCtf/tree/main/instance), [fallback/](https://github.com/Gmin2/InkCtf/tree/main/fallback), [reentrance/](https://github.com/Gmin2/InkCtf/tree/main/reentrance), [coinflip/](https://github.com/Gmin2/InkCtf/tree/main/coinflip), [king/](https://github.com/Gmin2/InkCtf/tree/main/king), [vault/](https://github.com/Gmin2/InkCtf/tree/main/vault) | Complete implementation of all 6 vulnerable contracts teaching different security concepts |
| 3. | Factory Contracts (All 6) | [instance/factory/](https://github.com/Gmin2/InkCtf/tree/main/instance/factory), [fallback/factory/](https://github.com/Gmin2/InkCtf/tree/main/fallback/factory), etc. | Factory pattern - each deploys unique instances per player and validates exploit completion |
| 4. | Statistics Contract | [statistics/lib.rs](https://github.com/Gmin2/InkCtf/blob/main/statistics/lib.rs) | On-chain progress tracking: registered levels, player instances, success/failure counts |
| 5. | Testnet Deployment | [README.md](https://github.com/Gmin2/InkCtf/blob/main/README.md) | All contracts deployed to Paseo Asset Hub with documented addresses |

---

## Milestone 2 Deliverables - Frontend Integration & Interactive Gameplay

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 1. | Wallet Integration | [polkadot-provider.tsx](https://github.com/Gmin2/InkCtf/blob/main/app/src/lib/polkadot-provider.tsx) | Polkadot.js extension integration for wallet connection, account selection, transaction signing via Talisman/SubWallet/Polkadot.js |
| 2. | Contract Interaction Layer | [useInkCTF.ts](https://github.com/Gmin2/InkCtf/blob/main/app/src/hooks/useInkCTF.ts), [chain-config.ts](https://github.com/Gmin2/InkCtf/blob/main/app/src/lib/chain-config.ts) | TypeScript service layer for calling factory contracts: `createLevelInstance()`, `submitLevelInstance()`, `callContract()` |
| 3. | Level Instance Creation UI | [ActionPanel.tsx](https://github.com/Gmin2/InkCtf/blob/main/app/src/components/ActionPanel.tsx) | "Get Instance" button that deploys player's unique vulnerable contract and displays instance address in console |
| 4. | Exploit Submission UI | [ActionPanel.tsx](https://github.com/Gmin2/InkCtf/blob/main/app/src/components/ActionPanel.tsx) | "Submit Instance" button that calls factory validation and shows success/failure with transaction confirmation |
| 5. | Browser Console Utilities | [contract-helper.ts](https://github.com/Gmin2/InkCtf/blob/main/app/src/lib/contract-helper.ts), [console-utils.ts](https://github.com/Gmin2/InkCtf/blob/main/app/src/lib/console-utils.ts) | Ethernaut-style `contract` object with methods like `authenticate()`, `contribute()`, `fallback()`, `withdraw()`, plus `help()` function |
| 6. | Console Transaction Logs | [TacticalRelay.tsx](https://github.com/Gmin2/InkCtf/blob/main/app/src/components/TacticalRelay.tsx) | Real-time transaction status, errors, and confirmations displayed in terminal-style UI |
| 7. | Progress Tracking | [useProgress.ts](https://github.com/Gmin2/InkCtf/blob/main/app/src/hooks/useProgress.ts) | Client-side progress persistence with localStorage, completion indicators on level cards |
| 8. | Hint System | [LevelDocs.tsx](https://github.com/Gmin2/InkCtf/blob/main/app/src/components/LevelDocs.tsx), [level markdown files](https://github.com/Gmin2/InkCtf/tree/main/app/src/gamedata/levels) | Collapsible "Level Intel" panel with progressive hints, vulnerability explanations, and syntax-highlighted code examples |

---

## Additional Information

### Deployed Contract Addresses (Paseo Asset Hub)

All contracts are live and can be interacted with via [Contracts UI](https://contracts-ui.substrate.io/?rpc=wss://testnet-passet-hub.polkadot.io):

**Factory Contract Addresses:**

| Factory | Contract Address |
|---------|------------------|
| Instance Factory | `0x9ae57Cf7f28651FB3AB5d86524D0049362D29C8E` |
| Fallback Factory | `0x93fF27d4d3ad03D3aa596b75dEdb9c94a94D1F13` |
| Reentrance Factory | `0x165e19c3D5b9Cf24395AF1E2286c73410F3be712` |
| CoinFlip Factory | `0x8fde0C3f9c11bee2F66F0E82415834fe67f25aAa` |
| King Factory | `0x5b5c27597917857d2869f2ffe61F8606DBe4a5db` |
| Vault Factory | `0x14279D8C03c9feAaFe36229a634505EF231c4476` |

**Statistics Contract:**

| Contract | Address |
|----------|---------|
| Statistics | `0x40c68bb385e9AD1d19D1FA5ABc86BE0f1464099b` |


### The Six Vulnerability Levels

| # | Name | Difficulty | Vulnerability | Learning Objective |
|---|------|------------|---------------|-------------------|
| 1 | **Instance** | Easy | Public `get_password()` function | Blockchain storage is always public |
| 2 | **Fallback** | Medium | Fallback selector changes ownership | Fallback function dangers |
| 3 | **Reentrance** | Hard | Transfer before balance update | Checks-effects-interactions pattern |
| 4 | **CoinFlip** | Medium | `block_number % 2` for randomness | Block data is deterministic |
| 5 | **King** | Medium | Transfer fails = DoS | External call vulnerabilities |
| 6 | **Vault** | Easy | "Private" storage readable | All storage is public on-chain |

---

### How to Play

1. **Connect Wallet:** Click the wallet button and connect with Talisman, SubWallet, or Polkadot.js extension
2. **Get Testnet Tokens:** Visit [Paseo Faucet](https://faucet.polkadot.io/?parachain=1111) for PAS tokens
3. **Select a Level:** Choose from the mission grid on the homepage
4. **Get Instance:** Click "Get Instance" to deploy your personal vulnerable contract
5. **Exploit:** Open browser console (F12) and use `contract.*` methods to interact
6. **Submit:** Click "Submit Instance" to validate your exploit on-chain

**Browser Console Example (Level 1 - Instance):**
```javascript
// View available commands
help()

// Read the password from contract
await contract.getPassword()

// Authenticate with the password
await contract.authenticate("the_password_you_found")
```

---

### Frontend Technology Stack

- **Framework:** React + Vite + TypeScript
- **Styling:** Tailwind CSS with dark/light theme support
- **Blockchain:** @polkadot/api + @polkadot/extension-dapp
- **Routing:** React Router (/, /docs, /level/:id)
- **Code Display:** React Syntax Highlighter with oneLight/oneDark themes
- **State:** Custom hooks (useInkCTF, useProgress, useWallet)


### Testing Instructions for Grant Committee

**Option 1: Use the Live Platform**
1. Visit [ctfs.ink](https://ctfs.ink)
2. Connect a Polkadot wallet (Talisman recommended)
3. Get testnet tokens from the faucet
4. Play through the levels

**Option 2: Test via Contracts UI**
1. Go to [Contracts UI](https://contracts-ui.substrate.io/?rpc=wss://testnet-passet-hub.polkadot.io)
2. Add any factory contract using addresses above
3. Call `create_instance(your_address)` to get your vulnerable contract
4. Interact with your instance to exploit the vulnerability
5. Call `validate_instance(instance_address, your_address)` to verify

**Option 3: Test via pop CLI**
```bash
# Create Instance level instance
pop call contract \
  --contract 0x9ae57Cf7f28651FB3AB5d86524D0049362D29C8E \
  --message "Level::create_instance" \
  --args "your_wallet_address" \
  --url wss://testnet-passet-hub.polkadot.io
```

---

### What's Next (M3)

1. Contract unit tests for all levels
2. On-chain Statistics integration for leaderboard
3. Real-time contract state display
4. MetaMask support via Solidity ABI compatibility
5. Educational blog series
6. Video walkthrough

---

