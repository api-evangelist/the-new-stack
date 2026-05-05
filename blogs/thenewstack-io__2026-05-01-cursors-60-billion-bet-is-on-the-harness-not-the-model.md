---
title: "Cursor’s $60 billion bet is on the harness, not the model"
url: "https://thenewstack.io/cursor-sdk-harness/"
date: "Fri, 01 May 2026 12:00:00 +0000"
author: "Matthew Burns"
feed_url: "https://thenewstack.io/feed/"
---
<img alt="" class="webfeedsFeaturedVisual wp-post-image wp-stateless-item" height="628" src="https://cdn.thenewstack.io/media/2026/04/c29038b1-naila-conita-w84kgrt8fx0-unsplash-1024x628.jpg" style="display: block; margin: auto; margin-bottom: 20px;" width="1024" />
<p><em>I&#8217;m Matt Burns, Chief Content Officer at Insight Media Group. Each week, I round up the most important AI developments, explaining what they mean for people and organizations putting this technology to work. The thesis is simple: workers who learn to use AI will define the next era of their industries, and this newsletter is here to help you be one of them.</em></p>



<hr class="wp-block-separator has-alpha-channel-opacity" />



<p>Cursor has spent the past two months telling the industry, in different ways, that it&rsquo;s more than an IDE company. On Wednesday, it shipped <a class="ext-link" href="https://cursor.com/blog/typescript-sdk" rel="external nofollow">the Cursor SDK</a>, and on Thursday, Cursor&rsquo;s harness team <a class="ext-link" href="https://cursor.com/blog/continually-improving-our-agent-harness" rel="external nofollow">published a long read on the agent harness</a> &mdash; together, they package years of internal orchestration work and put it in any developer&#8217;s hands. In February, CEO Michael Truell <a class="ext-link" href="https://cursor.com/blog/third-era" rel="external nofollow">published an essay</a> declaring this the &ldquo;third era&rdquo; of AI software development. And just last week, Cursor announced <a class="ext-link" href="https://cursor.com/blog/spacex-model-training" rel="external nofollow">a wild partnership with SpaceX</a> to train the next generation of its proprietary Composer models on xAI&rsquo;s Colossus supercomputer.</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>Cursor thinks the AI model is becoming a commodity, and the product that wins the next decade is the harness around it.</p>
</blockquote>



<p>Read together, the message is unambiguous: Cursor thinks the AI model is becoming a commodity, and the product that wins the next decade is the harness around it. The strongest confirmation came entirely from outside Cursor. Google told <em>The New Stack</em> this week that it doesn&rsquo;t care which coding tool developers use, be it Gemini, Claude Code, or Cursor.&nbsp;</p>



<h2 class="wp-block-heading" id="h-cursor-is-moving-past-being-just-an-ide-company">Cursor is moving past being just an IDE company</h2>



<p>The pieces have been sliding into place for months: This week, Cursor released an SDK that made the shift explicit. When Cursor 3 shipped <a class="local-link" href="https://thenewstack.io/cursor-3-demotes-ide/">earlier this month</a>, Jani MSV covered it for <em>The New Stack</em> with blunt terms: The IDE is now a fallback. Agents spin up dedicated cloud VMs, work for hours, and return logs, video recordings, and live previews. According to Truell&rsquo;s &ldquo;third era&rdquo; post, agent usage at Cursor has grown more than 15x in the last year. </p>



<p>Twelve months ago, Cursor had 2.5 times as many Tab autocomplete users as agent users. Today, it has 2x as many agent users as Tab users. Inside the Cursor itself, Truell says more than a third of internal pull requests are created by agents working in cloud VMs. He expects &ldquo;the vast majority&rdquo; of development work to look that way within a year.</p>



<p>If Truell is right (and I think he is), the IDE will matter less, and the harness will matter more. That&rsquo;s why on April 29, Cursor <a class="ext-link" href="https://cursor.com/blog/typescript-sdk" rel="external nofollow">released the Cursor SDK</a> in public beta. It&rsquo;s a Typescript package ( <code>npm install @cursor/sdk</code> ) that lets developers build agents directly on Cursor&rsquo;s harness, model-agnostic, deployable locally or on Cursor Cloud against dedicated VMs. </p>



