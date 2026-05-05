---
title: "Most AI coding is “like taking your Ferrari to buy milk”: IBM’s Neel Sundaresan"
url: "https://thenewstack.io/ibm-bob-agentic-coding/"
date: "Sun, 03 May 2026 14:12:00 +0000"
author: "Darryl K. Taft"
feed_url: "https://thenewstack.io/feed/"
---
<img alt="Stylized illustration of a driver gripping the wheel of a red sports car at high speed, with motion lines streaking past." class="webfeedsFeaturedVisual wp-post-image wp-stateless-item" height="683" src="https://cdn.thenewstack.io/media/2026/05/c4c2637a-screenshot-2026-05-02-at-08.21.15-1024x683.png" style="display: block; margin: auto; margin-bottom: 20px;" width="1024" />
<p><a class="ext-link" href="https://www.linkedin.com/in/neel-sundaresan-a964a2/" rel="external nofollow">Neel Sundaresan</a> doesn&#8217;t answer three questions. One of them, he says with some amusement, is why IBM Bob is named Bob.</p>



<p>That particular deflection is telling. Sundaresan &mdash; GM of Automation and AI at IBM Software, founding engineer of <a class="local-link" href="https://thenewstack.io/microsoft-makes-github-copilot-free-in-vs-code/">Microsoft GitHub Copilot</a>, and former researcher at <a class="local-link" href="https://thenewstack.io/ibm-tackles-shadow-ai-an-enterprise-blind-spot/">IBM</a> before that &mdash; is not a product marketing guy. He&#8217;s a researcher who became a builder who became an executive, and the through line across all three roles is the same obsession: What does it take to <a class="local-link" href="https://thenewstack.io/how-google-unlocks-and-measures-developer-productivity/">make software developers more productive</a>, and what keeps getting in the way?</p>



<p>He&#8217;s been working on that question since 2000, before transformers, before <a class="local-link" href="https://thenewstack.io/introduction-to-llms/">large language models</a>, before anyone outside the then-mall research community thought AI and developer tooling belonged in the same sentence. The arc from there to IBM Bob &mdash; <a class="local-link" href="https://thenewstack.io/ibm-bob-agentic-development/"><strong>announced this week and already running at 80,000 users inside IBM</strong></a> &mdash; is longer than the launch press release suggests.</p>



<h2 class="wp-block-heading" id="h-starting-before-anyone-was-watching">Starting before anyone was watching</h2>



<p>The first system Sundaresan built for developer productivity wasn&#8217;t anything like what we&#8217;d recognize as an AI coding tool today. It was a recommender system for API calls.</p>



<p>&#8220;30% of developer code is API calls,&#8221; he tells <em>The New Stack</em> in a wide-ranging interview. &#8220;If you do a class dot something, you get a long list of functions to call, and you gotta pick from there. That itself is a friction point.&#8221; </p>



