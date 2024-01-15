# Milestone Delivery :mailbox:

**The invoice has been sent out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**

- **Application Document:** [Ink Multisig](https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/ink_contract_multi-sig.md)

**Context**

After developing the proof-of-concept, we refined the Xsigners multisig smart contract and added more tests to validate functionality. We then focused our efforts on crafting an intuitive user interface that makes signing transactions and viewing account activity easy and enjoyable.

Given our decentralized approach without a backend server, we indexed blockchain data using a squid to power the front-end UI with real-time account information, transaction statuses, and notifications. This was challenging due to limitations in existing tooling, but we devised innovative workarounds.

The end result is a robust, community-driven multisig that offers class-leading usability. Xsigners delivers the features that are expected from every multisig without sacrificing ease-of-use.

The Xsigners project showcases our team's strengths in smart contract engineering, frontend development, and creating delightful yet secure user experiences. We could not be more thrilled with the final product in our quest to drive decentralized financial adoption through pragmatic innovation.

We have a live version of the Xsigners contracts deployed on the Shibuya Testnet, which can be interacted with through the web interface at [xsigners.io](https://xsigners.io)

**Deliverables**

| Number  | Deliverable               | Link                                                                                                                                          | Notes                                                                                                                                                                                                                  |
| ------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **0a.** | License                   | https://github.com/protofire/ink-multisig/blob/main/LICENSE / https://github.com/protofire/ink-multisig-ui/blob/main/LICENSE               |                                                                                                                                                                                                                        |
| **0b.** | Documentation             | https://github.com/protofire/xs-doc                                                                                                           | The documentation is accessible from the Docs tab in the app.                                                                                                                                                           |
| **0c.** | Testing and Testing Guide | https://github.com/protofire/ink-multisig/blob/main/README.md                                                                                 |                                                                                                                                                                                                                        |
| **0d.** | Docker                    | https://github.com/protofire/ink-multisig-ui/blob/develop/docker-compose.yml                                                                  |                                                                                                                                                                                                                        |
| 1.      | Figma file                | https://www.figma.com/file/9yvUVBlRE2CPfVw0rtDZ21/XSigners---Multisig-(Community)?type=design&node-id=9%3A38&mode=design&t=iG4c1byvfJk7aEdb-1 |                                                                                                                                                                                                                        |
| 2.      | Multisig Smart Contract   | https://github.com/protofire/ink-multisig                                                                                                     |                                                                                                                                                                                                                        |
| 3.      | Multisig UI               | https://github.com/protofire/ink-multisig-ui / https://github.com/protofire/ink-multisig-squid-shibuya                                        | The squid serves as a vital component, responsible for retrieving and processing data from the blockchain. Its primary function is to supply the UI with real-time information, enhancing the overall user experience. |
| 4.      | Report about the backend  | https://docs.xsigners.io/blog/implementation                                                                                                  |                                                                                                                                                                                                                        |
