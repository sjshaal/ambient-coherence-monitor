# RuVector — Brainstorming Reference

**Source directory:** `/Users/jennifershaal/code/ruvector`

RuVector is a self-learning, self-optimizing vector database and agentic operating system — CES 2026 Innovation Award honoree. It is not just a database; it is a cognitive substrate for always-on AI agents with hardware isolation, cryptographic proofs, quantum-ready security, and a built-in learning loop.

---

## What Lives There

### Scale
- **111 Rust crates** (core engine, distributed systems, ML, quantum, hardware)
- **58+ NPM packages** (Node.js bindings, SvelteKit UI, cloud tools)
- **47+ example apps**, **460+ docs**, **138 Architecture Decision Records**

### Primary Languages
- Rust (~80%) — MSRV 1.77, Edition 2021
- TypeScript/JavaScript (~15%) — SvelteKit frontend, NAPI bindings
- WebAssembly (~5%) — 5.5 KB browser runtime

---

## Exotic Corners Worth Exploring

### RVF — RuVector Format (`/crates/rvf/`, 22 subcrates)
The crown jewel. A single `.rvf` binary file that contains: vectors, ML models, a graph, a WASM runtime, eBPF programs, and a cryptographic witness chain. It self-boots as a Linux microservice in 125ms. Features:
- Git-style copy-on-write branching (1M vectors ≈ 2.5 MB branch)
- Post-quantum crypto: ML-DSA-65 + SLH-DSA-128s
- TEE attestation support
- 24 segment types
- Tamper-evident audit trails via SHAKE-256 hash chains

### SONA — Self-Optimizing Neural Architecture (`/crates/sona/`)
Runtime-adaptive learning built into the database itself. Every query feeds back into the model. Uses:
- Two-tier LoRA (Low-Rank Adaptation)
- EWC++ (Elastic Weight Consolidation++)
- ReasoningBank for persistent knowledge
- GraphMAE (Graph Masked Autoencoder) layers

### 50+ Attention Mechanisms (`/crates/ruvector-attention/`)
Implements cutting-edge ML research in one place:
- FlashAttention-3, MLA, Mamba SSM
- Hyperbolic HNSW, Sheaf attention (coherence-gated)
- Mixed-curvature topology-aware attention
- Optimal Transport attention
- ColBERT per-token late-interaction

### Quantum Computing (`/crates/ruqu-core/`, `ruqu-algorithms/`, `ruqu-exotic/`)
Full quantum circuit simulator integrated with the vector space:
- State-vector simulation with SIMD
- Noise models
- Dynamic min-cut error correction

### RuVix Cognition Kernel (`/crates/ruvix/`, 14 subcrates)
A bare-metal AArch64 cognition kernel — think OS kernel but purpose-built for AI agents:
- Capability-based security model
- Deterministic replay (syscall dispatch)
- Proof system integration
- Custom scheduler
- Hardware abstraction layer (`ruvix-hal`, `ruvix-aarch64`)

### rvAgent Framework (`/crates/rvAgent/`, 8 subcrates)
A complete AI agent framework (DeepAgents converted to Rust):
- Model Context Protocol (MCP) support
- Sub-agent spawning
- Tool registry + middleware chain
- WASM agent runtime

### Graph Engine (`/crates/ruvector-graph/`)
Neo4j-compatible Cypher engine on top of HNSW:
- Hypergraph support
- 8 graph transformer domains (Physics, Biology, Manifold, Temporal, Economic...)
- Community detection for Graph RAG (30–60% retrieval improvement)
- Real-time sparsification via shadow graphs
- Sublinear PageRank: O(log n)

### Cognitum Hardware Kernel (`/crates/cognitum-gate-kernel/`)
The kernel for the Cognitum chip — an "agentic chip" for always-on AI agents. Also includes tile-zero optimizations.

### Specialized Domain Crates
| Crate | Domain |
|-------|--------|
| `agentic-robotics-*` (7 crates) | Real-time robotics control |
| `neural-trader-core` + `neural-trader-replay` | AI-driven financial trading |
| `ruvector-temporal-tensor` | 2–32x memory compression via adaptive tiering |
| `ruvector-fpga-transformer` | FPGA-accelerated transformer inference |
| `thermorust` | Unknown — worth exploring |
| `prime-radiant` | Unknown — worth exploring |
| `ruvector-nervou-system` | Self-adaptive "nervous system" architecture |

---

## Hardware Targets

| Platform | Notes |
|----------|-------|
| Apple Silicon (M1–M4) | Metal + CoreML + Apple Neural Engine |
| NVIDIA | CUDA acceleration |
| FPGA | Transformer acceleration |
| Browsers | 5.5 KB WASM |
| PostgreSQL | 230+ SQL functions via extension |
| Bare metal | Single .rvf file, boots as microservice |
| IoT / Embedded | Lightweight runtime |
| Cognitum chip | Custom agentic hardware |

---

## Quick Navigation

```
/Users/jennifershaal/code/ruvector/
├── crates/          # All 111 Rust crates
│   ├── rvf/         # RuVector Format (22 subcrates) — start here
│   ├── sona/        # Self-optimizing neural architecture
│   ├── ruvix/       # Cognition kernel (14 subcrates)
│   ├── rvAgent/     # Agent framework (8 subcrates)
│   ├── ruqu-*/      # Quantum computing
│   └── ruvector-attention/  # 50+ attention mechanisms
├── npm/packages/    # 58+ TypeScript packages
├── examples/        # 47+ example apps
├── docs/            # 460+ docs, 138 ADRs
├── ui/ruvocal/      # SvelteKit chat UI
└── benchmarks/      # Performance suite
```

---

## Brainstorm Prompts

- What would it look like to run a RVF container as a browser extension with an embedded LLM?
- How could the quantum simulator (`ruqu-exotic`) intersect with the GNN learning loop?
- `prime-radiant` and `thermorust` are undocumented — what are they actually doing?
- The Cognitum chip + RuVix kernel: what does "always-on AI agent" mean at the hardware level?
- Could the temporal-tensor compression scheme apply to non-vector data (audio, genomics)?
- The neural trader uses "coherence scoring" — how does coherence transfer to other domains?
- RVF self-boots in 125ms — what is the minimum viable cognitive unit that could run on IoT?
