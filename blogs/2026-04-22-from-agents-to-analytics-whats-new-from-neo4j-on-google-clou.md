---
title: "From Agents to Analytics: What’s New from Neo4j on Google Cloud"
url: "https://neo4j.com/blog/graph-database/from-agents-to-analytics-whats-new-from-neo4j-on-google-cloud/"
date: "Wed, 22 Apr 2026 12:33:00 +0000"
author: "Nathan Barney"
feed_url: "https://neo4j.com/blog/feed/"
---
<div><img alt="" class="attachment-large size-large wp-post-image" height="427" src="https://dist.neo4j.com/wp-content/uploads/20260417142726/Next-Blog-Header-1024x683.png" style="margin-bottom: 15px;" width="640" /></div>
<p>As enterprises move from AI experimentation to production, connected data has become essential for building more accurate, context-aware applications. Over the past year, <a href="https://neo4j.com/partners/google/">Neo4j and Google Cloud</a> have expanded the ways customers can build graph-powered agents, streamline developer workflows, simplify deployment, and unlock new insights from connected data.</p>



<p>As we head into Google Cloud Next ’26, we’re excited to share some of the latest innovations across agentic AI, developer tooling, analytics, and enterprise readiness.</p>



<p>These updates reflect a broader focus: helping customers adopt graph technology more easily on Google Cloud, whether they’re building AI agents, deploying databases, analyzing connected data, or designing event-driven systems.</p>



<h3 class="wp-block-heading" id="h-building-graph-powered-ai-on-google-cloud">Building Graph-Powered AI on Google Cloud</h3>



<h4 class="wp-block-heading" id="h-neo4j-agent-integrations-with-the-google-cloud-ecosystem">Neo4j Agent integrations with the Google Cloud ecosystem</h4>



<h5 class="wp-block-heading" id="h-neo4j-agent-available-in-gemini-enterprise-console">Neo4j Agent Available in Gemini Enterprise Console</h5>



<p>Google Cloud Marketplace includes <a href="https://cloud.google.com/blog/products/ai-machine-learning/partner-built-agents-available-in-gemini-enterprise">partner-developed AI agents</a>, simplifying the discovery and deployment of validated agents integrated with Google Cloud for both Agent-to-Agent (A2A) and Gemini Enterprise integration. <sup class="fn"><a href="#d0addb56-9633-493d-ab5c-bd91da51fcf8" id="d0addb56-9633-493d-ab5c-bd91da51fcf8-link">1</a></sup></p>



<p>The Neo4j AI Agent is now available within the Gemini Enterprise console, meaning any user can potentially access it directly without seeking it out through a standalone agent marketplace. This offering provides users with a graph-native agent capable of translating natural language into Cypher and incorporating GraphRAG (Retrieval-Augmented Generation) into broader agentic workflows.</p>



<p>Neo4j Aura agents are built with Gemini 3 as the reasoning engine and can now be extended with graph-grounded retrieval through A2A, with no additional framework required. Neo4j also plugs directly into Gemini Enterprise workflows with reference architectures and guides purpose-built for Google Cloud. Whether teams are running agents on Vertex AI or building with the Agent Development Kit (ADK), Neo4j can appear as a native tool through the Model Context Protocol (MCP).</p>



<h5 class="wp-block-heading" id="h-gemini-cli-extension">Gemini CLI Extension</h5>



<p>The Neo4j Gemini CLI extension brings that same MCP-based integration into the terminal, enabling developers to deploy cloud infrastructure, generate Cypher queries from natural language, and build GraphRAG applications directly from the command line. Check out the developer blog <a href="https://cloud.google.com/blog/topics/developers-practitioners/using-the-neo4j-extension-in-gemini-cli">here</a> for more detail.</p>



<h5 class="wp-block-heading" id="h-a-complete-agent-memory-api">A complete agent memory API</h5>



<p>Neo4j is also expanding how agents persist and reuse context. The neo4j-agent-memory package gives agents short-term, long-term, and reasoning memory, including decision traces and context graphs. This allows agents to store what they’ve done, learn from prior interactions, and retrieve relevant context when it matters.</p>



<h3 class="wp-block-heading" id="h-designing-connected-real-time-workflows">Designing Connected, Real-Time Workflows</h3>



<h4 class="wp-block-heading" id="h-pub-sub-integration">Pub/Sub Integration</h4>



<p>Building on our success in building streaming graph data pipelines on Google Cloud with Apache Kafka,<sup class="fn"><a href="#df688b61-bd4a-4858-ac6d-a54780211e49" id="df688b61-bd4a-4858-ac6d-a54780211e49-link">2</a></sup> Neo4j is now available as a <a href="https://cloud.google.com/pubsub/integrations">Pub/Sub integration</a> inside the Google Cloud console. This makes it easier for users to discover and implement real-time data flows between Neo4j and Pub/Sub. Read the blog <a href="https://neo4j.com/blog/graph-database/seamless-data-pipeline-neo4j-and-google-cloud-pub-sub/">here</a>.</p>



<h4 class="wp-block-heading" id="h-application-design-center-integration">Application Design Center Integration</h4>



<p><a href="https://docs.cloud.google.com/application-design-center/docs">Google Cloud Application Design Center (ADC)</a> brings together visualization, writing Infrastructure-as-Code (IaaC), and governance to simplify management of the cloud-native application lifecycle. Neo4j is now available inside ADC. Using the Neo4j Terraform Provider for the Aura Admin API, this integration helps simplify the design of data flows connecting Neo4j with other Google services.</p>



