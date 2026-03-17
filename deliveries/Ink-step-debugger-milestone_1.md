# Milestone Delivery :mailbox:

* **Application Document:**
https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/ink-step-debugger.md

---

**Context**

The goal of Milestone 1 was to research DRink!, PolkaVM, and the tracing APIs in `pallet-revive`, set up an off-chain sandbox execution, and define the core architecture of the debug adapter.  
This establishes a working foundation: a prototype adapter capable of launching a debug session and executing a contract to completion, plus a sandbox rpc with logging each Step execution.

---

**Deliverables**

| Number | Deliverable                 | Link                                                                                                                                                    | Notes |
|-------:|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------|
| 1.     | **License (MIT)**           | https://github.com/last-dot/Ink-Step-Debugger/blob/main/LICENSE                                                                                         | MIT published in root |
| 2.     | **Docs**                    | https://github.com/last-dot/Ink-Step-Debugger/blob/main/Guide.md <br> https://github.com/last-dot/Ink-Step-Debugger/blob/main/README.md                 | Architecture overview; local sandbox setup; VS Code launch |
| 3.     | **Adapter prototype**       | https://github.com/last-dot/Ink-Step-Debugger/tree/main/ink-trace-extension <br> https://github.com/last-dot/Ink-Step-Debugger/tree/main/ink-dap-server | Rust DAP server binary; VS Code extension launches it directly via `DebugAdapterExecutable`; handles initialize / launch / threads / stack trace / disconnect |
| 4.     | **Breakpoint architecture** | https://github.com/last-dot/Ink-Step-Debugger/blob/main/ink-debug-rpc/src/sandbox_rpc.rs                                                               | PC logged on every step; breakpoint lines set in VS Code are received and stored by the DAP server — this validates the full communication path (VS Code → DAP server → sandbox → DAP server → VS Code); actual execution pause on hit is planned for M2 |
| 5.     | **Contract run in sandbox** | https://github.com/last-dot/Ink-Step-Debugger/tree/main/ink-debugger <br> https://github.com/last-dot/Ink-Step-Debugger/blob/main/ink-debug-rpc         | DRink!-based or custom PolkaVM sandbox for isolated execution |

---

**Additional Information**

- Tested on Ink! v6 toolchain, PolkaVM interpreter mode.
- The adapter currently focuses on end-to-end execution and PC logging. Stepping and breakpoint hit handling are planned for Milestone 2.
- A reproducible demo run and expected logs are documented in [Guide.md](https://github.com/last-dot/Ink-Step-Debugger/blob/main/Guide.md).
- The DAP server must be built before launching the extension: `cd ink-dap-server && cargo build --release`.
