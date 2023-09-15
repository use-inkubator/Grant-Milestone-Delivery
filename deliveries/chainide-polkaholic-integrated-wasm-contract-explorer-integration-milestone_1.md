# Milestone Delivery :mailbox:

**The invoice has been send out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/smart-contract-bounty/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**

- **Application Document:** [https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/chainide-polkaholic-integrated-wasm-contract-explorer-integration.md](https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/chainide-polkaholic-integrated-wasm-contract-explorer-integration.md)

**Context** 

[ChainIDE](https://chainide.com/) is a development environment for EVM Contracts being extended to include WASM Contract templates. See [this video link](https://www.dropbox.com/scl/fi/tf0jgxsmss5b52uk0nbw7/Astar-ChainIDE-M2-New.mp4?rlkey=ts3tpvzvxpbfg7wrl7f4va1yl&dl=0)  ([Testnet url](https://staging-9589904a8a.chainide.com/s/dashboard/projects)) for a full demonstration of ChainIDE's usage for EVM + WASM Contract Development.

[Polkaholic.io](https://polkaholic.io/), developed by Colorful Notion, is a multichain block explorer for the Substrate ecosystem covering 75+ chains, including parachains Astar/Shiden + Amplitude/Pendulum. Data from Polkaholic is exposed in substrate-etl's "contracts" dataset. See [this link](https://analytics.polkaholic.io/superset/dashboard/021154ed-efe1-4538-a177-30ae5ef59911/) for a PoC of Polkaholic's WASM Contract Explorer.

These 2 teams propose to provide the above well-integrated EVM development for WASM Contract Developers for all Substrate chains using the *contracts* pallet. Initial milestones by ChainIDE to cover WASM Contracts have been completed while Colorful Notion has done the groundwork to decode+index WASM Contracts.

**Deliverables**

| Number | Deliverable | Link | Notes |
| --- | --- | --- | --- |
| 0a. | License | ... | ... |
| 0b. | Polkaholic Documentation | ... | ... |
| 0c. | Testing and Testing Guide |  |  |
| 1. | Repository |  |  |
| 2. | Repository | https://staging-9589904a8a.chainide.com/s/dashboard/projects | Please note that due to the nature of ChainIDE being semi-open source, some of its underlying functions are not open sourced. Hence, we cannot provide a opensource repository link. Thanks |

**Additional Information**

ChainIDE has currently completed the following tasks:

Using WASM:

- Code sage (AI-Code-Assistant). 00:39
- In ChainIDE-sandbox, we provide customized images that contain Astar Swanky Suite and Node.js. 02:40
- Plugins and panels on the front end:
    - Compilation of Substrate smart contracts, including compilation support for Rust (ink). 02:06
    - Provide an interactive user interface to configure and quickly start a local development node. 03:30
    - Implemented a built-in wallet plugin that utilizes a set of services written by Polkdot's SDK to provide APIs such as network connection, account management, and contract deployment interaction (Mainnet, Testnet, & Devnet). 04:07
    - Wallet panel, manage network connection, account information. 04:46
    - Select the compiled contract to deploy to the Astar Network in the deployment panel. 09:37
    - Interaction panel to interact with deployed contracts. 10:32
    - Log viewer. 10:51
    - Support for four wallets: Polkadot, SubWallet, Math Wallet, and Talisman. 13:56
    - Support for Use On-Chain Contract Code and Import Deployed Contract. 22:13
- **The "ChainIDE" section in "[Key integration points.](https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/chainide-polkaholic-integrated-wasm-contract-explorer-integration.md?plain=1#L110)”**
    - Integrated WASM Developer dashboard (as an iframe), or direct link to the dashboard using the developer's wallet address; this can be used to link any developer dashboard. 07:26
    - Ask whether developers wish to (a) share the ABI/metadata (b) have their code verified and submitted for open source. 13:04
    - Use cases to post user's contract-related data. 13:15
    - A link to the contract call will take users to Polkaholic.io using the extrinsicHash generated. 15:15

Using EVM:

- A pre-built Linux container image includes a set of Hardhat, Truffle, and Node.js in ChainIDE-sandbox at the backend. 29:32
- An Astar EVM dashboard in the front end:
    - A wallet panel that allows users to connect MetaMask wallet in the browser switch to the mainnet, testnet, and devnet; mint testnet & devnet coin. 30:04
    - Compilation of Substrate smart contracts, including compilation support for Solidity. 30:48
    - Select the compiled contract to deploy to Astar Network. 31:13
    - Interact with the deployed contracts. 31:47
    - Monitor Astar Network backend real-time activities. 32:05
    - Includes some useful plugins: JavaScript Virtual Machine Wallet (JSVM), Flattener, & Debugger. 32:48

Video Link: 
[https://www.dropbox.com/scl/fi/tf0jgxsmss5b52uk0nbw7/Astar-ChainIDE-M2-New.mp4?rlkey=ts3tpvzvxpbfg7wrl7f4va1yl&dl=0](https://www.dropbox.com/scl/fi/tf0jgxsmss5b52uk0nbw7/Astar-ChainIDE-M2-New.mp4?rlkey=ts3tpvzvxpbfg7wrl7f4va1yl&dl=0)

Due to **[https://staging-9589904a8a.chainide.com/s/dashboard/projects](https://staging-9589904a8a.chainide.com/s/dashboard/projects)** being a testing version, Astar is currently undergoing acceptance testing. We anticipate completing the acceptance testing. We can discuss the production release date with you as you are interested in knowing it first, so that their PR team can plan the marketing. Additionally, we've noticed that **[https://github.com/paritytech/cargo-contract/releases/tag/v4.0.0-alpha](https://github.com/paritytech/cargo-contract/releases/tag/v4.0.0-alpha)** has been released, and the official version is about to be launched. In order to support this new feature "cargo contract build --verifiable," we will be collaborating with Polkaholic. Therefore, we propose Milestone 2 (This link will be updated).
