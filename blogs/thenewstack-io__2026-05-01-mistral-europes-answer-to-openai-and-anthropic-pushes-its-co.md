---
title: "Mistral, Europe’s answer to OpenAI and Anthropic, pushes its coding agents to the cloud"
url: "https://thenewstack.io/mistral-vibe-cloud-agents/"
date: "Fri, 01 May 2026 14:46:14 +0000"
author: "Paul Sawers"
feed_url: "https://thenewstack.io/feed/"
---
<img alt="A developer typing on a laptop surrounded by multiple code windows and a central cloud upload icon, depicting cloud-based coding agents" class="webfeedsFeaturedVisual wp-post-image wp-stateless-item" height="640" src="https://cdn.thenewstack.io/media/2026/05/f08b9a4e-hj-project-jykqoo7i25w-unsplash-1024x640.png" style="display: block; margin: auto; margin-bottom: 20px;" width="1024" />
<p>Countless companies are capitalizing on the AI boom, building everything from <a class="local-link" href="https://thenewstack.io/what-are-ai-code-assistants-and-how-should-you-use-them/">coding assistants</a> to customer support bots. But only a handful are building the foundational AI models themselves &mdash; the underlying systems that power it all.</p>



<p>That group is dominated largely by OpenAI, Anthropic, and Google, with the likes of <a class="ext-link" href="https://mistral.ai/" rel="external nofollow">Mistral AI</a> sitting just outside that elite circle. Founded out of Paris in 2023, Mistral has raised billions from a who&rsquo;s who of investors, <a class="ext-link" href="https://techcrunch.com/2024/02/27/microsoft-made-a-16-million-investment-in-mistral-ai/" rel="external nofollow">including Microsoft</a> and <a class="ext-link" href="https://mistral.ai/news/mistral-ai-and-nvidia-partner-to-accelerate-open-frontier-models" rel="external nofollow">Nvidia</a>, all while pushing a more open approach &mdash; releasing open-weight models and giving developers more control over how they run them.</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>On Wednesday, Mistral debuted a new model, Mistral Medium 3.5, alongside a system that lets its coding agents run in the cloud.</p>
</blockquote>



<p>Now, the company is edging toward the same territory as some of its larger rivals. On Wednesday, Mistral <a class="ext-link" href="https://mistral.ai/news/vibe-remote-agents-mistral-medium-3-5" rel="external nofollow">debuted</a> a new model, <a class="ext-link" href="https://docs.mistral.ai/models/model-cards/mistral-medium-3-5-26-04" rel="external nofollow">Mistral Medium 3.5</a>, alongside a system that lets its coding agents run in the cloud, where they can keep working in the background while developers get on with other things.</p>



<p>Additionally, Mistral is adding a &ldquo;work mode&rdquo; to <a class="ext-link" href="https://chat.mistral.ai/chat" rel="external nofollow">Le Chat</a>, its ChatGPT-style interface, that can take on longer jobs by calling tools in parallel, as it looks to move beyond chat and into doing actual work.</p>



<h2 class="wp-block-heading" id="h-teleport-to-the-cloud">Teleport to the cloud</h2>



<p>Mistral&rsquo;s coding assistant, <a class="ext-link" href="https://mistral.ai/products/vibe" rel="external nofollow">Vibe</a>, has until now mostly lived in the terminal, where developers could ask it to read a repo, edit files, run commands, fix bugs, or write tests from the command line. With this update, Mistral is pushing it into a different mode &mdash; one where you can spin up multiple agents in the cloud, let them work through tasks independently in isolated sandboxed environments, and come back to review what they&rsquo;ve done. </p>



<p>Sessions can be started locally from the CLI or Le Chat and &#8220;teleported&#8221; to the cloud mid-task, preserving the full context &mdash; including the task itself, previous steps, and any changes made so far. From there, the agents continue running remotely, without being tied to the developer&rsquo;s machine.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full"><img alt="Teleport to the cloud" class="wp-image-22821603" height="530" src="https://cdn.thenewstack.io/media/2026/05/0036b09b-teleport.gif" width="800" /><figcaption class="wp-element-caption"><em>Teleport to the cloud</em></figcaption></figure>
</div>


<p>So instead of sitting in a loop, prompting and checking results, developers can hand off chunks of work and allow them to run in the background. Those tasks might include writing new features, updating code, or preparing changes as draft pull requests for later review.</p>



<p>Users can also launch Vibe directly from Le Chat. For example, they could ask it to build a sales dashboard, and it would run the task in a remote setup before returning a finished branch or a draft pull request.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full"><img alt="Launching Vibe from Le Chat" class="wp-image-22821602" height="497" src="https://cdn.thenewstack.io/media/2026/05/ea4865c7-launchvibefromlechat.gif" width="800" /><figcaption class="wp-element-caption"><strong><em>Launching Vibe from Le Chat</em></strong></figcaption></figure>
</div>


<p>On top of that, Mistral is adding a &ldquo;work mode&rdquo; within Le Chat, where users can set broader tasks &mdash; like pulling together a meeting brief or updating documents &mdash; and have the system work through them using connected tools.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full"><img alt="Work Mode" class="wp-image-22821604" height="489" src="https://cdn.thenewstack.io/media/2026/05/d21a7658-workmodegif.gif" width="800" /><figcaption class="wp-element-caption"><em>Work Mode</em></figcaption></figure>
</div>


