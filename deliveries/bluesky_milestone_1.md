# Milestone Delivery :mailbox:

> ⚡ Only the GitHub account that submitted the application is allowed to submit milestones. 
> 
> Don't remove any of the mandatory parts presented in bold letters or as headlines! Lines starting with `>`, such as this one, can be removed.

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:**, please provide a link to the merged contract from the running buonty (the `.md` file in the [applications](https://github.com/smart-contract-bounty/Wasm-Bounty-01/tree/master/applications) directory).

[Bluesky project]()

**Context** (optional)
> Please provide a short paragraph or two connecting the deliverables in this milestone and describing their purpose.

In this [technical showcase](https://medium.com/@opensmartcontract/learn-ink-by-example-order-food-on-blockchain-a4024b2dee4a) we implemented with ink! smart contract language including custom macros, security, testing scripts, deployment and documents. It delivers the first milestone: define a specific use case: Order Food on Blockchain, implement in ink! with macros encapsulating reusable business logic, tested and deployed, then publish article to share with the community learning experiences / resources / recommendations about ink! and openBrush. 

**Deliverables**
> Please provide a list of all deliverables of the milestone extracted from the initial application and a link to the deliverable itself. Ideally all links inside the below table should include a commit hash, which will be used for testing. If you don't provide a commit hash, we will work off the default branch of your repository. Thus, if you plan on continuing work after delivery, we suggest you create a separate branch for either the delivery or your continuing work. 
> 
> If there is anything particular about any of the deliverables we or a future reader should know, use the respective `Notes` column.

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 1. | Define use case | [Food Order on Blockchain](https://medium.com/@opensmartcontract/learn-ink-by-example-order-food-on-blockchain-a4024b2dee4a) | define a contrived use case with [persona](https://docs.google.com/document/d/1yiZrPnSaz9myrXOrR2k2IALbJA9XcjeEJ-wCmhn3S3o/edit#heading=h.s7qu46re6cic), [workflow](https://docs.google.com/document/d/1yiZrPnSaz9myrXOrR2k2IALbJA9XcjeEJ-wCmhn3S3o/edit#heading=h.p52xmq7d7g3m), [target audiences](https://docs.google.com/document/d/1yiZrPnSaz9myrXOrR2k2IALbJA9XcjeEJ-wCmhn3S3o/edit#heading=h.y8aexxoud7oj) for ink! smart contract implementation |
| 2. | Investigate OpenZepplin's's security / ownership to see how it might fit | [OpenBrush vs openzeppelin on Ownable and AccessControl](https://docs.google.com/document/d/1yiZrPnSaz9myrXOrR2k2IALbJA9XcjeEJ-wCmhn3S3o/edit#heading=h.ahhyroiqktdx) | Implemented ownable for security and restaurants/coutier roles for access control |
| 3. | Define list of ink! Macros | Define declarative and procedure macros | 1) [Payment_macro](https://github.com/InkSmartContract/foodorder-smartcontract/blob/main/contracts/foodorder/logic/helpers/helpers.rs) as declarative macro; 2) [crud_macro](https://github.com/InkSmartContract/foodorder-smartcontract/tree/main/contracts/foodorder/crud-macro) as procedure macro encapsulating reusable logic to simplify code |
| 4. | Smart contracts | Implemented in ink! smart contract with macros] | [Github open source repository](https://github.com/InkSmartContract/foodorder-smartcontract.git) |
| 5. | End-to-end integration | [End-to-end integrate with testing scripts and results](https://docs.google.com/document/d/1yiZrPnSaz9myrXOrR2k2IALbJA9XcjeEJ-wCmhn3S3o/edit#heading=h.ni7dbbifqhne) | [Docker Image](https://hub.docker.com/repository/docker/fpleader/opensmartcontract/) |
| 6. | Deployment | Deploy smart contract to Shibuya (Shiden testnet) | [Step-by-step Contract Deployment and Interaction Guide](https://docs.google.com/document/d/1stF4dCXdT0fjPur23OD-eTZ90FdOq7tU8x2xEkoPojw/edit#heading=h.iq3vnposvacy) |
| 7. | Article |[ Article published in Medium](https://medium.com/@opensmartcontract/learn-ink-by-example-order-food-on-blockchain-a4024b2dee4a) | covers comprehensive topics and next steps |

**Additional Information**
> Any further comments on the milestone that you would like to share with us.
> 
Quick references:

* [[Learn ink! by Example - Order Food on Blockchain](https://medium.com/@opensmartcontract/learn-ink-by-example-order-food-on-blockchain-a4024b2dee4a)
* [[ink! Smart Contract Deployment and Interactions]](https://docs.google.com/document/d/1stF4dCXdT0fjPur23OD-eTZ90FdOq7tU8x2xEkoPojw/edit#heading=h.iq3vnposvacy)
* [Open source github repo](https://github.com/InkSmartContract/foodorder-smartcontract.git)
* [Docker Image](https://hub.docker.com/repository/docker/fpleader/opensmartcontract/)

The project delivers part 1, fully open sourced and [documented]() with Apache 2.0 license, to share with both web2 and web3 developer communities. This is the first of a three parts post covering the use case, ink! implementation with macros. For next steps, the upcoming part 2 on upgradability, and part3 to benchmark the performance, quantify binary footprints and optimize gas costs in various ink! optimization variations. 

