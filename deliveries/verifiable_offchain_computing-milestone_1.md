# Milestone Delivery :mailbox:

> ⚡ Only the GitHub account that submitted the application is allowed to submit milestones. 

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/use-inkubator/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:**, please provide a link to the merged contract from the running bounty (the `.md` file in the [applications](https://github.com/use-inkubator/Ecosystem-Grants/tree/master/applications) directory).

https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/verifiable_offchain_computing.md

**Context** (optional)
> Please provide a short paragraph or two connecting the deliverables in this milestone and describing their purpose.

On-chain computation capabilities are inherently limited by blockchain design, which affects all smart contract platforms including ink!. Our project aims to complement ink! smart contracts by providing verifiable off-chain computing capabilities through Phala Cloud's Trusted Execution Environment (TEE), enabling developers to build more complex applications while maintaining blockchain security guarantees.

This solution bridges the gap between blockchain's security and off-chain computational power.

In this first milestone, we deliver the SDK designed to simplify the connection between smart contracts and dApps deployed on Phala Cloud.
Its primary goal is to enable transactional and atomic cross-blockchain operations, ensuring seamless integration and interaction.

Key Benefits:
- Seamless connectivity between ink! smart contracts and workers
- Reliable KV-store on blockchains for durable state management
- Transactional (ACID) on-chain KV-store designed for stateful dApps deployed on Phala Cloud
- ACID-compliant read, write, and contract call operations for consistent data handling
- Request-response programming model that simplifies interactions between worker and on-chain smart contracts



**Deliverables**
> Please provide a list of all deliverables of the milestone extracted from the initial application and a link to the deliverable itself. Ideally all links inside the below table should include a commit hash, which will be used for testing. If you don't provide a commit hash, we will work off the default branch of your repository. Thus, if you plan on continuing work after delivery, we suggest you create a separate branch for either the delivery or your continuing work. 

| Number | Deliverable                                                                                    | Link                                                                                       | Notes |
|--------|------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------|
| 1.     | Library for ink! v6 smart contract                                                             | https://github.com/GuiGou12358/sc-rollup/tree/main/sc-rollup-client/sc-rollup-inkv6-client |       | 
| 2.     | Library for ink! v5 smart contract                                                             | https://github.com/GuiGou12358/sc-rollup/tree/main/sc-rollup-client/sc-rollup-inkv5-client |       | 
| 3.     | Library to interact with the the ink! contracts (to be used on Phala Cloud or everywhere else) | https://github.com/GuiGou12358/sc-rollup/tree/main/sc-rollup-api                           |       | 
| 4.     | Documentation                                                                                  | https://github.com/GuiGou12358/sc-rollup                                                   |       | 


**Additional Information**
> Any further comments on the milestone that you would like to share with us.
> 
The meta-transaction for the ink! v6 contract doesn't work for the time being due to an [issue](https://github.com/use-ink/ink/issues/2524) with the `ecdsa_recover` method in ink! v6. So, for the time being, the tests for this feature are disabled until the issue is fixed. The meta-transaction works fine for ink! v5 contract.
