# Milestone Delivery :mailbox:

**The invoice has been sent out correctly for this milestone and the delivery is according to the official [milestone delivery guidelines](https://github.com/use-inkubator/Support-Docs/blob/master/milestone-deliverables-guidelines.md).**

* **Application Document:** https://github.com/use-inkubator/Ecosystem-Grants/blob/master/applications/monsters_ink.md
* **Milestone Number:** 2

---

## Context

Milestone 2 delivers the core educational platform: a JSON lesson framework with Zod validation, a browser-based Monaco IDE for ink! development, a production-grade Dockerized code compilation server, and a complete NFT progression system powered by AssetHub.

Beyond the original scope, we built a **durable workflow engine** (Vercel Workflows) for reliable monster generation and NFT minting, a **graphical lesson editor** for content creators, and UX enhancements including an animated feedback character (Squink) and sound system.

**Live Platform:** https://monsters-prod.vercel.app/
**Video Showcase:** [Loom Recording](https://www.loom.com/share/e99c88107dd94df9ab271f57060d555d)
**Full Technical Details:** [M2 Report](https://github.com/forever8896/inkverse/blob/main/docs/M2_REPORT.md)

---

## Deliverables

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 0a. | License | [Apache License 2.0](https://github.com/forever8896/inkverse/blob/main/LICENSE.txt) | Apache License 2.0 |
| 0b. | Documentation | [M2 Report](https://github.com/forever8896/inkverse/blob/main/docs/M2_REPORT.md), [Lesson Content Guide](https://github.com/forever8896/inkverse/blob/main/docs/LESSON_CONTENT_GUIDE.md), [Contributing Lessons](https://github.com/forever8896/inkverse/blob/main/docs/CONTRIBUTING_LESSONS.md) | Comprehensive documentation for lesson schema, curriculum extension, and contributors. |
| 0c. | Testing and Testing Guide | [Testing Section](#testing-guide) | Lesson validation, code compilation testing, and progression tracking. |
| 0d. | Docker | [Dockerfile](https://github.com/forever8896/inkverse/blob/main/code-validation-server/Dockerfile) | Production multi-stage Dockerfile deployed on Railway. |
| 1. | JSON Lesson Schema | [lesson-editor-validation.ts](https://github.com/forever8896/inkverse/blob/main/src/lib/lesson-editor-validation.ts), [lesson-types.ts](https://github.com/forever8896/inkverse/blob/main/src/lib/lesson-types.ts) | Zod-validated schema with evolution metadata (`triggersGeneration`, `generationStage`, `displayStage`). |
| 2. | Browser-based IDE | [MonacoCodeEditor.tsx](https://github.com/forever8896/inkverse/blob/main/src/components/MonacoCodeEditor.tsx), [Lesson Page](https://github.com/forever8896/inkverse/tree/main/src/app/lesson) | Monaco Editor with Rust/ink! syntax highlighting and real-time error markers. |
| 3. | Code Validation | [code-validation-server/](https://github.com/forever8896/inkverse/tree/main/code-validation-server) | Dockerized ink! compilation with `cargo-contract` v6, BullMQ, Redis, and 23+ educational error explanations. |
| 4. | Lesson Content Integration | [Lesson Editor](https://github.com/forever8896/inkverse/blob/main/src/components/LessonEditorTutorial.tsx), [Lesson Editor Page](https://github.com/forever8896/inkverse/blob/main/src/app/lesson-editor/page.tsx), [Lesson 1 JSON](https://github.com/forever8896/inkverse/blob/main/src/content/lessons/1.json) | Graphical lesson editor with live preview, JSON import/export, and validation. Lesson 1 complete with 5 chapters. |
| 5. | User Progression System | [NFTs Pallet Service](https://github.com/forever8896/inkverse/blob/main/src/services/nfts-pallet-service.ts), [Vercel Workflows](https://github.com/forever8896/inkverse/tree/main/src/workflows), [Progress API](https://github.com/forever8896/inkverse/tree/main/src/app/api/progress) | Monster evolution → AssetHub NFT minting via durable workflows. Full progression tracking. |

---

## Testing Guide

**1. Unit Tests**

```bash
cd inkverse
npm test
```

Tests cover:
- **Generation Job State Machine** ([generation-job.state-machine.test.ts](https://github.com/forever8896/inkverse/blob/main/src/lib/__tests__/generation-job.state-machine.test.ts)): ERROR_HANDLERS configuration, retry logic (`canRetry()`, `getSecondsUntilRetry()`), status transitions, and retry limit enforcement for 15+ error types
- **AI Pipeline Services** ([fal-service.test.ts](https://github.com/forever8896/inkverse/blob/main/src/services/ai-pipeline/fal-service.test.ts)): 3D conversion, error handling, usage statistics tracking, cost calculation
- **Lesson Validation**: Zod schema validation for lessons, chapters, steps, and evolution metadata

**2. Code Compilation Server**

```bash
# Health check
curl https://monsters-code-validation-server-production.up.railway.app/health
```

The server compiles ink! contracts with `cargo-contract` v6 and returns educational error feedback.

**3. Progression Tracking**

1. Visit https://monsters-prod.vercel.app/lab
2. Log in via GitHub OAuth
3. Start Lesson 1 and complete steps
4. Progress persists across sessions

**4. NFT Minting**

NFT minting uses AssetHub (Paseo testnet). The [M2 Report](https://github.com/forever8896/inkverse/blob/main/docs/M2_REPORT.md) documents the full workflow with IPFS checkpointing and on-chain verification.

---

## Technical Architecture

| Component | Technology | Deployment |
| :--- | :--- | :--- |
| Code Validation Server | Express, BullMQ, Redis, cargo-contract v6 | Railway (Docker) |
| Monster Generation | Vercel Workflows, OpenAI, fal.ai | Vercel |
| NFT Minting | @polkadot/api, NFTs pallet | AssetHub (Paseo) |
| IPFS Storage | Pinata SDK | Pinata Cloud |
| Frontend | Next.js 15, Monaco Editor, Motion | Vercel |

See [M2 Report](https://github.com/forever8896/inkverse/blob/main/docs/M2_REPORT.md) for complete technical details.

---

## Additional Deliverables (Exceeding Scope)

- **Vercel Workflows:** Durable execution engine with idempotency, IPFS checkpointing, and crash recovery
- **Squink:** Animated feedback character ([ErrorSquink.tsx](https://github.com/forever8896/inkverse/blob/main/src/components/lesson/ErrorSquink.tsx))
- **Sound System:** Audio feedback for validation and progression ([sound-manager.ts](https://github.com/forever8896/inkverse/blob/main/src/lib/sound-manager.ts))
- **Lab Page:** NFT display and progress visualization ([LabClient.tsx](https://github.com/forever8896/inkverse/blob/main/src/components/LabClient.tsx))

---

**Repository:** https://github.com/forever8896/inkverse
**Live Platform:** https://monsters-prod.vercel.app/
**Code Validation Server:** https://monsters-code-validation-server-production.up.railway.app/health
**Commit Hash:** a4ec761 (M2 Report Added)
