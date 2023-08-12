# Milestone Delivery :mailbox:

> ⚡ Only the GitHub account that submitted the application is allowed to submit milestones. 
> 
> Don't remove any of the mandatory parts presented in bold letters or as headlines! Lines starting with `>`, such as this one, can be removed.

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**  

* **Application Document:**, please provide a link to the merged contract from the running buonty (the `.md` file in the [applications](https://github.com/smart-contract-bounty/Wasm-Bounty-01/tree/master/applications) directory).

[Bluesky project]()

**Context** (optional)
> Please provide a short paragraph or two connecting the deliverables in this milestone and describing their purpose.

In this [technical showcase]() we implemented with ink! smart contract language including custom macros, security, testing scripts, deployment and documents. It delivers the first milestone: define a specific use case [Order Food on Blockchain](), implement in ink! with macros encapsulating reusable business logic, tested and deployed, then publish article to share with the community learning experiences / resources / recommendations about ink! and openBrush. 

**Deliverables**
> Please provide a list of all deliverables of the milestone extracted from the initial application and a link to the deliverable itself. Ideally all links inside the below table should include a commit hash, which will be used for testing. If you don't provide a commit hash, we will work off the default branch of your repository. Thus, if you plan on continuing work after delivery, we suggest you create a separate branch for either the delivery or your continuing work. 
> 
> If there is anything particular about any of the deliverables we or a future reader should know, use the respective `Notes` column.

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 1. | Define use case | [Food Order on Blockchain]() | define a contrived use case with [persona](), [workflow](https://docs.google.com/document/d/1yiZrPnSaz9myrXOrR2k2IALbJA9XcjeEJ-wCmhn3S3o/edit#heading=h.p52xmq7d7g3m), [target audiences](https://docs.google.com/document/d/1yiZrPnSaz9myrXOrR2k2IALbJA9XcjeEJ-wCmhn3S3o/edit#heading=h.y8aexxoud7oj) for ink! smart contract implementation |
| 2. | Investigate OpenZepplin's's security / ownership to see how it might fit | [Compare openBrush vs openzeppelin on Ownable and AccessControl]() | Implemented ownable for security and restaurants/coutier roles for access control in this example |
| 3. | Define list of ink! Macros | [Define and implemented macros]() | 1) [Payment_macro]() as declarative macro [code](); 2) [Food_crud_macro]() as procedure macro encapsulating reusable logic to simplify [code]() |
| 4. | Smart contracts | [Implemented in ink! smart contract with macros]() | [Github code repository]() with Apache 2.0 license |
| 5. | End-to-end integration | [End-to-end integrate with testing scripts and results](https://docs.google.com/document/d/1yiZrPnSaz9myrXOrR2k2IALbJA9XcjeEJ-wCmhn3S3o/edit#heading=h.ni7dbbifqhne) | [Docker]() |
| 6. | Deployment | [Deploy smart contract to Shibuya (Shiden testnet)]() | Deployed to [Shibuya]() [Deployment amd interaction step-by-step guide]() |
| 7. | Article | [article]() published in public web3 media (mirror.xyz) | covers comprehensive topics including [sharing learning resources](https://docs.google.com/document/d/1yiZrPnSaz9myrXOrR2k2IALbJA9XcjeEJ-wCmhn3S3o/edit#heading=h.83wclhirwiww),[ recommendations and next steps]() |

**Additional Information**
> Any further comments on the milestone that you would like to share with us.
> 
Quick references:

* [Learn ink! - Order Food on Blockchain]()
* [ink! Smart Contract Deployment and Interactions]()
* [FoodOrder open source github repo]()

The project delivers part 1, fully open sourced and [documented]() with Apache 2.0 license, to share with both web2 and web3 developer communities. This is the first of a three parts post covering the use case, ink! implementation with macros. For [next steps](), the upcoming part 2 on upgradability, and part3 to benchmark the performance, quantify binary footprints and optimize gas costs in various ink! optimization variations. 

