# Milestone Delivery :mailbox:

* **Application Document:** [Dedot & Typink](https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/dedot_typink.md)
* **Milestone:** 1

## Overview
### Main purpose this delivery

- Implement comprehensive support for pallet-revive interactions for ink! v6 contracts, including contract deployment, queries, transactions, and event handling
- Develop essential utilities for pallet-revive operations: toEvmAddress, CREATE1, CREATE2, generateRandomHex (for deployment salt) and related functions
- Maintain unified interface architecture to ensure seamless backward compatibility with previous ink! versions, so the interface will automatically detect the ink! version using the metadata to do intial validation (address format, pallet availability, ...) and interact with coresponding pallet APIs (pallet-revive or pallet-contracts)

### Key Changes and Scope Adjustments

- **EVM Wallets Integration Limitation & Challenge:** The original proposal included support for signing transaction using EVM Wallets (e.g: MetaMask, SubWallet...). However, this functionality is currently only achievable through interactions with [eth_* JSON-RPC API](https://ethereum.org/en/developers/docs/apis/json-rpc/) via a different proxy RPC server ([more on this](https://forum.polkadot.network/t/contracts-on-assethub-roadmap/9513)), which Dedot does not natively support. Implementing this would require significant architectural changes to Dedot's core architecture. Consequently, after researching, we have decided to focus on supporting transaction signing through Polkadot Wallets for now (SubWallet, Polkadot.js Signer, Talisman, etc.)
- **New Contract Storage API:** We have introduced a new storage API that extends beyond the original proposal scope, enabling direct contract storage retrieval without having to send a query to the contract. Since interaction with contracts deployed on `pallet-revive` using a Substrate-based (32 bytes) address would require users to map the account first which is not a good UX. This Storage API offer a different way to access contract storage without users having to do the account mapping initially.

### Related Pull Requests
  - [Pallet-Revive & inital ink! v6 Support Implemantation](https://github.com/dedotdev/dedot/pull/479)
  - [Storage API Implementation](https://github.com/dedotdev/dedot/pull/452)

### Next Steps for M2
  - Provide more abstracted and user-friendly APIs to make it easier for developers to calculate contract addresses, without relying directly on the lower-level [CREATE1 and CREATE2 methods](https://docs.dedot.dev/ink-smart-contracts/deploy#ink-v6-only-calculate-contract-address), these methods are somewhat cumbersome and negatively impact developer experience.
  - Automatically perform a dry-run of contract transactions to validate them and estimate gas fees and storage deposit limits. Currently, developers are required to manually initiate a dry-run before submitting a transaction, which adds friction and reduces efficiency.
  - Add support for [Solidity-compatible metadata (ABI)](https://docs.dedot.dev/ink-smart-contracts/deploy#ink-v6-only-calculate-contract-address). Generate Types & APIs using the metadata, this should include IntelliSense with auto-completions, and ensure full support for contract queries, transactions, events, and storage APIs working seamlessly.

## Deliverables

| Number | Deliverable | Link | Notes |
| -----: | ----------- | ------------- | ------------- |
| **0a.** | License | [Apache 2.0](https://github.com/dedotdev/dedot/blob/main/LICENSE) | | 
| **0b.** | Documentation | - [Documentation](https://docs.dedot.dev/ink-smart-contracts)<br/> - Examples: [PSP22](https://github.com/dedotdev/dedot/blob/main/examples/scripts/inkv6/psp22-storage.ts), [flipper](https://github.com/dedotdev/dedot/blob/main/examples/scripts/inkv6/interact.ts) | - Make sure to use the latest [ink-node](https://github.com/use-ink/ink-node/releases/tag/v0.43.3) binary to test out the examples | 
| **0c.** | Testing and Testing Guide | - We've added unit tests & E2E tests (via zombienet & ink-node) | To run the tests, please follow the instructions below: <br/> - To run unit tests, simply clone the repo and run: `yarn install && yarn test` <br/> - To run e2e tests, please follow instructions in the repo: [ink-node](https://github.com/dedotdev/dedot/blob/main/e2e/contracts/README.md), [zombienet](https://github.com/dedotdev/dedot/blob/main/e2e/zombienet/README.md). <br/><br/> We're running [GH Actions](https://github.com/dedotdev/dedot/actions) for these tests on every changes/commits. | 
| **0d.** | Article & Communication | - [Forum Post](https://forum.polkadot.network/t/dedot-now-supports-pallet-revive-and-ink-v6-through-ink-ubator-2-0/13355)<br/> - [Announcement on ink! Telegram channel](https://t.me/inkathon/1/3000) | We're planning to make an X thread on this integration with details once we merge [the PR](https://github.com/dedotdev/dedot/pull/506) for better abstraction to calcuate contract address & auto-dry run, since the API will be easier to use for devs. | 
| 1. | `pallet-revive` support | - **Support for 20-byte (H160) address format & utilities:** [toEvmAddress, CREATE1, CREATE2](https://github.com/dedotdev/dedot/blob/main/packages/contracts/src/utils/address.ts), [AccountId20 (already supported)](https://github.com/dedotdev/dedot/blob/main/packages/codecs/src/codecs/generic/AccountId20.ts) ...<br />- **Contract Operations:** Implement comprehensive support for [deploying contracts](https://github.com/dedotdev/dedot/blob/main/packages/contracts/src/ContractDeployer.ts), [queries & submitting transactions](https://github.com/dedotdev/dedot/blob/main/packages/contracts/src/Contract.ts)<br />- **Event Handling:** [Listen to](https://github.com/dedotdev/dedot/blob/main/packages/contracts/src/executor/EventExecutor.ts) and [decode contract](https://github.com/dedotdev/dedot/blob/987267eac0d87ed9c8e3888ca4f3fb3f7bce0714/packages/contracts/src/TypinkRegistry.ts#L261-L273) events from pallet-revive<br />- **New Contract Storage API:** Implement [fully-typed Storage API](https://github.com/dedotdev/dedot/blob/987267eac0d87ed9c8e3888ca4f3fb3f7bce0714/packages/contracts/src/Contract.ts#L92-L112) to fetch contract storage directly | - We removed the item for support signing transactions with EVM wallets, instead devs will be signing transactions with Polkadot Wallets (e.g: SubWallet, Talisman ...) <br/> - We added a new item for Contract Storage API |

## Additional

As we're making a small adjustment to the initial proposal, please let us know if we are required to make a separate PR to the [Ecosystem Grants](https://github.com/use-inkubator/Ecosystem-Grants) repo to update this change.
