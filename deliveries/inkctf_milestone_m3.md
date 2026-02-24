# Milestone Delivery :mailbox:

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/use-inkubator/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**

* **Application Document:** https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/InkCtf.md
* **Milestone Number:** 3

---

## Context

This delivery covers Milestone 3 (Polish, Testing, Deployment & Documentation) for the  ink!CTF platform. Building on the fully functional platform delivered in M1 & M2, this milestone focused on a new walkthrough page, comprehensive contract testing, UI/UX refinements, performance optimization through local caching and error handling.

**Live Platform:** [ctfs.ink](https://ctfs.ink)

---

## Deliverables

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- | ------------- |
| 0a. | License | [MIT License](https://github.com/Gmin2/InkCtf/blob/main/LICENSE) | MIT License applied to repository |
| 0b. | Documentation | [README.md](https://github.com/Gmin2/InkCtf/tree/main/app/src/gamedata/walkthroughs), [Walkthrough Page](https://github.com/Gmin2/InkCtf/blob/main/app/src/pages/WalkthroughPage.tsx) | Comprehensive player guide via in-app walkthrough page that guides players through the entire platform |
| 0c. | Testing and Testing Guide | [Contract Tests](https://github.com/Gmin2/InkCtf/) | Unit tests for all 6 level contracts covering deployment, exploitation, and validation flows |
| 0e. | Article | | Blog series / article, in https://gmin.blog/blog/introducing-inkctf |
| 1. | UI/UX Refinement | [Error Dialog](https://github.com/Gmin2/InkCtf/blob/main/app/src/components/ErrorDialog.tsx), [Subpage Rendering Fix](https://github.com/Gmin2/InkCtf/commit/62ad6bc) | Error dialogs for known errors, fixed subpage rendering, removed table markdown from descriptions, handled duplicate instantiation gracefully |
| 2. | Performance Optimization | [useStatistics.ts](https://github.com/Gmin2/InkCtf/blob/main/app/src/hooks/useStatistics.ts), [useProgress.ts](https://github.com/Gmin2/InkCtf/blob/main/app/src/hooks/useProgress.ts) | Stale-while-revalidate localStorage caching for stats page, persistent session info in localStorage, dry run checks before on-chain submissions |
| 3. | Security Hardening | [Dry Run Check](https://github.com/Gmin2/InkCtf/commit/395b114), [Duplicate Handling](https://github.com/Gmin2/InkCtf/commit/e67bdd5) | Dry run validation before instance creation, duplicate instantiation prevention, proper error handling for known failure modes |
| 4. | Testnet Deployment | [ctfs.ink](https://ctfs.ink) | Full platform deployed and operational on Paseo Asset Hub testnet |
| 5. | Comprehensive Testing | https://github.com/Gmin2/InkCtf/commit/4edc2df0e45f14d1d26dfee747461ce5b310ec1a) | Contract tests for all 6 levels: Instance, Fallback, Reentrance, CoinFlip, King, Vault |
| 6. | Project Handover | [GitHub Repository](https://github.com/Gmin2/InkCtf) | Full source code, documentation, and deployment configuration available |

---

## Commits in this Milestone

| Commit | Description |
|--------|-------------|
| `8f38f0e` | Stats page with on-chain and local querying |
| `62ad6bc` | Fixed subpage rendering |
| `15b0b2f` | Persistent session info in localStorage |
| `1ed56b3` | localStorage state handling for clear state |
| `114cf4f` | Removed table markdown from descriptions |
| `8943b35` | Error dialog for known errors |
| `a60a020` | Walkthrough page guiding players end-to-end |
| `e67bdd5` | Graceful duplicate instantiation handling |
| `395b114` | Dry run check on instance page |
| `fafb7fa` | Caching and localStorage options in stats page |
| `4edc2df` | All contract tests |

---

## Additional Information

### Key Improvements Over M1 & M2

- **Contract Tests:** Full test suite covering all 6 vulnerable contracts — deployment, exploitation, and on-chain validation
- **Stats Page Caching:** Stale-while-revalidate pattern using localStorage for instant stats display with background chain refresh
- **Player Guidance:** Dedicated walkthrough page that guides new players through the entire platform flow
- **Error Handling:** User-friendly error dialogs for common failure modes (insufficient funds, network issues, duplicate instances)
- **Dry Run Validation:** Pre-flight checks before submitting transactions to avoid wasted gas on known-failing calls

### Testing Instructions

1. Visit [ctfs.ink](https://ctfs.ink)
2. Connect a Polkadot wallet (Talisman recommended)
3. Get testnet tokens from [Paseo Faucet](https://faucet.polkadot.io/?parachain=1111)
4. Navigate to the Walkthrough page for guided instructions
5. Play through levels — observe error handling on duplicate instance creation
6. Visit Stats page — note instant cached data display with background refresh
