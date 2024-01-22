# Milestone Delivery :mailbox:

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Ink Multisig](https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/ink_contract_multi-sig.md)

**Context**

The provided smart contract is a Multi-Signature (MultiSig) contract implemented in ink! - a Rust-based eDSL for writing smart contracts for the Polkadot ecosystem. A MultiSig contract is a type of contract that requires approval from multiple accounts (owners) before a transaction is executed.

Key details and deliverables of this smart contract are as follows:

1) Multisig Contract: The contract enables a group of owners to propose, approve, or reject transactions. Transactions are only executed if an approval threshold is met.

2) Threshold Management: The smart contract includes functionality for changing the approval threshold - the minimum number of approvals needed for a transaction to be executed.

3) Owner Management: The contract also has functions for adding and removing owners, as well as checking if a specific account is an owner. The number of owners is capped by a predefined constant (MAX_OWNERS).

4) Transaction Management: Each transaction is stored with a unique TxId and includes the recipient's address, a function selector, input data, transferred value, gas limit, and a boolean that controls whether reentry is allowed. Once a transaction is proposed, the owners can approve or reject it.

The following documents delivered in the docs folder provide more context about our research and implementation:

1) Overcoming Reentrancy and Circular Call Challenges in Polkadot Smart Contracts

2) Discovery POC Understanding Ink Smart Contracts

3) Contract Pallet Multisig Implementation_Backendless Architecture Document

**Deliverables**

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| **0a.** | License | https://github.com/protofire/ink-multisig/blob/Milestone-1/LICENSE | |
| **0b.** | Documentation | https://github.com/protofire/ink-multisig/blob/Milestone-1/README.md | |
| **0c.** | Testing and Testing Guide | https://github.com/protofire/ink-multisig/blob/Milestone-1/README.md | |
| **0d.** | Docker | - |There is no Docker to deliver in this phase |
| 1. | Research Documents | https://github.com/protofire/ink-multisig/blob/Milestone-1/docs/Discovery%20POC%20Understanding%20Ink%20Smart%20Contracts.pdf / https://github.com/protofire/ink-multisig/blob/Milestone-1/docs/Overcoming%20Reentrancy%20and%20Circular%20Call%20Challenges%20in%20Polkadot%20Smart%20Contracts.pdf | |
| 2. | Technical Specs Document  | https://github.com/protofire/ink-multisig/blob/Milestone-1/docs/Contract%20Pallets%20Multisig%20Implementation_Backendless%20Architecture%20Document.pdf | |
| 3. | Multisig Smart Contract | https://github.com/protofire/ink-multisig/tree/Milestone-1/contracts | |