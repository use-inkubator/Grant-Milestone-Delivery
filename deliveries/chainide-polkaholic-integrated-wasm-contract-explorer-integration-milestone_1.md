# Milestone Delivery :mailbox:


- **Application Document:** [https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/chainide-polkaholic-integrated-wasm-contract-explorer-integration.md](https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/chainide-polkaholic-integrated-wasm-contract-explorer-integration.md)

**Context**

[ChainIDE](https://chainide.com/) is a development environment for EVM Contracts being extended to include WASM Contract templates.

[Polkaholic.io](https://polkaholic.io/), developed by Colorful Notion, is a multichain block explorer for the Substrate ecosystem covering 75+ chains.




## Milestone 1 Deliverables

In Summer 2023, ChainIDE and Colorful Notion worked to ChainIDE+Polkaholic.io to support WASM Contract Developers with a fully integrated WASM Contract Development platform in Milestone 1.  Key results from this Milestone are:
* a complete WASM Contract Development platform from ChainIDE
* a full set of WASM Contract Templates: Flipper, PSP22, PSP34, UniswapV2, and more
*  WASM Contract Verification APIs
*  WASM Contract Developer Dashboards
*  WASM Contract API from Polkaholic.io
*  WASM Contract UI from Polkaholic.io

WASM Contract Developer feedback (new features) will be requested in October 2023 from Milestone 1 Deliverables and used to draft a Milestone 2 follow-on proposal.
| Number | Deliverable | Link | Notes |
| --- | --- | --- | --- |
| 0a. | License | [Polkaholic GNU GPL v3](https://github.com/colorfulnotion/polkaholic/blob/main/LICENSE) |   |
| 0b. | Polkaholic Documentation | See 0b. Polkaholic Documentation below  | See Polkaholic screenshots and URLs |
| 0c. | Testing and Testing Guide | See 0c. below | See ChainIDE video walkthrough |
| 1. | Repository | https://github.com/colorfulnotion/polkaholic  |  |
| 2. | Repository | https://staging-9589904a8a.chainide.com/s/dashboard/projects | ChainIDE is only semi-open source. This is [the open-source plugin template for ChainIDE](https://github.com/WhiteMatrixTech/chainide-plugin-doc). If you need other open-source plugins, please let us know. |

## 0b. Polkaholic Documentation

* Colorful Notion indexes [Shibuya](https://polkaholic.io/blocks/shibuya), [Shiden](https://polkaholic.io/blocks/shiden), and [Astar](https://polkaholic.io/blocks/astar) in its Polkaholic.io block explorer.  In particular, WASM Contract indexing and decoding processes are documented inline in its [Astar chain parser](https://github.com/colorfulnotion/polkaholic/blob/main/substrate/chains/astar.js) which is used for any chain that has been flagged with WASM capabilities.   See `astar.js` for inline documentation.

* The Polkaholic.io **WASM Contract Verification API** is exposed here:
   - API Endpoint: [https://api.polkaholic.io](https://api.polkaholic.io)
   - Swagger Endpoint test: [https://swagger.polkaholic.io/](https://swagger.polkaholic.io/)
   - [swagger.json](https://github.com/colorfulnotion/polkaholic/blob/main/substrate/schema/swagger.json)
  - Full documentation:  [WASM Contract Verification API](https://github.com/colorfulnotion/polkaholic/blob/main/WASM-Verifier.md) (based on [Summer 2023 Design docs](https://docs.google.com/document/d/1Uq_fRBYhHCvtdjlIcxGPYmGZ9cNRV7dKvvXwfBbQbnQ/edit))

   The primary user of this is an IDE (ie ChainIDE), but could be additional trusted IDEs.  We determined only 2 endpoints were needed:
	 1. `/verify/{network}/{codeHash}` Verifies a source code package compiled in an IDE such as this flipper.zip  
	 2. `/info/{network}/{codeHash}` Gets information on verification status of  uploaded source code.

	Contracts indexed by Polkaholic are considered Unknown until the IDE (in this work, ChainIDE) hits the `verify` endpoint with a signed code hash.  The ChainIDE is required to pass a `signature` parameter to `verify` using its ECDSA private key signing the codehash, and Polkaholic will consider the build verified if the address recovered matches a whitelist of addresses.  Multiple IDEs and trusted verifiers can be whitelisted.  Should any verifier's key be compromised, all contracts from the point of compromise should be considered Unverified.  

	Sample `verify` call:
	```
	curl -X POST -F "package=@flipper.zip" -F "signature=0xe209e220e80cc196f033e48a9e4a9bb178144372cdefb711a0ba211a1013fc3171d3b537fd3c3d2716753d664b7c6b3a3f887738672d484efd5d7da73bda89f71b" https://api.polkaholic.io/verify/shibuya/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0
	 {"success":true,"network":"shibuya","codeHash":"0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0","chainID":30000,"srcURLs":["https://cdn.polkaholic.io/wasmcode/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0/flipper.zip","https://cdn.polkaholic.io/wasmcode/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0/src/Cargo.lock","https://cdn.polkaholic.io/wasmcode/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0/src/Cargo.toml","https://cdn.polkaholic.io/wasmcode/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0/src/lib.rs","https://cdn.polkaholic.io/wasmcode/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0/flipper.contract"],"infoURL":"https://api.polkaholic.io/info/shibuya/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0"}
	```

	Sample `info` call:

	[https://api.polkaholic.io/info/shibuya/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0](https://api.polkaholic.io/info/shibuya/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0)


### ChainIDE-Polkaholic Verification Build Process: from Milestone 1 to Milestone 2

ChainIDE uses a containerized build process, where tiny variations in configuration may result in different codehashes.  This is acceptable for the above security model where ChainIDE is currently assumed to be a trusted IDE.   However, to standardize WASM Contract compilation such that multiple parties (in particular Colorful Notion and ChainIDE as well as others) can use identical build processes to derive the exact same code hash, in July 2023 Parity released the following  "cargo contract build --verifiable" functionality:
**[https://github.com/paritytech/cargo-contract/releases/tag/v4.0.0-alpha](https://github.com/paritytech/cargo-contract/releases/tag/v4.0.0-alpha)**
The official version is expected to be launched by the end of the year.  Both teams researched the usability of this (ChainIDE to incorporate into its build process, Polkaholic to replicate and arrive).   See issue [here](TODO).

We propose to collaborate _with Parity's assistance_ in Milestone 2 using this verifiable build process, wherein:
* ChainIDE will use Parity's "cargo contract build --verifiable" process, and use the same `/verify` API endpoint
* Polkaholic will verify the uploaded code using its the identical "--verifiable" process



### Polkaholic.io API for WASM Contracts

The [Polkaholic.io API](https://docs.polkaholic.io/#introduction) has been extended to include the following WASM Contract APIs at the same REST API Endpoint of [https://api.polkaholic.io](https://api.polkaholic.io) to enable anyone to access data about a network and contract address with simple `{network}` and `{contractAddress}` parameters.

|Function|REST API Format|Example|
|---|---|--|
|Retrieve indexed code hashes by code hash | https://api.polkaholic.io/wasmcode/`{network}` | https://api.polkaholic.io/wasmcode/shiden |
|Retrieve contract addresses | https://api.polkaholic.io/wasmcontracts/`{network}` | https://api.polkaholic.io/wasmcontracts/shibuya |
|  Retrieve contract calls of a contract address |  https://api.polkaholic.io/wasmcontract/`{network}`/`{contractAddress}`  | https://api.polkaholic.io/wasmcontract/shiden/XRcGZzdH841dHySiM62BfJDbQfXXYex3U7LYooRJt8EgJeX |


### Polkaholic.io UI for WASM Contracts

The [Polkaholic.io  UI](https://polkaholic.io) has been enhanced to support URL parametric access by code hash, contractAddress or extrinsicHash to support the following functions:

|Function|URL|Example|
|-----|----|----|
| Access the WASM code (by WASM code hash) | https://polkaholic.io/wasmcode/`{codehash}` | [screenshot](https://cdn.polkaholic.io/inkubator-m1/wasmcode-ui.png) [Example](https://polkaholic.io/wasmcode/0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0) |
| Access the WASM contract (by WASM contract address) | https://polkaholic.io/wasmcontract/`{contractAddress}` | [screenshot](https://cdn.polkaholic.io/inkubator-m1/wasmcontract-ui.png) [Example](https://polkaholic.io/wasmcontract/XRcGZzdH841dHySiM62BfJDbQfXXYex3U7LYooRJt8EgJeX)
| Access the WASM contract calls (by Substrate extrinsic hash) |  https://polkaholic.io/tx/`{extrinsicHash}` | [screenshot](https://cdn.polkaholic.io/inkubator-m1/tx-ui.png) [Example](https://shibuya.polkaholic.io/tx/0x4d0461f63da912503c7355db5a79c0e285773c66a383a7d9922b8c4a0852ef33)

This the above can used by any UI (e.g. the ChainIDE, dashboard).  In addition, users can search by the same keys in the Polkaholic.io search bar, e.g.
* 0x396418ff533172de8407004f53051b5409f6892564ddeba12f75cc855cb16fe0
* XRcGZzdH841dHySiM62BfJDbQfXXYex3U7LYooRJt8EgJeX
* 0x4d0461f63da912503c7355db5a79c0e285773c66a383a7d9922b8c4a0852ef33

### Polkaholic.io WASM developer dashboard

The Polkaholic.io WASM developer dashboard was built using [Apache Superset](https://superset.apache.org/), a popular open-source modern data exploration and visualization platform that is hosted at

https://analytics.polkaholic.io

This is connected to Colorful Notion's [substrate-etl](https://github.com/colorfulnotion/substrate-etl) with BigQuery as well as the Polkaholic MySQL replica.  

Many dashboards can be built in Superset very rapidly (with no "front end engineering"), but for Milestone 1 we built two core dashboards, with `{network}` and `{developerAddress}` URL parameters:

|Function|URL|Example|
|------|----|----|
| WASM Contract Activity for one network, across all developers | https://analytics.polkaholic.io/superset/dashboard/20/?network=`{network}`&standalone=2 | https://analytics.polkaholic.io/superset/dashboard/20/?network=shibuya&standalone=2 [screenshot](https://cdn.polkaholic.io/inkubator-m1/dashboard20.png)
| WASM Contract Activity for specific developer on one network |  https://analytics.polkaholic.io/superset/dashboard/57/?network=`{network}`&developer=`{developerAddress}`&standalone=2  |  https://analytics.polkaholic.io/superset/dashboard/57/?network=shibuya&developer=afAEAGz4MVRQjkqUuaUTCU9nTPHruE5xfvazKzPs4kndwso&standalone=2  [screenshot](https://cdn.polkaholic.io/inkubator-m1/dashboard57.png)

ChainIDE integrated both of the above dashboards with IFRAMEs and used the CSS customization capabilities to match its Dark Mode.

It is expected that additional dashboards can be done for other purposes (e.g. a line chart showing # of calls, contracts verified, etc. by day/month/quarter, by network etc.) for other contexts.  The same Superset can be used to expose these in Polkaholic.io, as well support many other blockchain analytics problems.    

## 0c. Testing and Testing Guide

The ChainIDE-Polkaholic unit tests are comprehensively demonstrated in the following video link:

[Comprehensive ChainIDE Walkthrough, including Polkaholic.io integration (Video Link)](https://www.dropbox.com/scl/fi/tf0jgxsmss5b52uk0nbw7/Astar-ChainIDE-M2-New.mp4?rlkey=ts3tpvzvxpbfg7wrl7f4va1yl&dl=0)

Any WASM Contract developer can preview:

[ChainIDE WASM Contract Development Preview - September 2023](https://staging-9589904a8a.chainide.com/s/dashboard/projects) (Note: to be finalized in October!)


#### WASM Highlights of the above process:

Both WASM + EVM Contracts are seen in the above, with key highlights

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
- The "ChainIDE" section in [Key integration points.](https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/chainide-polkaholic-integrated-wasm-contract-explorer-integration.md?plain=1#L110)
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

### Network Support: from Milestone 1 to Milestone 2

This project was completed and tested mostly on Shibuya but the following chains are supported by both teams:

| {network} | Relay Chain / Para ID | Integration |  
|----|---|---|
| `astar` | Polkadot / 2006 | Milestone 1 |
| `shiden` | Kusama / 2007 |  Milestone 1 |
| `shibuya` | Testnet | Milestone 1 |
| `rococo-contracts` | Rococo / 1002 | Milestone 2 possible (Note: Parity support required due to low numbers of peers, syncing halted) |

ChainIDE contains the ability to add arbitrary chains, while Polkaholic.io is able to add additional chains upon request in Milestone 2 based on community feedback.

### Current Status / Future Plans

Both teams will complete Milestone 1 in September and are developing plans to propose Milestone 2 in November, after using October as a feedback collection period.  

Here is the detailed timeline:
* September 2023 - ChainIDE is awaiting QA from Colorful Notion while Astar is currently undergoing acceptance testing.  Colorful Notion is completing this document and finalizing functionality for a developer preview in October 2023.

* *October 2023* - ChainIDE + Colorful Notion  request feedback from curators, all inkubator WASM Contract Developers and experienced WASM Contract Developers to:

	1. Try ChainIDE at [https://staging-9589904a8a.chainide.com/s/dashboard/projects](https://staging-9589904a8a.chainide.com/s/dashboard/projects) using Shibuya and the SBY faucet.   We recommend using PSP22, PSP34 or the UniswapV2 contract templates, and then using your own WASM Contract.  

	2. For bug reports and feature requests, submit them [here](TODO) or join our open group here [ChainIDE+Colorful Notion+Astar]()  

*  _November 2023_ - ChainIDE + Colorful Notion will submit a follow up Milestone 2 proposal based on everyones feedback accumulated in October.

*  _December 2023-March 2024_ - Milestone 2 work (if approved).
