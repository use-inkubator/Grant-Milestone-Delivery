# Milestone Delivery :mailbox:

> ⚡ Only the GitHub account that submitted the application is allowed to submit milestones. 

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/use-inkubator/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:**, please provide a link to the merged contract from the running bounty (the `.md` file in the [applications](https://github.com/use-inkubator/Ecosystem-Grants/tree/master/applications) directory).

https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/verifiable_offchain_computing.md

**Context** (optional)
> Please provide a short paragraph or two connecting the deliverables in this milestone and describing their purpose.

On-chain computation capabilities are inherently limited by blockchain design, which affects all smart contract platforms including ink!. Our project aims to complement ink! smart contracts by providing verifiable off-chain computing capabilities through Phala Cloud's Trusted Execution Environment (TEE), enabling developers to build more complex applications while maintaining blockchain security guarantees.

This solution bridges the gap between blockchain's security and off-chain computational power.

In the fourth milestone, a Guess The Number game is built with this solution previously delivered. 
We provide:
- the worker, deployed on Phala Cloud, that computes the target number to found via a Verifiable Random Function and give the clue (LowerThan, GreaterThan) based on the number proposed by the user. The worker (Graph Api Oracle) also queries the indexer to determine the maximum number of attempts available to the user. This number depends on the NFTs held by the user’s address. If no NFTs are owned by the address, the default number of attempts is 3.
- the ink! smart contract that manages the game (start a new game and save the guess made by the user) and consumes the response sent by the worker
- the ink! smart contract as an ERC-721 implementation. Each NFT has a unique identifier and an attribute 'max attempts'
- a Graph indexer that indexes all events coming from the two ink! smart contracts
- a UI to mint/transfer/burn the NFT and play to the game 
- the documentation to use these contracts


**Deliverables**
> Please provide a list of all deliverables of the milestone extracted from the initial application and a link to the deliverable itself. Ideally all links inside the below table should include a commit hash, which will be used for testing. If you don't provide a commit hash, we will work off the default branch of your repository. Thus, if you plan on continuing work after delivery, we suggest you create a separate branch for either the delivery or your continuing work. 

| Number | Deliverable             | Link                                                                                            | Notes |
|--------|-------------------------|-------------------------------------------------------------------------------------------------|-------|
| 1.     | ink! v6 smart contracts | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/guess-the-number/ink-v6-contracts   |       | 
| 2.     | Worker on Phala Cloud   | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/guess-the-number/worker-phala-cloud |       | 
| 3.     | Indexer                 | https://github.com/LuckyDapp/squid-guess                                                        |       | 
| 4.     | UI                      | https://github.com/LuckyDapp/guess-ui                                                           |       | 
| 5.     | Documentation           | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/guess-the-number                    |       | 
| 6.     | Documentation          | https://medium.com/@guigoucrypto/verifiable-offchain-workers-for-ink-and-evm-contracts-d943f9022699 |

The ink! v6 smart contracts are deployed on our development node (wss://query.substrate.fi/guess-the-number-node) 
 - ERC-721 : 0xeb3c4a6d9dd4b62eca09f87e5de151f37c02c2e7
 - Game : 0x987b94aaff6c60d10002d76f7ec2fe3fef837559

The indexer is available here: https://query2.substrate.fi/squid-guess/graphql

The UI is available here: https://guess.substrate.fi/

**Additional Information**
> Any further comments on the milestone that you would like to share with us.

Initially the smart contracts were deployed on Paseo and Westend but since few days, we can not interact anymore with these contracts via use.ink and cargo-contract cli (issue to estimate the gas). 
It's why we have set up a local ink! node and deployed the smart contracts there.
