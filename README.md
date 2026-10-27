# Forge Ecosystem

Forge is a local-first, agent-native software-development operating system.

It converts a plain-English objective into controlled, recoverable, and verifiable engineering work:

```text
Forge IDE / CLI / Hermes (IDE dropped by the owner, 2026-10-27)
          |
          v
     Forge Runtime
          |
          v
Objective -> Plan -> Isolated Agents -> Verification -> Integration
```

## Repositories

| Repository | Purpose | Status |
|---|---|---|
| `forge-runtime` | Durable mission state, Temporal workflows, policy enforcement, workers, receipts, recovery, and integration | v0.1.0 complete; source private during hardening |
| `forge-ide` | VS Code Mission Control client and later Forge-branded Code-OSS distribution | Planned (dropped by the owner, 2026-10-27) |
| `forge-ecosystem` | Public architecture, roadmap, demonstrations, and release index | Active |

## Forge Runtime v0.1.0

The first release proves:

- durable mission state
- Temporal interruption recovery
- pause, resume, and cancellation
- worker heartbeats and lease reclamation
- idempotent mission creation
- WebSocket event streaming
- Open Policy Agent enforcement
- structured evidence receipts
- false-receipt rejection
- secret redaction
- frozen regression baseline
- 146 offline tests and 11 live acceptance tests

The v0.1.0 adapter is intentionally a mock adapter. Real Claude and Codex orchestration begins in v0.2.

## Roadmap

- **v0.2:** real Claude/Codex adapters, task graphs, multiple worktrees, verification, integration, and recovery
- **v0.3:** VS Code Mission Control (dropped by the owner, 2026-10-27)
- **v0.4:** repository indexing, memory, RAG, decisions, and provenance
- **v0.5:** taste profiles and governed skills
- **v0.6:** MCP broker, credentials, n8n, and capability-based tools
- **v0.7:** controlled improvement with benchmarks and rollback
- **v1.0:** independent Forge IDE distribution (dropped by the owner, 2026-10-27)

## Safety model

Forge treats prompts as instructions, not enforcement. Deterministic policy, isolated worktrees, durable audit records, evidence-backed receipts, independent verification, and explicit production approval gates define the operating boundary.

## Portfolio status

This public repository documents the architecture and verified results. Runtime source remains private until a dedicated public-release audit removes internal traces, confirms licensing, and validates the security boundary.
