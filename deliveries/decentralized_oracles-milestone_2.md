# Milestone Delivery :mailbox:

> ⚡ Only the GitHub account that submitted the application is allowed to submit milestones.

**The invoice has been sent out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**

* **Application Document:**, please provide a link to the merged contract from the running bounty (the `.md` file in the [applications](https://github.com/smart-contract-bounty/Wasm-Bounty-01/tree/master/applications) directory).

https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/decentralized_oracles.md


**Context** (optional)
> Please provide a short paragraph or two connecting the deliverables in this milestone and describing their purpose.

Recently the Phala team released the Lens Api Oracle.  
https://medium.com/phala-network/lensapi-oracle-supercharge-your-web3-social-app-a413c936df2b

This oracle is built on offchain rollup request-response for EVM smart contracts.  
https://github.com/Phala-Network/phat-bricks/tree/master/phat/contracts/action_offchain_rollup

Our team has applied to the Phala builder program to develop the offchain rollup request-response for Ink! smart contracts.

When this milestone is completed, we would like to use this offchain rollup request-response model to build:
- VRF Oracle. It should generate cryptographically secure random numbers for Ink! smart contracts
- Graph API Oracle that:
    - accesses SubQuery/SubSquid via an URI
    - transform and format the response via the JS engine developed by the Phala team
    - send the output to the Ink! smart contract

In the milestone 2, concerning the Graph Api Oracle, we provide:
- the Phala offchain rollup for the Graph Api Oracle 
- the Ink! smart contract to interact with the offchain rollup
- a UI to test and play with these smart contracts.
- A SubQuery project that indexes the data from dApp Staking on Astar Network
- the documentation to use these contracts

**Deliverables**
> Please provide a list of all deliverables of the milestone extracted from the initial application and a link to the deliverable itself. Ideally all links inside the below table should include a commit hash, which will be used for testing. If you don't provide a commit hash, we will work off the default branch of your repository. Thus, if you plan on continuing work after delivery, we suggest you create a separate branch for either the delivery or your continuing work.
> If there is anything particular about any of the deliverables we or a future reader should know, use the respective `Notes` column.

Demo here: https://graph-api-decentralized-oracle.substrate.fi

| Number | Deliverable                             | Link                                                                              | Notes                                                                  |
|--------|-----------------------------------------|-----------------------------------------------------------------------------------|------------------------------------------------------------------------|
| 1.     | Phat contract: JS Offchain Rollup       | https://github.com/decentralized-oracles/graph-api-oracle/tree/main/phat/contracts/js_offchain_rollup|                                                                        | 
| 2.     | Ink! smart contract: graph api consumer | https://github.com/decentralized-oracles/graph-api-oracle/tree/main/ink/contracts/graph_api_consumer|                                                                        | 
| 3.     | Documentation                           | https://github.com/decentralized-oracles/graph-api-oracle                                |                                                                        | 
| 4.     | UI                                      | https://github.com/decentralized-oracles/graph-api-ui                            | Demo here: https://graph-api-decentralized-oracle.substrate.fi         |  
| 5.     | SubQuery Indexer                        | https://github.com/decentralized-oracles/subquery-dapp-staking                         | Deployed here: https://query.substrate.fi/dapps-staking-subquery-astar | 


**Additional Information**
> Any further comments on the milestone that you would like to share with us. 