<p>The harness ships with codebase indexing, MCP server support, subagents, and observability hooks.&nbsp;This puts Cursor in the same race as OpenAI&#8217;s Agents SDK and Anthropic&#8217;s Claude Agent SDK, but with a harness that&#8217;s used at scale on its own users. Cursor positions Composer 2 as the cheap default &mdash; priced at $0.50 per million input tokens versus Claude Opus 4.6&#8217;s $5 per million input tokens &mdash; and claims competitive benchmark performance. But the SDK supports any model you want.</p>



<p>Cursor positions Composer 2 as the cheap default &mdash; priced at $0.50 per million input tokens versus Claude Opus 4.6&#8217;s $5 per million input tokens &mdash; and claims competitive benchmark performance. But the SDK supports any model you want.</p>



<p>The SpaceX partnership lands on top of all of this. Cursor&rsquo;s blog states the company has been &ldquo;bottlenecked by compute&rdquo; and will now &ldquo;leverage xAI&rsquo;s Colossus infrastructure to dramatically scale up the intelligence of our models.&rdquo; The partnership became even more interesting when <a class="ext-link" href="https://www.bloomberg.com/news/articles/2026-04-21/spacex-says-has-agreement-to-acquire-cursor-for-60-billion" rel="external nofollow"><em>Bloomberg</em></a> and <em><a class="ext-link" href="https://techcrunch.com/2026/04/21/spacex-is-working-with-cursor-and-has-an-option-to-buy-the-startup-for-60-billion/" rel="external nofollow">TechCrunch</a></em> reported that SpaceX has said it will either pay Cursor $10 billion for the companies&rsquo; work together or acquire Cursor outright for $60 billion later this year. Musk likely isn&rsquo;t buying Composer 2&rsquo;s weights alone. xAI already has Grok and Colossus. The more strategic asset is Cursor&rsquo;s harness and its line to developers who actually use these tools every day.</p>



<h2 class="wp-block-heading" id="h-what-a-harness-is-and-why-it-s-suddenly-the-most-valuable-ai-layer">What a harness is and why it&#8217;s suddenly the most valuable AI layer</h2>



<p>A harness is the software wrapper that turns a raw frontier model &mdash; Claude, GPT, Gemini, Composer &mdash; into something that can actually do real work inside your codebase. The model is the brain; the harness acts on its instructions and provides feedback to the brain.</p>



<p>A harness picks which files, docs, commits, and tool outputs the model gets to see. This is context management, and Cursor&rsquo;s harness team writes that doing it well is a multi-year engineering project. The harness calls tools: the terminal, the linter, the MCP server, and the internal APIs. It spawns subagents, even using separate models with separate prompts to better plan, edit, or debug in parallel. It runs hooks for observability, and it enforces security boundaries for better access control. And it stitches all of that into a loop that the model iterates inside until the task is done.</p>



<p>Harness&#8217;s work looks like unglamorous engineering. Cursor&rsquo;s team writes that they spend &ldquo;weeks&rdquo; tuning the harness model-by-model because each one has different strengths and quirks. They warn about &ldquo;context rot&rdquo; &mdash; the way one bad tool call can poison every decision an agent makes after it. They run continuous A/B tests on real usage, watching a metric they call Keep Rate, which measures how much agent-written code actually survives in the final commit. None of that workshops into in a benchmark headline. All of it is what makes the difference between an agent that closes a ticket and one that ships broken code.</p>



<p>There&#8217;s a reason this matters beyond software: The same shape will replicate everywhere agents are eventually deployed. The model is what understands the legal contract, the patient chart, or the financial model. The harness is what gives it the right context, the right tools, the right boundaries, and the right oversight. Whoever owns the harness layer in your domain owns the product.</p>



<h2 class="wp-block-heading" id="h-google-s-we-don-t-care-is-proof-that-models-are-commodities">Google&rsquo;s &ldquo;we don&rsquo;t care&rdquo; is proof that models are commodities</h2>



