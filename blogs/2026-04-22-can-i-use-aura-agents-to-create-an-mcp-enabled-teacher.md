---
title: "Can I use Aura Agents to create an MCP enabled Teacher?"
url: "https://neo4j.com/blog/agentic-ai/can-i-use-aura-agents-to-create-an-mcp-enabled-teacher-2/"
date: "Wed, 22 Apr 2026 15:59:16 +0000"
author: "Martin O'Hanlon"
feed_url: "https://neo4j.com/blog/feed/"
---
<div><img alt="GraphAcademy content is moved into Neo4j Aura, and an Aura Agent used to provide MCP server access to VS Code, Cursor, and Claude agents." class="attachment-large size-large wp-post-image" height="423" src="https://dist.neo4j.com/wp-content/uploads/20260423023749/architecture-1-1024x677.png" style="margin-bottom: 15px;" width="640" /></div>
<p>If you have used an agent to code you will know they are great at providing solutions to problems. Unfortunately they are not as good at teaching you to do it yourself.</p>



<p>Fine tuned to deliver solutions, they lack good context relating to how to teach complex subjects, often missing key points, providing inconsistent results, and don’t build confidence.</p>


<pre class="wp-block-code"><span><code class="hljs language-plaintext">&#91;Human]
Create a function which connects to my Neo4j databases and runs a 
Cypher statement.

&#91;AI] 
Sure, here is a new function, run_cypher(driver, datab ase, cypher).

&#91;Human]
How does this work?

&#91;AI]
It runs a cypher statement using the neo4j.GraphDatabase driver 
instance and database name and returns a list of Record objects.

&#91;Human]
But how does it actually work? What are the concepts I need to know? 
How do I do this myself?</code></span></pre>


<p>I wanted to change this and provide coding agents (VS Code, Cursor, etc) with access to Neo4j’s <a href="http://graphacademy.neo4j.com?ref=martin-aura-agents" rel="noreferrer noopener" target="_blank">GraphAcademy</a> content and teaching approaches.&nbsp;</p>



<p>GraphAcademy is Neo4j’s free online training platform and provides learners with knowledge and skills to use Neo4j to solve real world problems, including a new course on <a href="https://graphacademy.neo4j.com/courses/aura-agents/?ref=martin-aura-agents" rel="noreferrer noopener" target="_blank">Building Agents on Neo4j Aura</a>.</p>



<h2 class="wp-block-heading" id="h-the-plan">The plan</h2>



<ol class="wp-block-list">
<li>Create a <a href="https://neo4j.com/product/neo4j-graph-database" rel="noreferrer noopener" target="_blank">Neo4j graph database</a> on <a href="https://neo4j.com/product/auradb/" rel="noreferrer noopener" target="_blank">Aura</a> of <a href="https://graphacademy.neo4j.com" rel="noreferrer noopener" target="_blank">GraphAcademy</a> lessons.</li>



<li>Build an <a href="https://neo4j.com/product/aura-agent/" rel="noreferrer noopener" target="_blank">Aura agent</a> with tools to search, retrieve, and format lessons.</li>



<li>Expose the agent as an MCP server that can connect to an agent.</li>
</ol>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-415481" height="529" src="https://dist.neo4j.com/wp-content/uploads/20260420075138/image-226.png" width="800" /></figure>



<h2 class="wp-block-heading" id="h-the-graph-nbsp-database">The graph&nbsp;database</h2>



<p><a href="http://github.com/neo4j-graphacademy/courses" rel="noreferrer noopener" target="_blank">GraphAcademy’s lesson content is open source</a> and written in Asciidoc.&nbsp;</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-415482" height="600" src="https://dist.neo4j.com/wp-content/uploads/20260420075229/image-227.png" width="800" /></figure>



<p>I used <a href="https://github.com/asciidoctor/asciidoctor-reducer" rel="noreferrer noopener" target="_blank">asciidoctor-reducer</a> to turn the lessons into single files containing all the text, code, examples, and questions by injecting attributes and resolving any includes.</p>



