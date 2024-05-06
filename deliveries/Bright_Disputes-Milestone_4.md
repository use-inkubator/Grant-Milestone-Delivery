# Milestone 4 Delivery :mailbox:

* **Application Document:** https://github.com/bright/Ecosystem-Grants/blob/6a756f94bca60bc3d3bcbed64baf11675a5b1eca/applications/Bright_Disputes.md

**Context** (optional)

Bright Disputes is a dApp for solving disputes. Our goal is to create a smart contract (written in ink!) which could be used to raise and solve disputes on the Substrate-based blockchains. We would like to leverage a Zk-Snarks to accomplish privacy of voting.

**Deliverables**

| Number | Deliverable | Link | Notes |
| -----: | ----------- |----------- | ------------- |
| **0a.** | License |[LICENSE](https://github.com/bright/bright-disputes/blob/main/LICENSE) | MIT |
| **0b.** | Documentation | [README](https://github.com/bright/bright-disputes-showcase/blob/main/README.md) | We will provide **inline documentation** of the code. |
| **0c.** | Testing and Testing Guide | [README](https://github.com/bright/bright-disputes-showcase/blob/main/README.md) | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | - | Omitted due to the lack of extensive prerequisites. |
| **0e.** | Article | [blog post](https://brightinventions.pl/blog/the-bright-disputes-showcase/) |An **article** that explains how to use the BrightDispute user interface.  |
| **0f.** | YouTube video | [video](https://www.youtube.com/watch?v=x8cfKKUvQls)| A **tutorial video** that explains how to use the BrightDispute user interface and how the solution behind it. 
| 1. | Add new dispute |[source code](https://github.com/bright/bright-disputes-showcase/blob/main/app/routes/dispute.create/route.tsx) | In the Showcase app, we utilize predefined, prefunded accounts instead of individual users' Polkadot accounts. This approach is designed to make the process of switching between personas involved in the dispute more convenient and streamlined. With those account user can create a new dispute, specifying who's a part of the dispute and adding a link to an external service (description of the case)
| 2. | Add defending info | [source code](https://github.com/bright/bright-disputes-showcase/blob/main/app/routes/dispute.%24id.defendant/route.tsx) | Once a dispute is created, a defendant of the dispute can present their own side of the case (adding a link to the external service).
| 3. | Follow the status of the dispute | [source code](https://github.com/bright/bright-disputes-showcase/blob/main/app/routes/dispute.%24id._index/route.tsx)| Both sides of the dispute can follow the status of the dispute status and outcome.
| 4. | Application to the jury pool | [source code](https://github.com/bright/bright-disputes-showcase/blob/main/app/routes/_index/route.tsx)| A user, after loging in with their wallet address, can request to become a part of the jury pool.
| 5. | Confirm jury role in a case  | [source code](https://github.com/bright/bright-disputes-showcase/blob/main/app/routes/dispute.%24id._index/route.tsx)| For each case, a jury is randomly selected from the jury pool. A user selected for a specific case should confirm their participation in order to take part in the case.
| 6. | Vote on a case  | [source code](https://github.com/bright/bright-disputes-showcase/blob/main/app/routes/dispute.%24id._index/route.tsx)| A jury member that confirmed their participation in a case is expected to vote in a voting round.