<p>The most candid quote from a hyperscaler I&rsquo;ve seen came from Google Cloud&#8217;s Chief Evangelist Richard Seroter. <a class="local-link" href="https://thenewstack.io/google-doesnt-care/">As Frederic Lardinois writes on <em>The New Stack</em> this week</a>, Seroter said: &ldquo;developer loyalty is at zero right now.&rdquo; Google&rsquo;s position is that it doesn&rsquo;t matter whether developers use Cursor, Copilot, Code, or Claude Code. </p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>Google&rsquo;s position is that it doesn&rsquo;t matter whether developers use Cursor, Copilot, Code, or Claude Code. </p>
</blockquote>



<p>Six months ago, Google was racing to put Gemini inside VS Code. Now it&rsquo;s apparently comfortable letting the harness vendors fight it out, because Google&rsquo;s moats &mdash; search, Android, Cloud, the compute under the whole stack &mdash; sit at a different layer than the IDE entirely. When a company with a frontier model is comfortable with developers using someone else&rsquo;s interface, it is at least acknowledging that the interface and infrastructure layers may matter more than model loyalty. That&rsquo;s the cleanest expression of model commoditization I&rsquo;ve seen, said out loud, by the company best positioned to know.</p>



<p>It&rsquo;s not just Google. Two weeks ago, Jani <a class="local-link" href="https://thenewstack.io/ai-agent-harness-pricing-split/">wrote on our site</a> that Anthropic, OpenAI, Google, and Microsoft all agree the harness is the product &mdash; they just disagree on what to charge for it. Anthropic&#8217;s Managed Agents pricing adds a hosted-agent runtime fee on top of model usage. Cursor&rsquo;s SDK launched with per-token pricing on top of Composer 2 at a fraction of the Claude Opus&rsquo;s rate. </p>



<p>The pattern is clear: Model providers are under pressure to make intelligence cheaper and more interchangeable, while harness vendors are charging for orchestration, observability, and the integration work that actually makes agents productive. Both Anthropic&rsquo;s enterprise harness and Cursor&rsquo;s SDK are betting on the same future: cheap, swappable intelligence and proprietary orchestration.</p>



<p>What this means for the rest of us depends on where you sit. If you&rsquo;re a developer, the model you use day-to-day is going to keep changing under you, and your harness is going to keep getting smarter. Worry less about which model is the popular kid this month and more about whether your tools are designed to swap models gracefully. </p>



<p>If you&rsquo;re a CIO, your AI vendor lock-in shouldn&rsquo;t sit at the model layer &mdash; it should sit at the harness, and you should be asking vendors hard questions about how theirs handles context, tools, observability, and model-swapping. </p>



<p>If you work outside of engineering, don&rsquo;t look away. The same architecture &mdash; commodity intelligence underneath, proprietary harness on top &mdash; is what&#8217;s coming next for legal, finance, operations, design, and editorial work. The companies building those harnesses are the ones who&#8217;ll own how the work gets done.</p>



<hr class="wp-block-separator has-alpha-channel-opacity" />



<h2 class="wp-block-heading" id="h-past-editions">Past Editions</h2>



<figure class="wp-block-embed is-type-wp-embed is-provider-the-new-stack wp-block-embed-the-new-stack"><div class="wp-block-embed__wrapper">
<blockquote class="wp-embedded-content"><a class="local-link" href="https://thenewstack.io/openai-workspace-agents-gpt-5-5/">The real story from OpenAI&rsquo;s big week is Workspace Agents, not GPT-5.5</a></blockquote>
</div></figure>



<figure class="wp-block-embed is-type-wp-embed is-provider-the-new-stack wp-block-embed-the-new-stack"><div class="wp-block-embed__wrapper">
<blockquote class="wp-embedded-content"><a class="local-link" href="https://thenewstack.io/google-and-openai-are-making-a-run-at-claudes-desktop-moat-and-anthropic-is-making-it-easy/">Google and OpenAI are making a run at Claude&#8217;s desktop moat, and Anthropic is making it easy</a></blockquote>
</div></figure>
<p>The post <a href="https://thenewstack.io/cursor-sdk-harness/">Cursor&#8217;s $60 billion bet is on the harness, not the model</a> appeared first on <a href="https://thenewstack.io">The New Stack</a>.</p>