<p>Each lesson was chunked into sections, embeddings were created using <a href="https://developers.openai.com/api/docs/models/text-embedding-3-small" rel="noreferrer noopener" target="_blank">OpenAI’s text-embedding-3-small model</a>, and stored in Neo4j Aura with associated meta data about the lesson (course structure, slugs, names, urls, etc).</p>



<figure class="wp-block-image"><img alt="" src="https://cdn-images-1.medium.com/max/800/1*VvJbSMVREpHHTi9eLWYHQg.png" /><figcaption class="wp-element-caption">Graph model</figcaption></figure>



<p>With the data in Neo4j I could search to find complete lessons based on something I want to learn (a <code>$subject</code>) e.g. <em>Teach me about filtering with Cypher WHERE clauses</em>.</p>


<pre class="wp-block-code"><span><code class="hljs language-sql"><span class="hljs-keyword">WITH</span> ai.text.embed(
  $subject, 
  <span class="hljs-string">'OpenAI'</span>, 
  { token: $token, <span class="hljs-keyword">model</span>: <span class="hljs-string">'text-embedding-3-small'</span> }
) <span class="hljs-keyword">AS</span> userEmbedding

<span class="hljs-keyword">MATCH</span> (c:<span class="hljs-keyword">Chunk</span>)
<span class="hljs-keyword">SEARCH</span> c <span class="hljs-keyword">IN</span> (
  VECTOR <span class="hljs-keyword">INDEX</span> chunkText
  <span class="hljs-keyword">FOR</span> userEmbedding
  <span class="hljs-keyword">LIMIT</span> $k
) SCORE <span class="hljs-keyword">AS</span> score
<span class="hljs-keyword">WHERE</span> score &gt; <span class="hljs-number">0.7</span>

<span class="hljs-keyword">MATCH</span> (c)&lt;-&#91;:HAS_CHUNK]-(l:Lesson)

<span class="hljs-keyword">RETURN</span> 
  l.slug <span class="hljs-keyword">as</span> slug, 
  l.title <span class="hljs-keyword">as</span> title, 
  l.url <span class="hljs-keyword">as</span> <span class="hljs-keyword">url</span>, 
  l.text <span class="hljs-keyword">as</span> lesson, 
  <span class="hljs-keyword">avg</span>(score) <span class="hljs-keyword">as</span> score

<span class="hljs-keyword">ORDER</span> <span class="hljs-keyword">BY</span> score <span class="hljs-keyword">DESC</span></code></span></pre>


<p>The Cypher query:</p>



<ol class="wp-block-list">
<li>Creates an embedding of the <code>$subject</code> using the same OpenAI text-embedding-3-small model that was used create embeddings of the lesson chunks.</li>



<li>Searches the <code>chunkText</code> vector index and return chunks that have a similarity <code>score > 0.7</code> .</li>



<li>Matches the lessons for the chunks.</li>



<li>Returns the lesson data, aggregating by the average score of the lesson chunks found. Averaging the score ensures single high scoring chunks don’t result in the query returning less relevant lessons as the top match.</li>
</ol>



<figure class="wp-block-image"><img alt="" src="https://cdn-images-1.medium.com/max/800/1*X3sRFtAsZAYeDfjogP7Xfg.png" /><figcaption class="wp-element-caption">Results of the cypher to search&nbsp;lessons</figcaption></figure>



<h2 class="wp-block-heading" id="h-aura-agent">Aura Agent</h2>



<p>Aura Agents allow you to create a fully functional GraphRAG agent connected to your Neo4j Aura database. </p>



<p>I used an <a href="https://neo4j.com/product/aura-agent/" rel="noreferrer noopener" target="_blank">Aura agent</a> to provide the entry point to the lessons and generate responses to queries and questions.</p>



<p>Aura Agents require:</p>



