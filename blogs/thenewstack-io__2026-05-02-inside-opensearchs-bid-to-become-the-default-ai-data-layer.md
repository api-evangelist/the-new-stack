---
title: "Inside OpenSearch’s bid to become the default AI data layer"
url: "https://thenewstack.io/opensearch-ai-data-layer/"
date: "Sat, 02 May 2026 16:00:00 +0000"
author: "Anil Inamdar"
feed_url: "https://thenewstack.io/feed/"
---
<img alt="Abstract illustration of horizontal earthy strata in shades of brown and tan, representing a stable AI data layer and infrastructure substrate for OpenSearch applications." class="webfeedsFeaturedVisual wp-post-image wp-stateless-item" height="655" src="https://cdn.thenewstack.io/media/2026/05/fe0e7b3c-yana-kravchuk-qmtrqesja6o-unsplash-1024x655.jpg" style="display: block; margin: auto; margin-bottom: 20px;" width="1024" />
<p>Most of the engineering teams I work with started with <a class="ext-link" href="https://opensearch.org/" rel="external nofollow">open source OpenSearch</a> for log analytics and enterprise search. But as their requirements have since shifted to semantic retrieval and agent memory, they&rsquo;re now trying to figure out just how much of that AI application stack they can consolidate onto infrastructure they already run.</p>



<p>The first quarter of 2026 has been very good news on that front. OpenSearch 3.5 and 3.6, which shipped in February and April, respectively, are worth understanding if you inherited an OpenSearch deployment and are now being asked to run agents on it. Here&rsquo;s what to know.</p>



<h2 class="wp-block-heading" id="h-dense-and-sparse-vector-search-aren-t-interchangeable">Dense and sparse vector search aren&rsquo;t interchangeable</h2>



<p>Teams like to start with <code>knn_vector</code>, and that&rsquo;s understandable. Point it at your embedding model&rsquo;s output dimension, enable k-NN on the index, and you are doing approximate nearest neighbor search. The default (Faiss, HNSW, L2 distance) covers a pretty darn wide range of use cases without much configuration.</p>



<p>The change in 3.6 that matters for organizations running this at scale is Better Binary Quantization, now integrated from the Lucene project. BBQ compresses high-dimensional float vectors into compact binary representations using quantization methods derived from RaBitQ, slashing the memory footprint by 32x.&nbsp;</p>



<p>On the Cohere-768-1M dataset, BBQ recall at 100 results is 0.63, compared to 0.30 for Faiss Binary Quantization. With oversampling and rescoring, it exceeds 0.95 on large production datasets. The OpenSearch project is also working to make 32x compression the default, which would eliminate the need for manual tuning.</p>



<p>Where <code>knn_vector</code> runs into trouble is term-level precision. Dense semantic search retrieves results based on meaning (which is good!), but it can miss exact-term relevance. A query for a specific product model number or technical identifier, for example, may bring up results that are conceptually similar but not the precise match you wanted.&nbsp;</p>



<p>This is the problem <code>sparse_vector</code> alleviates. Instead of representing a document as a point in continuous vector space, it stores it as a map of token-weight pairs. Each token is a vocabulary term, and each weight reflects how central that term is to the document&rsquo;s meaning.</p>



<p>These 3.6 additions include BBQ flat index support for exact-recall workloads and the SEISMIC algorithm for neural sparse approximate nearest neighbor search, enabling large-scale sparse retrieval <em>without</em> a full index scan.</p>



<p>Most production AI search applications use both. Hybrid search combines dense semantic recall with sparse neural precision, and both field types are built around that pattern in mind. Most teams, in my experience, get more mileage out of understanding when each one earns its place in the pipeline than from picking a winner.</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>&#8220;Hybrid search combines dense semantic recall with sparse neural precision, and both field types are built around that pattern in mind.&#8221;</p>
</blockquote>



<h2 class="wp-block-heading" id="h-opensearch-is-absorbing-the-agent-memory-problem">OpenSearch is absorbing the agent memory problem</h2>



<p>Before 3.5, teams building multi-turn conversational agents had to solve memory outside of OpenSearch. You would maintain a session store elsewhere and manage context scoping in application logic (while wiring it all yourself).&nbsp;</p>



<p>OpenSearch 3.5 moves agentic conversation memory directly into the ML commons, with hook-based context management that gives developers the reins over how memory is stored, scoped, and retrieved during an agent session.</p>



