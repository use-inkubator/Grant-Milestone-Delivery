# Milestone Delivery :mailbox:

> ⚡ Only the GitHub account that submitted the application is allowed to submit milestones.

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**

* **Application Document:**, please provide a link to the merged contract from the running buonty (the `.md` file in the [applications](https://github.com/smart-contract-bounty/Wasm-Bounty-01/tree/master/applications) directory).

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

In the milestone1, concerning the VRF, we will provide:
- the Phala offchain rollup for the VRF
- the Ink! smart contracts to interact with the offchain rollup
- a UI to test and play with these smart contracts.
- the documentation to use these contracts

**Deliverables**
> Please provide a list of all deliverables of the milestone extracted from the initial application and a link to the deliverable itself. Ideally all links inside the below table should include a commit hash, which will be used for testing. If you don't provide a commit hash, we will work off the default branch of your repository. Thus, if you plan on continuing work after delivery, we suggest you create a separate branch for either the delivery or your continuing work.
> If there is anything particular about any of the deliverables we or a future reader should know, use the respective `Notes` column.

| Number | Deliverable                                          | Link                                                                              | Notes                                                           |
|--------|------------------------------------------------------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------|
| 1.     | Phat contract: VRF Oracle                            | https://github.com/decentralized-oracles/vrf/tree/main/phat/contracts/vrf_oracle  | ...                                                             | 
| 2.     | Ink! smart contract: vrf consumer                    | https://github.com/decentralized-oracles/vrf/tree/main/ink/contracts/vrf_consumer | ...                                                             | 
| 3.     | Library: crate to develop easily the oracle/consumer | https://github.com/Phala-Network/phat-offchain-rollup                             | This part has been released in context of Phala Builder Program | 
| 4.     | Documentation                                        | https://github.com/decentralized-oracles/vrf                                      |                                                                 | 
| 5.     | UI                                                   | https://vrf-decentralized-oracle.substrate.fi                                     | ...                                                             |  
| 6.     | Squid used by the UI                                 | https://github.com/decentralized-oracles/squid-vrf                                | ...                                                             |   


**Additional Information**
> Any further comments on the milestone that you would like to share with us.
 