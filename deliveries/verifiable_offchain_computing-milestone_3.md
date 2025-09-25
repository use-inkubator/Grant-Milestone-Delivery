# Milestone Delivery :mailbox:

> ⚡ Only the GitHub account that submitted the application is allowed to submit milestones. 

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/use-inkubator/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:**, please provide a link to the merged contract from the running bounty (the `.md` file in the [applications](https://github.com/use-inkubator/Ecosystem-Grants/tree/master/applications) directory).

https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/verifiable_offchain_computing.md

**Context** (optional)
> Please provide a short paragraph or two connecting the deliverables in this milestone and describing their purpose.

On-chain computation capabilities are inherently limited by blockchain design, which affects all smart contract platforms including ink!. Our project aims to complement ink! smart contracts by providing verifiable off-chain computing capabilities through Phala Cloud's Trusted Execution Environment (TEE), enabling developers to build more complex applications while maintaining blockchain security guarantees.

This solution bridges the gap between blockchain's security and off-chain computational power.

In the third milestone, a Guess The Number game is built with this solution previously delivered. 
We provide:
- the worker, deployed on Phala Cloud, that compute the target number to found via a Verifiable Random Function and give the clue (LowerThan, GreaterThan) based on the number proposed by the user 
- the ink! smart contract that manage the game (start a new game and save the guess made by the user) and consumes the response sent by the worker
- a UI to display the data from the smart contract
- the documentation to use these contracts


**Deliverables**
> Please provide a list of all deliverables of the milestone extracted from the initial application and a link to the deliverable itself. Ideally all links inside the below table should include a commit hash, which will be used for testing. If you don't provide a commit hash, we will work off the default branch of your repository. Thus, if you plan on continuing work after delivery, we suggest you create a separate branch for either the delivery or your continuing work. 

| Number | Deliverable            | Link                                                                                                | Notes                                                                                                                                          |
|--------|------------------------|-----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| 1.     | ink! v6 smart contract | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/guess-the-number/ink-v6-contract        |                                                                                                                                                | 
| 2.     | Worker on Phala Cloud  | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/guess-the-number/worker-phala-cloud     |                                                                                                                                                | 
| 3.     | UI                     | https://github.com/GuiGou12358/guess-the-number-ui                                                  | A new, more sophisticated version, is under development but ideally we would need an graph indexer (SubQuery or Subsquid) for ink! v6 contract | 
| 4.     | Documentation          | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/guess-the-number                        |                                                                                                                                                | 
| 5.     | Documentation          | https://medium.com/@guigoucrypto/verifiable-offchain-workers-for-ink-and-evm-contracts-d943f9022699 |                                                                                                                                                | 

The ink! v6 smart contract `0xe75cbD47620dBb2053CF2A98D06840f06baAf141` is deployed on PAssetHub Network (testnet).

The UI is deployed here: https://guess-the-number-ui.vercel.app/

The worker is deployed on Phala Cloud, the UI to start/stop the workers and more: https://8d876b0ed6e97a50739e92b87b24e5e1f1ed45cb-3020.dstack-prod5.phala.network/

**Additional Information**
> Any further comments on the milestone that you would like to share with us.

