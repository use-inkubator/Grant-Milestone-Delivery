# Milestone 3 Delivery :mailbox:

* **Application Document:** https://github.com/bright/Ecosystem-Grants/blob/6a756f94bca60bc3d3bcbed64baf11675a5b1eca/applications/Bright_Disputes.md

**Context** (optional)

Bright Disputes is a dApp for solving disputes. Our goal is to create a smart contract (written in ink!) which could be used to raise and solve disputes on the Substrate-based blockchains. We would like to leverage a Zk-Snarks to accomplish privacy of voting.

**Deliverables**

| Number | Deliverable | Link | Notes |
| -----: | ----------- |----------- | ------------- |
| **0a.** | License |[LICENSE](https://github.com/bright/bright-disputes/blob/main/LICENSE) | MIT |
| **0b.** | Documentation | [SHOWCASE](https://github.com/bright/bright-disputes/blob/main/doc/README.md) / [SHOWCASE_CLI](https://github.com/bright/bright-disputes/blob/main/doc/README_CLI.md) / [README](https://github.com/bright/bright-disputes/blob/main/README.md) | We will provide **inline documentation** of the code. |
| **0c.** | Testing and Testing Guide | [README](https://github.com/bright/bright-disputes/blob/main/README.md) | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | [Dockerfile](https://github.com/bright/bright-disputes/blob/main/docker/Dockerfile) | Dockerfile that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | [blog post](https://brightinventions.pl/blog/dispute-resolution-solution-in-blockchain-with-bright-disputes/) |An **article** that explains the dispute resolution solution.  |
| 1. | Smart contract | [contract.rs](https://github.com/bright/bright-disputes/blob/main/contract/src/contract.rs)| Modify a smart contract to accomplish a private voting goal, by encrypting votes using Judge's public key and signing them with their private keys.
| 2. | Smart contract |[contract.rs](https://github.com/bright/bright-disputes/blob/main/contract/src/contract.rs) | Modify smart contract with the private vote counting and zk-snarks.
| 3. | CLI | [README](https://github.com/bright/bright-disputes/blob/main/cli/README.md) | Extend CLI to use created relations from the Milestone 2.
| 4. | Script | [deploy.sh](https://github.com/bright/bright-disputes/blob/main/scripts/deploy.sh)| Extend `deploy` script to accomplish for the smart contract (ex: generate veryfications / proving keys)