<ul class="wp-block-list">
<li>a name — to indicate what the agents does.</li>



<li>a prompt — that describes the agent’s purpose, approach, and instructions.</li>



<li>a set of tools — to retrieve data from Neo4j as context to the questions.</li>
</ul>



<p>The prompt instructs the agent to present the GraphAcademy lessons as a learning experience, including ensuring there is an objective, that misconceptions are challenged, and options given for next steps.</p>


<pre class="wp-block-code"><span><code class="hljs language-plaintext">Find and present Neo4j GraphAcademy lessons and appropriate progression 
to the follow on topics.

Provide lessons that:

- are standalone and meet a learning objective
- include examples and code snippets where relevant
- show outcomes and results of actions
- where there are potential misconceptions pose questions 
  and answers that challenge them
- have recommendations for next steps.
- provide a link to the full lesson to learn more.
- give options to either: continue to the next lesson, explore 
  related topics, or get more information.

Use the tool "get lesson for a chunk" after "search lesson chunks".</code></span></pre>


<figure class="wp-block-image"><img alt="" src="https://cdn-images-1.medium.com/max/800/1*5v-Xhbwoqa-UcwOeK5KICg.png" /><figcaption class="wp-element-caption">Neo4j Aura agent&nbsp;setup</figcaption></figure>



<p>The agent accesses the lesson data through its tools. The tools are chosen by the agent based on the task. The agent will use as many of the tools as required to complete the task.</p>



<p>The agent only needs access to a relatively smaller number of tools which search and retrieve the lesson:</p>



<ul class="wp-block-list">
<li><strong>search for a lesson</strong> — semantic search for lesson chunks</li>



<li><strong>get a complete lesson</strong> — gets a complete lesson</li>



<li><strong>get next lesson</strong> — gets the next lesson in the sequence</li>
</ul>



<figure class="wp-block-image"><img alt="" src="https://cdn-images-1.medium.com/max/800/1*MWlmNSOEDxQZ9e9Qt0iyKQ.png" /><figcaption class="wp-element-caption">Aura agent&nbsp;tools</figcaption></figure>



<p>Using the smallest number of tools to provide access to the data often results in better outcomes and tool use.</p>



<p>The agent will use the tools to find and present teaching content about Neo4j.</p>



<p>When given a query such as “How to use WITH in Cypher”, the agent will search for a lesson, get the complete lesson for the chunk returned, and provide a lesson.</p>



<figure class="wp-block-image"><img alt="" src="https://cdn-images-1.medium.com/max/800/1*HBo93pcdKqyEXsOCC3vmFw.png" /></figure>



<p>The lessons are already structured for the purpose and the prompt is enough for the agent to provide good responses.</p>



<p>The agent will provide follow on tasks and allow the user to progress through to the next lesson in the course.</p>



<figure class="wp-block-image"><img alt="" src="https://cdn-images-1.medium.com/max/800/1*VsFdNNQ0XzkaAyOZ0v4d7w.png" /></figure>



<h2 class="wp-block-heading">MCP Server</h2>



<p>Its important we meet developers were they are and to do that I need to provide external access to my agent.</p>



<p>An Aura agent can be accessed externally via a HTTPS endpoint or as an MCP server.</p>



<figure class="wp-block-image"><img alt="" src="https://cdn-images-1.medium.com/max/800/1*6LjfdSpAs_fuVDD5Xe4-Jw.png" /></figure>



<p>Agent applications (VS Code, Cursor, etc) typically have the ability to interact with MCP servers to complete tasks.</p>



<p>You can <a href="https://neo4j.com/developer/genai-ecosystem/aura-agent-getting-started/#_part_4_deploying_the_agent_to_rest_mcp" rel="noreferrer noopener" target="_blank">add your Aura agent as an MCP server</a> to you agent application allowing it to use the context your agent as context to your queries.</p>



