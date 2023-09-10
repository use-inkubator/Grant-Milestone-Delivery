# Milestone Delivery :mailbox:

> ⚡ Only the GitHub account that submitted the application is allowed to submit milestones. 
> 
> Don't remove any of the mandatory parts presented in bold letters or as headlines! Lines starting with `>`, such as this one, can be removed.

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Archisinal](https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/Archisinal.md)

**Context** (optional)
> The 1st milestone covers only Smart Contracts part of Archisinal MVP. It covers simple marketplace features, including buyer's and creator's administering, fixed price and timed auction options for NFT sales, and colleciton management

**Deliverables**

| Number | Deliverable | Link                                                                                   | Notes                                                                                                                                                                                        |                             
| ------------- | ------------- |----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0a. | License | [LICENSE](https://github.com/archisinal/marketplace-contracts/blob/main/LICENSE)                   | MIT                                                                                                                                                                                          |
| 0b. | Documentation | [DOCS](https://github.com/archisinal/marketplace-contracts/blob/main/README.md)                      | Entry-point of docs is README.md, then use `cargo doc --open` to check all docs.                                                                                                             |
| 0c. | Testing and Testing Guide | [TESTING](https://github.com/archisinal/marketplace-contracts/blob/main/TESTING.md)             | Created E2E, Security, Performance tests, and testing guide for them.                                                                                                                        |
| 0d. | Docker | [Dockerfile](https://github.com/archisinal/marketplace-contracts/blob/main/Dockerfile)             | Created dockerfile for testing, also CI for automatic checks.                                                                                                                                |
| 0e. | Article | [Meduim: Archisinal Technologies — Genesis Scoping & MVP](https://medium.com/p/3df888e1de98)                                                                            |                                                                                                                                                                                              |
| 1. | NFT Minting | [ArchNFT](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/arch_nft)        | Implemented in ArchNFT contract (PSP34 logic from OpenBrush). Also ArchNFT contains different metadata such as collection royalty.                                                                                                                                                                                             |
| 2. | NFT Transfer | [ArchNFT](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/arch_nft)        | Implemented in ArchNFT contract (PSP34 logic from OpenBrush). Also ArchNFT contains different metadata such as collection royalty.                                                           |
| 3. | Creator’s Administering | [Creator](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/creator)         | Creator contract inherits logic of user contract and adding opportunity to deploy collections.                                                                                               |
| 4. | Buyer’s Administering | [User](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/user)               | User contract is used to manage user data on-chain, such as NFT-avatars or nicks. Will be extended in the future releases.                                                                   |
| 5. | Marketplace Administration | [Marketplace](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/marketplace) | Contract that contains auction and just marketplace logic.                                                                                                                                   |
| 6. | Auction | [Marketplace](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/marketplace) | Auction is a part of `marketplace` contract.                                                                                                                                                 |
| 7. | Test Network Deployment | [DEPLOYMENTS.md](https://github.com/archisinal/marketplace-contracts/blob/main/DEPLOYMENTS.md)     | Successfully deployed our contracts to Shibuya testing network, contract addresses are provided in `DEPLOYMENTS.md` file.                                                                    |
| 8. | Quality, Performance, and Security Considerations | [Tests](https://github.com/archisinal/marketplace-contracts/tree/main/test)                            | All contracts, and `archisinal_lib` are checked via clippy and rustfmt, tests checked via prettier, eslint and typescript, also security and perfomamnce considerations are part of testing. |



**Additional Information**
> //TODO add marketing docs
