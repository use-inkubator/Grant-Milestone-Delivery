# Milestone Delivery :mailbox:




* **Application Document:** https://github.com/bright/Ecosystem-Grants/blob/6a756f94bca60bc3d3bcbed64baf11675a5b1eca/applications/Bright_Disputes.md

**Context** (optional)

Bright Disputes is a dApp for solving disputes. Our goal is to create a smart contract (written in ink!) which could be used to raise and solve disputes on the Substrate-based blockchains. We would like to leverage a Zk-Snarks to accomplish privacy of voting.

**Deliverables**





| Number | Deliverable | Link | Notes |
| -----: | ----------- |----------- | ------------- |
| **0a.** | License |[LICENSE](https://github.com/bright/bright-disputes/blob/main/LICENSE) | MIT |
| **0b.** | Documentation | [README](https://github.com/bright/bright-disputes/blob/main/doc/README.md) | We will provide **inline documentation** of the code. |
| **0c.** | Testing and Testing Guide | [README](https://github.com/bright/bright-disputes/blob/main/README.md) | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | [Dockerfile](https://github.com/bright/bright-disputes/blob/main/docker/Dockerfile) | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 1. | Repository | [github](https://github.com/bright/bright-disputes/blob/main) | We will create a GitHub repository for Dispute project.
| 2. | Smart contract | [contract.rs](https://github.com/bright/bright-disputes/blob/main/contract/src/contract.rs) | Create a smart contract according to documentation, where voting is public.
| 3. | Script | [deploy.sh](https://github.com/bright/bright-disputes/blob/main/scripts/deploy.sh) | Create a `deploy` script, it will allows to setup the local environment (run aleph-node, deploy smart contract)
