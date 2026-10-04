---
name: neo4j-transaction-execute-commit
description: Open a transaction, execute statements, and commit the transaction.
api: openapi/neo4j-transactions-api-openapi.yml
operations:
- openTransaction
- executeInTransaction
- commitTransaction
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/neo4j-transactions-api-openapi.yml ; every operationId checked against the contract
---

# neo4j-transaction-execute-commit

Open a transaction, execute statements, and commit the transaction.

## Steps

1. 1. `openTransaction` – provide `databaseName` path parameter and request body with transaction metadata if any.
2. 2. `executeInTransaction` – provide `databaseName` and `transactionId` path parameters and request body containing the Cypher statements to run.
3. 3. `commitTransaction` – provide `databaseName` and `transactionId` path parameters; optional request body may contain final statements.

## Rules

- Authentication: include either a `Authorization: Basic <credentials>` header (basicAuth) or a `Authorization: Bearer <token>` header (bearerAuth).
- Idempotency: `openTransaction` and `executeInTransaction` are not idempotent; `commitTransaction` and `rollbackTransaction` should be called only once per transaction ID.
- Errors: the API returns standard HTTP error codes; on authentication failure 401, on missing transaction 404, and on server errors 5xx.
