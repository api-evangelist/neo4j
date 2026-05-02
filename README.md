# Neo4j (neo4j)
Neo4j is the leading graph database platform, enabling developers to build applications powered by connected data. Their developer platform provides HTTP, Query, and Aura cloud APIs alongside official drivers for Python, Java, and JavaScript, as well as a GraphQL library for rapid API development backed by the Neo4j graph database.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/neo4j/refs/heads/main/apis.yml)

## Scope

- **Type:** Contract
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags:

 - Graph Database, Cypher, Cloud, GraphQL, Drivers, APIs

## Timestamps

- **Created:** 2025-03-05
- **Modified:** 2026-04-28

## APIs

### Neo4j HTTP API
The Neo4j HTTP API allows developers to execute Cypher queries against a Neo4j database through HTTP requests. It supports both implicit transactions, where the API handles transaction management automatically, and explicit transactions, where developers control the full transaction lifecycle including open, commit, and rollback operations. By default the API uses port 7474 for HTTP and port 7473 for HTTPS on self-managed instances.

**Human URL:** [https://neo4j.com/docs/http-api/current/](https://neo4j.com/docs/http-api/current/)


#### Tags:

 - Graph Database, Cypher, HTTP, Transactions, Database

#### Properties

- [Documentation](https://neo4j.com/docs/http-api/current/)
- [OpenAPI](openapi/neo4j-http-api-openapi.yml)

### Neo4j Query API
The Neo4j Query API enables the execution of Cypher statements against a Neo4j server through HTTP requests. It provides a streamlined interface for running graph database queries, supporting both self-managed and cloud-hosted Neo4j instances. The Query API is designed for applications that need to interact with Neo4j programmatically and is particularly useful for languages where a dedicated Neo4j driver is not available.

**Human URL:** [https://neo4j.com/docs/query-api/current/](https://neo4j.com/docs/query-api/current/)


#### Tags:

 - Graph Database, Cypher, Query, HTTP, Database

#### Properties

- [Documentation](https://neo4j.com/docs/query-api/current/)
- [OpenAPI](openapi/neo4j-query-api-openapi.yml)

### Neo4j Aura API
The Neo4j Aura API provides programmatic access to manage Neo4j AuraDB cloud database instances. It supports operations across three primary resources: instances, tenants, and snapshots. Developers authenticate using OAuth2 bearer tokens obtained through client credentials, and can automate the provisioning, configuration, and management of their cloud-hosted Neo4j graph databases. The API is accessible through the console.neo4j.io platform.

**Human URL:** [https://neo4j.com/docs/aura/platform/api/specification/](https://neo4j.com/docs/aura/platform/api/specification/)


#### Tags:

 - Cloud, Graph Database, Database Management, Instances, Snapshots

#### Properties

- [Documentation](https://neo4j.com/docs/aura/platform/api/specification/)
- [OpenAPI](openapi/neo4j-aura-api-openapi.yml)

### Neo4j GraphQL Library
The Neo4j GraphQL Library is an open source JavaScript library that enables rapid development of GraphQL APIs backed by a Neo4j graph database. It automatically generates a single optimized Cypher query for each GraphQL query or mutation, eliminating the N+1 problem common in GraphQL implementations. The library supports schema-first development and integrates with Neo4j AuraDB for cloud-hosted deployments, making it suitable for cross-platform and mobile applications.

**Human URL:** [https://neo4j.com/docs/graphql/current/](https://neo4j.com/docs/graphql/current/)


#### Tags:

 - GraphQL, Graph Database, JavaScript, Low-Code, API Development

#### Properties

- [Documentation](https://neo4j.com/docs/graphql/current/)

### Neo4j Bolt Protocol
The Neo4j Bolt Protocol is a binary application protocol designed for efficient execution of database queries using the Cypher query language. It operates over TCP or WebSocket connections on the default port 7687 and serves as the foundation for all official Neo4j drivers including Java, Python, JavaScript, .NET, and Go. The protocol supports both direct connections via the bolt:// scheme and routing connections via bolt+routing:// for clustered deployments.

**Human URL:** [https://neo4j.com/docs/bolt/current/bolt/](https://neo4j.com/docs/bolt/current/bolt/)


#### Tags:

 - Binary Protocol, Graph Database, Drivers, Connectivity, Networking

#### Properties

- [Documentation](https://neo4j.com/docs/bolt/current/bolt/)

### Neo4j Python Driver
The Neo4j Python Driver is the official library for interacting with Neo4j graph databases from Python applications. It communicates using the Bolt protocol and supports both single instance and clustered database deployments. The driver is available on PyPI as the neo4j package and provides a comprehensive API for session management, transaction handling, and result processing.

**Human URL:** [https://neo4j.com/docs/python-manual/current/](https://neo4j.com/docs/python-manual/current/)


#### Tags:

 - Python, SDK, Driver, Graph Database, Bolt

#### Properties

- [Documentation](https://neo4j.com/docs/python-manual/current/)
- [Documentation](https://neo4j.com/docs/api/python-driver/current/)

### Neo4j Java Driver
The Neo4j Java Driver is the official library for connecting Java applications to Neo4j graph databases. Distributed via Maven, it uses the Bolt protocol for network communication and supports both single instance and clustered database configurations. The driver provides a full API for managing connections, sessions, transactions, and query results within Java applications.

**Human URL:** [https://neo4j.com/docs/java-manual/current/](https://neo4j.com/docs/java-manual/current/)


#### Tags:

 - Java, SDK, Driver, Graph Database, Bolt

#### Properties

- [Documentation](https://neo4j.com/docs/java-manual/current/)
- [Documentation](https://neo4j.com/docs/api/java-driver/current/)

### Neo4j JavaScript Driver
The Neo4j JavaScript Driver is the official library for interacting with Neo4j graph databases from JavaScript and Node.js applications. It uses the Bolt protocol for efficient communication and can be installed via npm. The driver supports both browser and server-side environments and provides APIs for session management, transaction control, and processing of query results from Neo4j databases.

**Human URL:** [https://neo4j.com/docs/javascript-manual/current/](https://neo4j.com/docs/javascript-manual/current/)


#### Tags:

 - JavaScript, SDK, Driver, Graph Database, Bolt, Node.js

#### Properties

- [Documentation](https://neo4j.com/docs/javascript-manual/current/)
- [Documentation](https://neo4j.com/docs/api/javascript-driver/current/)

## Common Properties

- [Portal](https://neo4j.com/developer/)
- [Documentation](https://neo4j.com/docs/)
- [Website](https://neo4j.com)
- [PrivacyPolicy](https://neo4j.com/privacy-policy/)
- [TermsOfService](https://neo4j.com/terms/)
- [Support](https://support.neo4j.com/)
- [Blog](https://neo4j.com/blog/)
- [Login](https://console.neo4j.io/)

## Maintainers

**FN:** API Evangelist

**Email:** info@apievangelist.com