<figure class="wp-block-image size-large"><img alt="" class="wp-image-22821743" height="487" src="https://cdn.thenewstack.io/media/2026/05/428cd83c-screenshot-2026-05-02-at-08.18.19-1024x487.png" width="1024" /><figcaption class="wp-element-caption"><em>Sundaresan stands next to the IBM Bob mascot. (Credit Sundaresan&#8217;s LinkedIn profile)</em></figcaption></figure>



<p>The goal wasn&#8217;t to generate code. It was to surface the right function call at the right moment &mdash; essentially a search ranking problem applied to a developer&#8217;s autocomplete experience.</p>



<p>The model wasn&#8217;t a transformer. It wasn&#8217;t even a deep learning model in the modern sense. But developers loved it, he says. And that early signal &mdash; that reducing friction at a specific, small moment in the development workflow produced outsized satisfaction &mdash; shaped how Sundaresan thinks about the problem to this day.</p>



<p>&#8220;Coding is an analytical task. It&#8217;s different from shopping [online],&#8221; he says. &#8220;If the system makes a wrong recommendation, or if it makes a recommendation that kind of interferes with my thought process &mdash; that matters.&#8221; </p>



<p>The user experience, he argues, is orthogonal to whatever the AI is doing underneath. You can have a better model and a worse product if you get the surface wrong.</p>



<p>He watched the model world evolve from there: Long Short-Term Memory models, early encoder-decoder architectures, the <a class="ext-link" href="https://proceedings.neurips.cc/paper_files/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf" rel="external nofollow">Google transformer paper</a>, and the first GPT. At each stage, his team had already seen the problem they were trying to solve. The models just weren&#8217;t powerful enough yet. &#8220;If you go back and look at our publications, we have publications in all of this,&#8221; Sundaresan says. &#8220;Every paper would say, here&#8217;s the model for this, here&#8217;s the model for that.&#8221;</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>&ldquo;Even our customers were not comfortable sending over data to our own cloud. They wanted the data on the client. So, we would actually have the model run on the laptop &mdash; a lot of engineering had to be done to make sure it can work within the laptop.&rdquo;</p>
</blockquote>



<p>When frontier models finally arrived with enough capability to make the bigger bets pay off, Copilot was the result, he says. But by then, Sundaresan had also spent years watching what the models got wrong &mdash; and what the product design around them got wrong. The training cutoffs produced confident misinformation. The tendency to reach for the most powerful (and most expensive) model for every task, regardless of whether it warranted it. The difficulty of running capable models in the constrained environments in which enterprises actually operate.</p>



<p>&#8220;Even our customers were not comfortable sending over data to our own cloud,&#8221; he says of the early Microsoft years. &#8220;They wanted the data on the client. So, we would actually have the model run on the laptop &mdash; a lot of engineering had to be done to make sure it can work within the laptop.&#8221;</p>



<h2 class="wp-block-heading" id="h-why-ibm">Why IBM?</h2>



<p>The obvious question, when Sundaresan describes this history, is why he took that accumulated knowledge to IBM rather than somewhere flashier. He&#8217;s direct about it: he was looking for a change after a decade at Microsoft, and IBM made a compelling case.</p>



<p>But the less obvious answer is that, for his particular problem, IBM&#8217;s liabilities are actually assets.</p>



<p>&#8220;Within software, we have almost 20,000 people. We have infrastructure, we have consulting. There are a large number of users within IBM,&#8221; he says. &#8220;If I could create something that could benefit them, that itself is a giant product.&#8221; The internal deployment &mdash; what IBM calls &#8220;client zero&#8221; &mdash; gave him something no external product launch can: a massive, diverse, captive user base willing to absorb early friction in exchange for genuine productivity gains.</p>



<p>The other asset is the workload mix. IBM&#8217;s internal developer population writes <a class="local-link" href="https://thenewstack.io/python/">Python</a> and <a class="local-link" href="https://thenewstack.io/rust-programming-language-guide/">Rust</a>, yes &mdash; but also <a class="ext-link" href="https://www.ibm.com/docs/en/zos-basic-skills?topic=zos-pli" rel="external nofollow">PL/I</a>, <a class="local-link" href="https://thenewstack.io/cobol-everywhere-will-maintain/">COBOL</a>, <a class="ext-link" href="https://www.ibm.com/docs/da/zos-basic-skills?topic=collection-basic-jcl-concepts" rel="external nofollow">mainframe JCL</a>, and languages Sundaresan described as &#8220;custom languages, like slang.&#8221; If Bob could handle that range, it could handle anything an enterprise customer would bring.</p>



<p>&#8220;Before we even go knock on the doors of a client, we have a story to tell,&#8221; he says.</p>



<p>He was also direct about what he was building against. Not a horizontal tool for any developer doing any task, but a system optimized specifically for the enterprise conditions that most AI coding tools treat as edge cases: legacy codebases, strict compliance requirements, hybrid environments, and the very real cost of <a class="local-link" href="https://thenewstack.io/ai-generated-code-needs-refactoring-say-76-of-developers/">AI-generated code</a> that looks production-ready but isn&#8217;t.</p>



<h2 class="wp-block-heading" id="h-the-cost-problem-nobody-talks-about">The cost problem nobody talks about</h2>



<p>One of the more candid moments in a conversation with Sundaresan is when he describes how most developers use AI coding tools left to their own devices.</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>&#8220;It&#8217;s like taking your Ferrari to go buy milk. You don&#8217;t need to.&#8221;</p>
</blockquote>



<p>&#8220;People will just say, &#8216;What model do you want to use?&#8217; And people will pick the latest Sonnet 4.7 or whatever. And they might be running a simple prompt, but it will cost $40 for a million tokens,&#8221; he said. &#8220;It&#8217;s like taking your Ferrari to go buy milk. You don&#8217;t need to.&#8221;</p>



<p>Bob doesn&#8217;t expose the underlying model to users. It routes tasks automatically &mdash; to Anthropic Claude, Mistral open-source models, IBM Granite, or one of several proprietary, fine-tuned models built specifically for Bob&#8217;s environment &mdash; based on what the task actually requires.</p>



<p>That routing intelligence is where Sundaresan thinks the real architectural work is. &#8220;It&#8217;s not slapping on a model into the system,&#8221; he says. &#8220;It is bringing the model, bringing the experience, but also bringing the architecture that provides a great experience. All three have to come together. The model is only one part of the equation.&#8221;</p>



<p>He described running A/B experiments on IBM&#8217;s internal user base &mdash; testing frontier model variants against one another, monitoring usage patterns, and identifying where costly models were used for tasks that cheaper ones handled equally well. The internal deployment made that kind of experimentation possible at a scale no early-stage product could afford.</p>



<h2 class="wp-block-heading" id="h-on-where-the-agentic-market-is-actually-going">On where the agentic market is actually going</h2>



<p>Ask Sundaresan about the hype cycle around agentic AI, and he&#8217;ll give you the researcher&#8217;s answer, not the GM&#8217;s.</p>



<p>&#8220;There&#8217;s no smoke without fire,&#8221; he tells <em>The New Stack</em>. &#8220;If hype is the smoke, there is fire somewhere. It may not be as big as the smoke. But there is fire.&#8221;</p>



<p>His read is that agent-based development is real, but it&#8217;s not new. Service-based development, API-based development, agent-based development &mdash; all of it existed before. What&#8217;s changed is that the interface is now probabilistic and conversational rather than deterministic and programmatic. That shift creates genuine new capability, but also genuine new risk.</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>&#8220;We could be afraid and not do anything at all, or we could go forward bravely but systematically.&#8221;</p>
</blockquote>



<p>&#8220;You can also distract it,&#8221; he says of agent systems. &#8220;You can ask questions you&#8217;re not supposed to ask, or reveal information that it&#8217;s not supposed to reveal.&#8221; The 91% AI project failure rate he&#8217;s seen cited, he argues, comes down to discipline &mdash; or the lack of it. Companies assume that signing a deal with a frontier model provider is sufficient. It isn&#8217;t. &#8220;You need the discipline that you&#8217;re following before you incorporate them into your software product,&rdquo; Sundaresan says.</p>



<p>The direction he&#8217;s watching, and which he thinks demands more attention than it&#8217;s getting: agents that talk to other agents, eventually in machine-native languages that humans can&#8217;t directly read. &#8220;If there are errors in those derivative languages, that error could explode,&#8221; he says. &#8220;There are lots of things to come. We could be afraid and not do anything at all, or we could go forward bravely but systematically.&#8221;</p>



<p></p>
<p>The post <a href="https://thenewstack.io/ibm-bob-agentic-coding/">Most AI coding is &#8220;like taking your Ferrari to buy milk&#8221;: IBM&#8217;s Neel Sundaresan</a> appeared first on <a href="https://thenewstack.io">The New Stack</a>.</p>