<p>OpenSearch 3.6 goes even further. New semantic and <a class="local-link" href="https://thenewstack.io/supercharge-your-rag-app-with-agentic-hybrid-search/">hybrid search</a> APIs enable agents to search stored memory using vector similarity, keyword matching, or both. An agent engaged in a long conversation can now retrieve contextually relevant prior exchanges rather than relying solely on recency, which matters when the relevant history is not the most recent turn. The V2 Chat Agent provides a cleaner interface for chat-based workflows while retaining tool and memory integration. A rebuilt Dashboards chat interface adds persistent conversation history that&rsquo;s backed by the ML Commons Agent Memory APIs.</p>



<p>The practical effect of all this is that agent memory is handled natively by the platform rather than reinvented by each team. Hook-based APIs leave enough room for engineers to customize behavior wherever their requirements diverge from defaults, without requiring them to build the whole thing from scratch.</p>



<h2 class="wp-block-heading" id="h-some-of-the-less-covered-changes-that-matter-in-production">Some of the less-covered changes that matter in production</h2>



<p>Token usage tracking in the ML Commons agent framework is one of the most immediately useful additions in 3.6. Every LLM call during agent execution is instrumented to extract and aggregate token counts (per turn and per model) with no configuration required. It supports Amazon Bedrock Converse, OpenAI v1, and Gemini v1beta. If your team has been running agents without visibility into what API calls cost or which steps are expensive, this is a clear win.</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>&#8220;If your team has been running agents without visibility into what API calls cost or which steps are expensive, this is a clear win.&#8221;</p>
</blockquote>



<p>The async encryption refactor is less visible but fixes an important reliability issue. The legacy EncryptorImpl used a blocking CountDownLatch with a three-second timeout to manage master key initialization. During concurrent requests, this caused thread contention and a race condition where multiple tenants hitting the encryption layer simultaneously could trigger duplicate key generation.</p>



<p>The new implementation, contributed by my NetApp Instaclustr engineering colleague <a class="ext-link" href="https://www.linkedin.com/in/muneer-kolarkunnu/" rel="external nofollow">Abdul Muneer</a>, replaces that with an ActionListener-based approach that queues requests and processes them once the key is ready. (Side note: want to contribute yourself? Read Abdul&rsquo;s blog about it <a class="ext-link" href="https://opensearch.org/blog/how-to-start-contributing-to-opensearch-a-beginners-guide-based-on-my-journey/" rel="external nofollow">here</a>.) In high-throughput environments, the old design produced intermittent failures under load.</p>



<p>Turning to observability: until 3.6, debugging a failed multi-step agent execution meant cobbling together your own instrumentation. OpenSearch now addresses this with Application Performance Monitoring built on OpenTelemetry standards, bringing RED metrics, distributed traces, service maps, and SLO tracking into OpenSearch Dashboards.</p>



<p>Time-series metrics are routed to Prometheus, trace data stays in <a class="local-link" href="https://thenewstack.io/opensearch-3-2-delivers-hybrid-search-enhanced-observability-tools/">OpenSearch</a>, and Data Prepper handles the split based on query patterns. The agent traces plugin gives teams a dedicated view for debugging agent executions directly from the UI.</p>



<h2 class="wp-block-heading" id="h-is-opensearch-becoming-the-default-data-layer-for-ai-applications">Is OpenSearch becoming the default data layer for AI applications?</h2>



<p>The opensearch-agent-server in 3.6 adds in a multi-agent orchestration layer for integrating OpenSearch Dashboards and the <a class="local-link" href="https://thenewstack.io/mcp-the-missing-link-between-ai-agents-and-apis/" id="https://thenewstack.io/mcp-the-missing-link-between-ai-agents-and-apis/" type="link">Model Context Protocol</a>. MCP has become the standard for how AI systems communicate with external tools and data sources. Its inclusion here says something about intent. The project is moving toward OpenSearch as a full participant in agentic tooling ecosystems, with MCP as the connective tissue.</p>



<p>That direction was visible with 3.5, when the project introduced the experimental Agent-User Interaction protocol. OpenSearch is building toward a durable, observable, memory-capable substrate for AI applications, with the protocol support required to fit cleanly into a broader agentic stack.</p>



<p>Teams not yet considering agents will still gain clear value from 3.5 and 3.6, particularly on the vector search and compression side. But the roadmap is clear enough, in my view.</p>



<p>OpenSearch isn&rsquo;t trying to be a better Elasticsearch; it is focused on being the data layer on which AI applications are built.</p>
<p>The post <a href="https://thenewstack.io/opensearch-ai-data-layer/">Inside OpenSearch&#8217;s bid to become the default AI data layer</a> appeared first on <a href="https://thenewstack.io">The New Stack</a>.</p>