<p><a class="ext-link" href="https://www.linkedin.com/in/pini-wietchner-45224513a/" rel="external nofollow">Pini Wietchner</a>, who works on the Mistral product team, says in an <a class="ext-link" href="https://www.youtube.com/watch?v=KaMbzM9dsTc" rel="external nofollow">online discussion</a> that the company has been dogfooding Vibe internally for its latest launch, with most of its pull requests handled remotely.</p>



<p>&ldquo;We&rsquo;ve seen internally that Vibe has been really effective,&rdquo; Wietchner says during that company-produced YouTube video. &ldquo;Our customers want to use agents both locally and remotely. A local agent is great for a developer working in their IDE or terminal on a coding task. Remote agents let them run multiple agents in parallel, in a secure way using our sandboxing setup.&rdquo;</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>&#8220;Our customers want to use agents both locally and remotely. A local agent is great for a developer working in their IDE or terminal on a coding task. Remote agents let them run multiple agents in parallel.&#8221;</p>
</blockquote>



<h2 class="wp-block-heading" id="h-model-behavior">Model behavior</h2>



<p>Underpinning all this is Mistral Medium 3.5, a 128B parameter model with a 256k context window, designed to handle longer, more involved tasks rather than quick prompts.</p>



<p>Mistral is positioning Medium 3.5 against models already used for similar workloads &mdash; including Claude Sonnet, Kimi K2.5, GLM 5.1, and Qwen 3.5, as shown in its reported results. On standard tests like SWE-bench Verified, which measures how well models can resolve real GitHub issues, the company reports competitive scores, alongside results on domain-specific tasks in telecom, retail, and banking. These figures come from Mistral&rsquo;s own evaluations and may vary under different setups or conditions.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large"><img alt="Agentic benchmarks vs. competing models" class="wp-image-22821601" height="750" src="https://cdn.thenewstack.io/media/2026/05/8f19cc18-frame-2147228534-1024x750.png" width="1024" /><figcaption class="wp-element-caption"><em>Agentic benchmarks vs. competing models</em></figcaption></figure>
</div>


<p>For those all-in on Mistral&rsquo;s stack, a more relevant comparison, perhaps, is against its own earlier models. By that measure, Medium 3.5 marks a step up from previous coding-focused releases <span style="margin: 0px; padding: 0px;">such as&nbsp;<a class="ext-link" href="https://huggingface.co/mistralai/Devstral-2-123B-Instruct-2512" rel="external nofollow" target="_blank">Devstral 2</a>, according to</span> the company&rsquo;s reported Swe-Bench Verified results.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large"><img alt="Agentic benchmarks vs. previous Mistral models" class="wp-image-22821600" height="607" src="https://cdn.thenewstack.io/media/2026/05/ef08fa34-frame-2147228532-1024x607.png" width="1024" /><figcaption class="wp-element-caption"><em>Agentic benchmarks vs. previous Mistral models</em></figcaption></figure>
</div>


<h2 class="wp-block-heading" id="h-building-out-the-pieces">Building out the pieces</h2>



<p>Mistral has been building toward this almost since its inception. In 2024, the company released <a class="ext-link" href="https://huggingface.co/mistralai/Codestral-22B-v0.1" rel="external nofollow">Codestral</a>, its <a class="ext-link" href="https://mistral.ai/news/codestral" rel="external nofollow">first dedicated coding model</a>, focused on everyday developer tasks like code completion and generation. More recently, it <a class="local-link" href="https://thenewstack.io/leanstral-formal-verification-code/">followed up with Leanstral</a>, which tackled a more difficult problem &mdash; using formal verification to check whether code is actually correct.</p>



<p>So rather than jumping straight to fully autonomous agents, Mistral has been building out the pieces: models that can write code, models that can check it, and now a system that tries to run that work in the background.</p>



<p>It&rsquo;s also where the company starts to overlap more directly with bigger rivals. Anthropic, for example, has been pushing similar ideas with Claude Code, including tools that let developers run longer coding tasks and keep them going across sessions, whether in the <a class="local-link" href="https://thenewstack.io/anthropics-claude-code-comes-to-web-and-mobile/">browser, on mobile</a>, or via <a class="ext-link" href="https://code.claude.com/docs/en/remote-control" rel="external nofollow">remote access to a local environment</a>.</p>



<p>What sets Mistral apart is how it&rsquo;s packaging those ideas. Its models are typically released with open weights, and now tools like Vibe can run locally or in the cloud, giving developers more control over their use.</p>



<p>That doesn&rsquo;t guarantee it will win out &#8212; far from it. But it does give Mistral something of a unique angle &mdash; especially in Europe, where Mistral has positioned itself as a homegrown alternative to the dominant US labs.</p>



<p>What is seemingly consistent across the board, however, is a growing desire to turn AI from something you have to keep steering into something that can handle chunks of work on its own.</p>
<p>The post <a href="https://thenewstack.io/mistral-vibe-cloud-agents/">Mistral, Europe’s answer to OpenAI and Anthropic, pushes its coding agents to the cloud</a> appeared first on <a href="https://thenewstack.io">The New Stack</a>.</p>