<p>When asking the VS Code agent to <em>“Teach me how to run a Cypher statement using the Neo4j Python driver”,</em> the agent will find lessons from GraphAcademy and create responses using the lessons content and structure.</p>



<figure class="wp-block-image"><img alt="" src="https://cdn-images-1.medium.com/max/800/1*SVqRKEFmU0T_4gSTnYkcow.gif" /><figcaption class="wp-element-caption">Aura Agent used in VS&nbsp;Code</figcaption></figure>


<pre class="wp-block-code"><span><code class="hljs language-plaintext">&#91;HUMAN]
Teach me how to run a Cypher statement using the Neo4j Python driver

&#91;AI]
I'll quickly pull the official Neo4j learning guidance first, then I'll give 
you a concise, practical Python example you can run immediately.

&#91;TOOL]
Ran Neo4j Learning
Input:
{
  "query": "How to run a Cypher statement using the Neo4j Python driver
}
Output:
Here's a lesson on how to run a Cypher statement using the Neo4j Python driver,
including connection setup and query execution.
...continued...

&#91;AI]
Great use case. Here is the simplest way to run a Cypher statement with the Neo4j 
Python driver.

1. Install the driver
pip install neo4j

2. Use this minimal script:

from neo4j import GraphDatabase

URI = "neo4j+s://&lt;your-instance-id&gt;.databases.neo4j.io"
USER = "neo4j"
PASSWORD = "&lt;your-password&gt;"

def run_query():
    # Create a driver (connection factory)
    driver = GraphDatabase.driver(URI, auth=(USER, PASSWORD))

    try:
        # execute_query is the easiest API in driver v5+
        records, summary, keys = driver.execute_query(
            "RETURN 'Hello, Neo4j!' AS message"
        )

        for record in records:
            print(record&#91;"message"])

        print("Query ran successfully.")
        print("Database:", summary.database)
    finally:
        driver.close()

if __name__ == "__main__":
    run_query()

I'll quickly pull the official Neo4j learning guidance first, then I'll give 
you a concise, practical Python example you can run immediately.

3. Run it
python your_script.py

Parameterized Cypher example (recommended):

records, summary, keys = driver.execute_query(
    "RETURN $name AS name",
    name="Martin"
)
print(records&#91;0]&#91;"name"])

Why this matters:

1. Use parameters like $name instead of string concatenation for safety and performance.
2. For Neo4j Aura, use neo4j+s in the URI.
3. Close the driver when done.

If you want, I can also give you:

1. A read/write transaction example with session.execute_read and session.execute_write.
2. A small reusable Neo4j client class you can drop into your project.</code></span></pre>


<p>The response from the agent is structured as a lesson, includes good progression from a simple example, adding features, explaining the approaches used, and giving options to continue learning.</p>



<p>All the code and resources are in the repository <a href="https://github.com/martinohanlon/ga-mcp-poc" rel="noreferrer noopener" target="_blank">github.com/martinohanlon/ga-mcp-poc</a>.</p>



<h2 class="wp-block-heading">Next steps</h2>



<p>This proof-of-concept is just the beginning, an MCP server is part of our ongoing development of GraphAcademy. We are keen to meet developers where they are, and some of them are in code development environments.</p>



<p>You can learn the skills to create your own graph, MCP server, and Aura agent in the GraphAcademy courses <a href="https://graphacademy.neo4j.com/courses/llm-vectors-unstructured/?ref=martin-aura-agents" rel="noreferrer noopener" target="_blank">Introduction to Vector Indexes and Unstructured Data</a>, <a href="https://graphacademy.neo4j.com/courses/genai-mcp-build-custom-tools-python/?ref=martin-aura-agents" rel="noreferrer noopener" target="_blank">Building GraphRAG Python MCP tools</a>, and <a href="https://graphacademy.neo4j.com/courses/aura-agents?ref=martin-aura-agents" rel="noreferrer noopener" target="_blank">Building Agents in Neo4j Aura</a>.</p>



<p></p>