<p>Visit us at our Google Cloud Next ’26 Expo Booth #2717 for a demonstration!</p>



<h4 class="wp-block-heading" id="h-bigquery-notebooks">BigQuery Notebooks</h4>



<p>Analyzing and understanding connections and patterns in a dataset can derive new value for businesses. Neo4j Aura Graph Analytics enables graph modeling on your data in place &#8211; no ETL required. Take a look at our <a href="https://neo4j.com/blog/aura-graph-analytics/discover-rich-graph-powered-insights-in-your-bigquery-data/">developer blog</a> for an example of how Aura Graph Analytics fits naturally into a BigQuery workflow, unlocking new insights from existing enterprise data.</p>



<h3 class="wp-block-heading" id="h-expanding-deployment-and-enterprise-readiness">Expanding Deployment and Enterprise Readiness</h3>



<h4 class="wp-block-heading" id="h-updated-neo4j-enterprise-edition-listing">Updated Neo4j Enterprise Edition listing</h4>



<p>While many users enjoy the ease of use of our fully-managed Aura database offering, others prefer tighter control over their database infrastructure. For teams that prefer self-managed infrastructure, the updated <a href="https://console.cloud.google.com/marketplace/product/neo4j-mp-public/neo4j-enterprise-edition">Neo4j Enterprise Edition</a> listing simplifies deployment on Google Cloud using infrastructure optimized for graph workloads. The new and improved offering helps users get up and running more quickly by automating the deployment of Google Cloud infrastructure optimized to run a graph database. We’ve also published the <a href="https://github.com/neo4j-partners/google-cloud-terraform-neo4j">underlying code</a>, allowing users to fork and customize the Terraform for their unique use cases.</p>



<h4 class="wp-block-heading" id="h-neo4j-community-edition-listing">Neo4j Community Edition listing</h4>



<p><a href="https://console.cloud.google.com/marketplace/product/neo4j-mp-public/neo4j-community-edition">Neo4j Community Edition</a> is now available on Google Cloud Marketplace, making it easier for developers to deploy and start building on Google Cloud. This offering automates the deployment of a Google Cloud virtual machine, enabling developers to focus on building applications rather than configuring infrastructure.</p>



<h4 class="wp-block-heading" id="h-neo4j-google-distributed-cloud-nbsp">Neo4j / Google Distributed Cloud&nbsp;</h4>



<p>Organizations that require air-gapped systems to maintain the highest level of network security can leverage the innovative features and operational benefits of Google Cloud with <a href="https://cloud.google.com/distributed-cloud">Google Distributed Cloud</a>. Google curates a <a href="https://docs.cloud.google.com/distributed-cloud/hosted/docs/latest/gdch/application/ao-user/marketplace-overview#available_software_packages">Marketplace</a> of software packages validated by Google Cloud and its relevant partners, which can be installed and managed even when disconnected from the Internet. <a href="https://docs.cloud.google.com/distributed-cloud/hosted/docs/latest/gdch/application/ao-user/marketplace-overview#available_software_packages">Neo4j is now validated for use with GDC</a>.</p>



<h4 class="wp-block-heading" id="h-our-commitment-to-hcls">Our Commitment to HCLS</h4>



<p>Neo4j’s graph database is well-suited to healthcare and payer use cases that depend on connected data, such as building a 360-degree patient view across clinical, operational, and device-generated data. To support these and other HCLS workloads, Neo4j and Google Cloud formalized a BAA aligned to HIPAA requirements.</p>



<p>Learn more about our <a href="https://neo4j.com/blog/graph-database/neo4j-google-cloud-marketplace-listings/">Google Cloud Marketplace listings</a> in this update.&nbsp;</p>



<h3 class="wp-block-heading" id="h-looking-ahead">Looking Ahead</h3>



<p>Together, these updates reflect how Neo4j and Google Cloud are making graph-powered AI more practical for the enterprise, from discoverable agents and MCP-based Gemini integration to persistent agent memory, simplified deployment, real-time data flows, and connected analytics.</p>



<p>With these advancements, Neo4j is making it easier for customers to build connected, intelligent applications on Google Cloud.</p>



<p>If you’ll be at Google Cloud Next ’26, visit us at <strong>Booth #2717</strong> to see these innovations in action and to talk with the team. You can also learn more about the <a href="https://neo4j.com/partners/google/">Neo4j + Google Cloud partnership</a> or reach us at <a href="mailto:ecosystem@neo4j.com">ecosystem@neo4j.com</a>.&nbsp;</p>


<ol class="wp-block-footnotes"><li id="d0addb56-9633-493d-ab5c-bd91da51fcf8"><a href="https://cloud.google.com/blog/topics/partners/google-cloud-ai-agent-marketplace">Scaling AI agents with Google Cloud Marketplace and Gemini Enterprise,</a> October 14, 2025 <a href="#d0addb56-9633-493d-ab5c-bd91da51fcf8-link"><img alt="↩" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/21a9.png" style="height: 1em;" />︎</a></li><li id="df688b61-bd4a-4858-ac6d-a54780211e49"><a href="https://cloud.google.com/blog/products/data-analytics/keep-graph-data-updated-on-google-cloud-using-confluent--neo4j">Streaming graph data with Confluent Cloud and Neo4j on Google Cloud</a>, May 25, 2023 <a href="#df688b61-bd4a-4858-ac6d-a54780211e49-link"><img alt="↩" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/21a9.png" style="height: 1em;" />︎</a></li></ol>


<p></p>
