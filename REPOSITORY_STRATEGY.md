# Forge GitHub and Repository Strategy

## Decision

Use a **hybrid multi-repository architecture**.

A component gets its own repository when it has an independent release cadence, deployment boundary, security boundary, or product identity. A folder does not get its own repository merely because it is technically separate.

## Organization

Create a dedicated GitHub organization owned by your personal GitHub account:

- Preferred organization slug: `ForgeAutonomy`
- Keep Forge separate from the KaBo company organization
- Make your personal account an organization owner
- Use the organization as the branded home for the ecosystem

## Repositories to create now

| Repository | Visibility now | Purpose |
|---|---|---|
| `forge-runtime` | Private | Current `~/Developer/forge` code, v0.1.0 source of truth, remote backup |
| `forge-ecosystem` | Public | Portfolio overview, architecture, roadmap, release matrix, demos |
| `forge-ide` | Private | Independent VS Code/Code-OSS client; actual development begins after v0.2 (dropped by the owner, 2026-10-27) |

## Keep together inside forge-runtime

Do not split these into separate repositories yet:

- runtime API
- Temporal worker
- contracts
- mission state machine
- policy client
- receipts and artifacts
- database and migrations
- infrastructure
- integration tests
- evaluation fixtures

They share contracts, storage, recovery behavior, and release cadence. Splitting them now would create unnecessary cross-repository versioning and integration overhead.

## Repositories to defer

Create these only after they become independently useful:

- `forge-protocol`
- `forge-hermes-adapter`
- `forge-actions`
- `forge-docs`

## Portfolio approach

The public `forge-ecosystem` repository should be the first pinned portfolio item. It can show architecture, verified test results, screenshots, release notes, and videos without exposing internal logs or private operational traces.

Keep `forge-runtime` private until a public-release audit confirms:

- no secrets or credentials
- no private KaBo material
- no raw internal prompts or sensitive logs
- no personal paths/emails that should be hidden
- license compatibility
- a chosen repository license
- security and contribution policies
- complete regression results

After that audit, either make `forge-runtime` public or publish a sanitized public mirror.

## Backup model

GitHub is the remote source backup for Git-tracked code, commits, branches, and tags.

It does not back up:

- `.forge-data`
- ignored artifacts
- Docker volumes
- PostgreSQL/Temporal runtime state
- credentials
- local-only logs
- untracked files

Keep the verified Git bundle and later add a separate encrypted backup for runtime state.
