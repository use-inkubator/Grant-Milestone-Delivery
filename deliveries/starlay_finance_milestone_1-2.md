# Milestone Delivery :mailbox:

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Starlay Finance](https://github.com/Chidasan/Ecosystem-Grants/blob/master/applications/starlay_finance.md).

**Deliverables**

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 0a. | License | [License](https://github.com/starlay-finance/starlay-protocol-wasm/blob/0576d244710c7a0e904479721682929ddbff51c3/LICENSE.md) | 　|
| 0b. | Documentation | [Documentation](https://docs.starlay.finance) |　 |
| 1. | Liquidate_borrow function | [Liquidate_borrow function](https://github.com/starlay-finance/starlay-protocol-wasm/blob/0576d244710c7a0e904479721682929ddbff51c3/logics/impls/pool/mod.rs#L434)  | **Test link:** [Liquidate_Borrow](https://github.com/starlay-finance/starlay-protocol-wasm/blob/0576d244710c7a0e904479721682929ddbff51c3/tests/Pool1.spec.ts#L716) **Test Method:** 1. Run swanky-node on localhost 2. yarn compile 3. yarn test:single tests/Pool1.spec.ts |
| 2. | List tokens (by the owner) | [List tokens](https://github.com/starlay-finance/starlay-protocol-wasm/blob/0576d244710c7a0e904479721682929ddbff51c3/contracts/manager/lib.rs#L111) | **Test link:** [List Tokens](https://github.com/starlay-finance/starlay-protocol-wasm/blob/0576d244710c7a0e904479721682929ddbff51c3/tests/Manager.spec.ts#L82) **Test Method:** 1. Run swanky-node on localhost 2. yarn compile 3. yarn test:single tests/Manager.spec.ts |
| 3. | Switch between EVM and Polkadot | [Switch between EVM and Polkadot](https://testnet-wasm.starlay.finance/app/wasm) | The link provided allows you to test the capability of our platform to switch between EVM and Polkadot. |

**Additional Information**

- **End-to-End Testing Results with GitHub CI:**
  - [Pool1.spec.ts](https://github.com/starlay-finance/starlay-protocol-wasm/actions/runs/5900982103/job/16009345510#step:20:2892)
  - [Pool2.spec.ts](https://github.com/starlay-finance/starlay-protocol-wasm/actions/runs/5900982103/job/16009345510#step:20:464)
  - [Manager.spec.ts](https://github.com/starlay-finance/starlay-protocol-wasm/actions/runs/5900982103/job/16009345510#step:20:947)
  - [WETHGateway.spec.ts](https://github.com/starlay-finance/starlay-protocol-wasm/actions/runs/5900982103/job/16009345510#step:20:1922)
  - [Controller.spec.ts](https://github.com/starlay-finance/starlay-protocol-wasm/actions/runs/5900982103/job/16009345510#step:20:2389)
  - [Flashloan.spec.ts](https://github.com/starlay-finance/starlay-protocol-wasm/actions/runs/5900982103/job/16009345510#step:20:3850)
  - [Lens.spec.ts](https://github.com/starlay-finance/starlay-protocol-wasm/actions/runs/5900982103/job/16009345510#step:20:4930)

- **Gitbook Updates:**
  We've updated the liquidation section on our gitbook. Furthermore, we've been actively updating and modifying other sections as documented on the following [Notion page](https://unruly-innovation-bff.notion.site/Starlay-Gitbook-5a9fd96d676a47fdbd411c07e0857f9e?pvs=4*). As discussed in milestone1-1, once we transition to the mainnet, we will promptly update our gitbook page with the relevant information and resources.
