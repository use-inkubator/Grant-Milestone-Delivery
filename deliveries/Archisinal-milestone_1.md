# Milestone Delivery :mailbox:

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Archisinal](https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/Archisinal.md)

**Context** (optional)
The 1st milestone focuses on the Smart Contracts part of our Artisanal MVP. It includes basic marketplace features like administering buyers and creators, selling NFTs with fixed prices or timed auctions, managing collections, etc.

**Deliverables**

| Number | Deliverable | Link                                                                                   | Notes                                                                                                                                                                                        |                             
| ------------- | ------------- |----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0a. | License | [LICENSE](https://github.com/archisinal/marketplace-contracts/blob/main/LICENSE)                   | MIT                                                                                                                                                                                          |
| 0b. | Documentation | [README.md](https://github.com/archisinal/marketplace-contracts/blob/main/README.md)                      | Entry-point of docs is README.md, then use `cargo doc --open` to check all docs.                                                                                                             |
| 0c. | Testing and Testing Guide | [TESTING.md](https://github.com/archisinal/marketplace-contracts/blob/main/TESTING.md)             | Created E2E, Security, Performance tests, and testing guide for them.                                                                                                                        |
| 0d. | Docker | [Dockerfile](https://github.com/archisinal/marketplace-contracts/blob/main/Dockerfile), [CI](https://github.com/Archisinal/marketplace-contracts/blob/main/.github/workflows/ci.yml)             | Created dockerfile for testing, also CI for automatic checks.                                                                                                                                |
| 0e. | Article | [Medium: Archisinal Technologies — Genesis Scoping & MVP](https://medium.com/p/3df888e1de98)                                                                            |                                                                                                                                                                                              |
| 1. | NFT Minting | [ArchNFT](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/arch_nft)        | Implemented in ArchNFT contract (PSP34 logic from OpenBrush). Also ArchNFT contains different metadata such as collection royalty.                                                                                                                                                                                             |
| 2. | NFT Transfer | [ArchNFT](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/arch_nft)        | Implemented in ArchNFT contract (PSP34 logic from OpenBrush). Also ArchNFT contains different metadata such as collection royalty.                                                           |
| 3. | Creator’s Administering | [Creator](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/creator)         | Creator contract inherits logic of user contract and adding opportunity to deploy collections.                                                                                               |
| 4. | Buyer’s Administering | [User](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/user)               | User contract is used to manage user data on-chain, such as NFT-avatars or nicks. Will be extended in the future releases.                                                                   |
| 5. | Marketplace Administration | [Marketplace](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/marketplace) | Contract that contains auction and just marketplace logic.                                                                                                                                   |
| 6. | Auction | [Marketplace](https://github.com/archisinal/marketplace-contracts/tree/main/contracts/marketplace) | Auction is a part of `marketplace` contract.                                                                                                                                                 |
| 7. | Test Network Deployment | [DEPLOYMENTS.md](https://github.com/archisinal/marketplace-contracts/blob/main/DEPLOYMENTS.md)     | Successfully deployed our contracts to Shibuya testing network, contract addresses are provided in `DEPLOYMENTS.md` file.                                                                    |
| 8. | Quality, Performance, and Security Considerations | [Tests](https://github.com/archisinal/marketplace-contracts/tree/main/test)                            | All contracts, and `archisinal_lib` are checked via clippy and rustfmt, tests checked via prettier, eslint and typescript, also security and perfomamnce considerations are part of testing. |



**Additional Information**

- Marketing materials:
  - [Go-to-market strategy](https://www.canva.com/design/DAFtxP4snUY/1hHgx_zNKLNjASJ9EZr6hg/view?utm_content=DAFtxP4snUY&utm_campaign=designshare&utm_medium=link&utm_source=publishsharelink)
- Social media links:
  - [Archisinal Blog](https://archisinal.medium.com/)
  - [Instagram](https://www.instagram.com/archisinal.io/)
  - [LinkedIn](https://www.linkedin.com/company/archisinal-technologies/)
