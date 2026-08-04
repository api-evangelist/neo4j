# Neo4j (neo4j)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Neo4j is the leading graph database platform, enabling developers to build applications powered by connected data. Their developer platform provides HTTP, Query, and Aura cloud APIs alongside official drivers for Python, Java, and JavaScript, as well as a GraphQL library for rapid API development backed by the Neo4j graph database.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/neo4j/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/neo4j/refs/heads/main/apis.yml)

## Tags

- Graph Database
- Cypher
- Cloud
- GraphQL
- Drivers
- APIs

## Timestamps

- **Created:** 2025-03-05
- **Modified:** 2026-05-19

## APIs

### Neo4j HTTP API

The Neo4j HTTP API allows developers to execute Cypher queries against a Neo4j database through HTTP requests. It supports both implicit transactions, where the API handles transaction management automatically, and explicit transactions, where developers control the full transaction lifecycle including open, commit, and rollback operations. By default the API uses port 7474 for HTTP and port 7473 for HTTPS on self-managed instances.

- **Human URL:** [https://neo4j.com/docs/http-api/current/](https://neo4j.com/docs/http-api/current/)

#### Tags

- Graph Database
- Cypher
- HTTP
- Transactions
- Database

#### Properties

- [Documentation](https://neo4j.com/docs/http-api/current/)
- [OpenAPI](openapi/neo4j-http-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/neo4j-http-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-http-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Neo4j Query API

The Neo4j Query API enables the execution of Cypher statements against a Neo4j server through HTTP requests. It provides a streamlined interface for running graph database queries, supporting both self-managed and cloud-hosted Neo4j instances. The Query API is designed for applications that need to interact with Neo4j programmatically and is particularly useful for languages where a dedicated Neo4j driver is not available.

- **Human URL:** [https://neo4j.com/docs/query-api/current/](https://neo4j.com/docs/query-api/current/)

#### Tags

- Graph Database
- Cypher
- Query
- HTTP
- Database

#### Properties

- [Documentation](https://neo4j.com/docs/query-api/current/)
- [OpenAPI](openapi/neo4j-query-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Neo4j Aura API

The Neo4j Aura API provides programmatic access to manage Neo4j AuraDB cloud database instances. It supports operations across three primary resources: instances, tenants, and snapshots. Developers authenticate using OAuth2 bearer tokens obtained through client credentials, and can automate the provisioning, configuration, and management of their cloud-hosted Neo4j graph databases. The API is accessible through the console.neo4j.io platform.

- **Human URL:** [https://neo4j.com/docs/aura/platform/api/specification/](https://neo4j.com/docs/aura/platform/api/specification/)

#### Tags

- Cloud
- Graph Database
- Database Management
- Instances
- Snapshots

#### Properties

- [Documentation](https://neo4j.com/docs/aura/platform/api/specification/)
- [OpenAPI](openapi/neo4j-aura-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/neo4j-aura-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-aura-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Neo4j GraphQL Library

The Neo4j GraphQL Library is an open source JavaScript library that enables rapid development of GraphQL APIs backed by a Neo4j graph database. It automatically generates a single optimized Cypher query for each GraphQL query or mutation, eliminating the N+1 problem common in GraphQL implementations. The library supports schema-first development and integrates with Neo4j AuraDB for cloud-hosted deployments, making it suitable for cross-platform and mobile applications.

- **Human URL:** [https://neo4j.com/docs/graphql/current/](https://neo4j.com/docs/graphql/current/)

#### Tags

- GraphQL
- Graph Database
- JavaScript
- Low-Code
- API Development

#### Properties

- [Documentation](https://neo4j.com/docs/graphql/current/)
- [Postman Collection](collections/neo4j-aura-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-aura-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/neo4j-http-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-http-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Neo4j Bolt Protocol

The Neo4j Bolt Protocol is a binary application protocol designed for efficient execution of database queries using the Cypher query language. It operates over TCP or WebSocket connections on the default port 7687 and serves as the foundation for all official Neo4j drivers including Java, Python, JavaScript, .NET, and Go. The protocol supports both direct connections via the bolt:// scheme and routing connections via bolt+routing:// for clustered deployments.

- **Human URL:** [https://neo4j.com/docs/bolt/current/bolt/](https://neo4j.com/docs/bolt/current/bolt/)

#### Tags

- Binary Protocol
- Graph Database
- Drivers
- Connectivity
- Networking

#### Properties

- [Documentation](https://neo4j.com/docs/bolt/current/bolt/)
- [Postman Collection](collections/neo4j-aura-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-aura-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/neo4j-http-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-http-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Neo4j Python Driver

The Neo4j Python Driver is the official library for interacting with Neo4j graph databases from Python applications. It communicates using the Bolt protocol and supports both single instance and clustered database deployments. The driver is available on PyPI as the neo4j package and provides a comprehensive API for session management, transaction handling, and result processing.

- **Human URL:** [https://neo4j.com/docs/python-manual/current/](https://neo4j.com/docs/python-manual/current/)

#### Tags

- Python
- SDK
- Driver
- Graph Database
- Bolt

#### Properties

- [Documentation](https://neo4j.com/docs/python-manual/current/)
- [Documentation](https://neo4j.com/docs/api/python-driver/current/)
- [Postman Collection](collections/neo4j-aura-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-aura-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/neo4j-http-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-http-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Neo4j Java Driver

The Neo4j Java Driver is the official library for connecting Java applications to Neo4j graph databases. Distributed via Maven, it uses the Bolt protocol for network communication and supports both single instance and clustered database configurations. The driver provides a full API for managing connections, sessions, transactions, and query results within Java applications.

- **Human URL:** [https://neo4j.com/docs/java-manual/current/](https://neo4j.com/docs/java-manual/current/)

#### Tags

- Java
- SDK
- Driver
- Graph Database
- Bolt

#### Properties

- [Documentation](https://neo4j.com/docs/java-manual/current/)
- [Documentation](https://neo4j.com/docs/api/java-driver/current/)
- [Postman Collection](collections/neo4j-aura-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-aura-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/neo4j-http-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-http-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Neo4j JavaScript Driver

The Neo4j JavaScript Driver is the official library for interacting with Neo4j graph databases from JavaScript and Node.js applications. It uses the Bolt protocol for efficient communication and can be installed via npm. The driver supports both browser and server-side environments and provides APIs for session management, transaction control, and processing of query results from Neo4j databases.

- **Human URL:** [https://neo4j.com/docs/javascript-manual/current/](https://neo4j.com/docs/javascript-manual/current/)

#### Tags

- JavaScript
- SDK
- Driver
- Graph Database
- Bolt
- Node.js

#### Properties

- [Documentation](https://neo4j.com/docs/javascript-manual/current/)
- [Documentation](https://neo4j.com/docs/api/javascript-driver/current/)
- [Postman Collection](collections/neo4j-aura-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-aura-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/neo4j-http-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neo4j-http-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/neo4j)
- [LinkedIn](https://www.linkedin.com/company/neo4j)
- [Portal](https://neo4j.com/developer/)
- [Documentation](https://neo4j.com/docs/)
- [Website](https://neo4j.com)
- [Privacy Policy](https://neo4j.com/privacy-policy/)
- [Terms of Service](https://neo4j.com/terms/)
- [Support](https://support.neo4j.com/)
- [Blog](https://neo4j.com/blog/)
- [Login](https://console.neo4j.io/)
- [Integrations](https://neo4j.com/partners/)
- [Agent Skill](https://neo4j.com/blog/developer/introducing-neo4j-agent-skills/)
- [L L Ms Txt](https://neo4j.com/llms.txt)

## Maintainers

**FN:** API Evangelist
**Email:** info@apievangelist.com
