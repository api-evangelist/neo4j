---
name: neo4j-create-and-restore-snapshot
description: Create a snapshot of an instance and restore it to a new instance.
api: openapi/neo4j-snapshots-api-openapi.yml
operations:
- createSnapshot
- restoreSnapshot
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/neo4j-snapshots-api-openapi.yml ; every operationId checked against the contract
---

# neo4j-create-and-restore-snapshot

Create a snapshot of an instance and restore it to a new instance.

## Steps

1. 1. Use `createSnapshot` with path parameter `instanceId` and request body describing the snapshot.
2. 2. Use `restoreSnapshot` with path parameters `instanceId` and `snapshotId` (from the response of `createSnapshot`).

## Rules

- Auth: Include either a `Authorization: Basic <credentials>` header for `basicAuth` or a `Authorization: Bearer <token>` header for `bearerAuth`.
- Idempotency: `createSnapshot` is not idempotent; avoid duplicate calls.
