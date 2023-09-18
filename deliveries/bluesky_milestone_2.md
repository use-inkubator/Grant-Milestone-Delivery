# Milestone Delivery :mailbox:

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:**

[Bluesky project](https://github.com/dan0ero/Ecosystem-Grants/blob/master/applications/bluesky.md)

**Context** (optional)

[This deliverable](https://medium.com/@opensmartcontract/learn-ink-by-example-part-2-upgrade-ink-smart-contracts-29ff34bd1b26) is part 2 of the same Learn ink! By Example series, specifically covering ink! smart contract upgradability and storage layouts, particularly in comparison to Solidity contract upgradability.


**Deliverables**

| Number | Deliverable | Notes | Links |
| ------------- | ------------- | ------------- |------------- |
| 1. | Upgrade ink! smart contracts due to feature changes | Demonstrate Upgradability via ink!'s built-in upgradeable smart contract features to upgrade the smart contract code without having to migrate the data or interrupt the user experience | [dApps business logic change triggers smart contract upgrades](https://docs.google.com/document/d/1qOTZmsEMuHqBMV2It6yomhduHTlFt6KrErpKd3pRkA4/edit#heading=h.ebvi3ppn6ave) with detailed coverage on [ink! contract storage layout ](https://docs.google.com/document/d/1qOTZmsEMuHqBMV2It6yomhduHTlFt6KrErpKd3pRkA4/edit#heading=h.lqaakdi2om8d), and [best practices](https://docs.google.com/document/d/1qOTZmsEMuHqBMV2It6yomhduHTlFt6KrErpKd3pRkA4/edit#heading=h.g73axqbjlgsz) to avoid [potential storage collisions and corruptions](https://docs.google.com/document/d/1qOTZmsEMuHqBMV2It6yomhduHTlFt6KrErpKd3pRkA4/edit#heading=h.qbnihzgpcffo) | |
| 2. | Seamless interaction during upgrades | Demonstrate users can continue to interact with the updated contract without losing any data or transaction history as ink!'s flexible upgrade mechanism allows for on-chain upgrades of smart contracts | Test script output with both regression tests before upgrade and new tests after upgrade, as well as seamless user interaction through upgrade screenshots [documented in this section](https://docs.google.com/document/d/1qOTZmsEMuHqBMV2It6yomhduHTlFt6KrErpKd3pRkA4/edit#heading=h.l4bmgs1le3fy) | |
| 3. | Demo ink! built-in tools and libraries for managing contract upgrades | For example, the "Upgradeable" trait that can be used to mark a smart contract as upgradeable, and the "Dispatcher" module that can be used to handle contract upgrades and routing of function calls| Covered in [Solidity smart contract upgrade comparisons](https://docs.google.com/document/d/1qOTZmsEMuHqBMV2It6yomhduHTlFt6KrErpKd3pRkA4/edit#heading=h.n6js1hfmlgir) and [Upgradeable example with code snippet ](https://docs.google.com/document/d/1qOTZmsEMuHqBMV2It6yomhduHTlFt6KrErpKd3pRkA4/edit#heading=h.ebvi3ppn6ave)| |
| 4. | Expose ink!'s Dispatcher module | To handle contract upgrades and routing of function calls between different versions of the same contract | [ink! smart contract upgrade patterns and comparison with Solidity](https://docs.google.com/document/d/1qOTZmsEMuHqBMV2It6yomhduHTlFt6KrErpKd3pRkA4/edit#heading=h.ap8zxwslp6jf) | |
| 5. | Improve storage example of upgradable contracts | This [issue](https://github.com/paritytech/ink/issues/1679) says "The documentation around storage and upgradeability isn't thorough enough", use this showcase to address the pain points to provide better examples and documentation for contract developers| The [issue](https://github.com/paritytech/ink/issues/1679) was closed | Can adapt [detailed ink! smart contract upgradability and storage contents ](https://docs.google.com/document/d/1qOTZmsEMuHqBMV2It6yomhduHTlFt6KrErpKd3pRkA4/edit#heading=h.lqaakdi2om8d)as needed|
| 6. | Demo ink! upgradability and parachain flexibility without hard fork | Compare to Solidity smart contract upgrades | [Step-by-step Guide on ink! smart contract upgrde with screenshots](https://github.com/InkSmartContract/BlockchainFoodOrder/blob/V2/docs/BlockchainFoodOrder%20Step-by-step%20Guide%20Part2.pdf) | | 
| 7. | Articles | published Medium article on ink! smart contract upgrade flow, ease of upgradability and flexibility| [Medium article](https://medium.com/@opensmartcontract/learn-ink-by-example-part-2-upgrade-ink-smart-contracts-29ff34bd1b26)| All code and docs in [Github repository](https://github.com/InkSmartContract/BlockchainFoodOrder/tree/V2) under Apache2 license |

**Additional Information**

Quick redferences:

[Medium article](https://medium.com/@opensmartcontract/learn-ink-by-example-part-2-upgrade-ink-smart-contracts-29ff34bd1b26)

[Gihub code repo](https://github.com/InkSmartContract/BlockchainFoodOrder/tree/V2)
