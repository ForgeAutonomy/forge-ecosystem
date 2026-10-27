# Forge Architecture

## Repository boundaries

### forge-runtime

Owns the backend control plane:

- runtime API and WebSocket events
- Temporal workflows and workers
- PostgreSQL schemas and migrations
- policy evaluation
- approvals
- receipts and artifacts
- worktree and sandbox lifecycle
- agent adapters
- verification and sequential integration
- evaluation suites

The runtime worker remains in this repository because it shares the database schema, contracts, release cadence, and recovery protocol with the runtime.

### forge-ide

**Dropped by the owner, 2026-10-27.** This plan is not pursued. The text below is kept as the record.

Owns user-facing development clients:

- VS Code extension
- Mission Control
- objective intake
- agent status
- logs, receipts, tests, and diffs
- approval interfaces
- later Code-OSS packaging

The IDE communicates with Forge Runtime through versioned HTTP, WebSocket, and generated client contracts.

### forge-ecosystem

Owns public-facing material:

- system overview
- roadmap
- architecture diagrams
- release matrix
- demonstrations
- screenshots and videos
- links to public components

## Future repository rule

A new repository is created only when a component has an independent release cadence, deployment boundary, security boundary, or consumer base. Internal packages are not split merely because they are separate folders.
