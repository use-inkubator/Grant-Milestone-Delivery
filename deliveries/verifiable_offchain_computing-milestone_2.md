# Milestone Delivery :mailbox:

> ⚡ Only the GitHub account that submitted the application is allowed to submit milestones. 

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/use-inkubator/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:**, please provide a link to the merged contract from the running bounty (the `.md` file in the [applications](https://github.com/use-inkubator/Ecosystem-Grants/tree/master/applications) directory).

https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/verifiable_offchain_computing.md

**Context** (optional)
> Please provide a short paragraph or two connecting the deliverables in this milestone and describing their purpose.

On-chain computation capabilities are inherently limited by blockchain design, which affects all smart contract platforms including ink!. Our project aims to complement ink! smart contracts by providing verifiable off-chain computing capabilities through Phala Cloud's Trusted Execution Environment (TEE), enabling developers to build more complex applications while maintaining blockchain security guarantees.

This solution bridges the gap between blockchain's security and off-chain computational power.

In the second milestone, a Feed Price Oracle is built with this sdb previously delivered. 
We provide:
- the worker, deployed on Phala Cloud, that feeds the prices in the smart contract
- the ink! smart contract that consumes the prices sent by the worker
- a UI to display the data from the smart contract
- the documentation to use these contracts


**Deliverables**
> Please provide a list of all deliverables of the milestone extracted from the initial application and a link to the deliverable itself. Ideally all links inside the below table should include a commit hash, which will be used for testing. If you don't provide a commit hash, we will work off the default branch of your repository. Thus, if you plan on continuing work after delivery, we suggest you create a separate branch for either the delivery or your continuing work. 

| Number | Deliverable                      | Link                                                                                                     | Notes |
|--------|----------------------------------|----------------------------------------------------------------------------------------------------------|-------|
| 1.     | ink! v6 smart contract           | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/price-feed-oracle/price_feed_consumer/ink-v6 |       | 
| 2.     | ink! v5 smart contract           | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/price-feed-oracle/price_feed_consumer/ink-v5 |       | 
| 2.     | Price Feed Oracle on Phala Cloud | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/price-feed-oracle/worker-phala-cloud         |       | 
| 3.     | UI                               | https://github.com/GuiGou12358/price-feed-ui-v2                                                          |       | 
| 4.     | Documentation                    | https://github.com/GuiGou12358/sc-rollup/tree/main/examples/price-feed-oracle                            |       | 

The ink! v6 smart contract `0x96213b72A4CF50402D9dFe71919350451B8dC356` is deployed on Pop Network (Paseo testnet).

The ink! v5 smart contract `W6jGgZUAiryufdJRX33GdDTeX28pt7dZxawwbCUfFwbc2cH` is deployed on Shibuya (Astar testnet).

The UI is deployed here: https://price-feed-ui-v2.vercel.app/

The worker is deployed on Phala Cloud, the UI to start/stop the workers and more: https://367dcb717cab98ca9a84e5534d61df6b91467f4e-3000.dstack-testnet.phala.network/

**Additional Information**
> Any further comments on the milestone that you would like to share with us.

