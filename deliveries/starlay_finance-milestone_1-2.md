# Milestone Delivery :mailbox:

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Starlay Finance](https://github.com/Chidasan/Ecosystem-Grants/blob/master/applications/starlay_finance.md).

**Deliverables**

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 0a. | License | [License](https://github.com/starlay-finance/starlay-protocol-wasm/blob/main/LICENSE.md) | 　|
| 0b. | Documentation | [Documentation](https://docs.starlay.finance) |　 |
| 1. | Liquidate_borrow function | [Liquidate_borrow function](https://github.com/starlay-finance/starlay-protocol-wasm/blob/main/logics/impls/pool/mod.rs#L401)  | **Test link:** [Liquidate_Borrow](https://github.com/starlay-finance/starlay-protocol-wasm/blob/main/tests/Pool.spec.ts#L679) **Test Method:** 1. Run swanky-node on localhost 2. yarn compile 3. yarn test:single tests/Pool.spec.ts |
| 2. | List tokens (by the owner) | [List tokens](https://github.com/starlay-finance/starlay-protocol-wasm/blob/main/contracts/manager/lib.rs#L98) | **Test link:** [List Tokens](https://github.com/starlay-finance/starlay-protocol-wasm/blob/main/tests/Manager.spec.ts#L58) **Test Method:** 1. Run swanky-node on localhost 2. yarn compile 3. yarn test:single tests/Manager.spec.ts |
| 3. | Switch between EVM and Polkadot | [Switch between EVM and Polkadot](https://testnet-wasm.starlay.finance/) | The link provided allows you to test the capability of our platform to switch between EVM and Polkadot. |

**Additional Information**

```
