---
title: "IBM Bob hits 80,000 developers with 45% productivity gains"
url: "https://thenewstack.io/ibm-bob-agentic-development/"
date: "Fri, 01 May 2026 19:06:02 +0000"
author: "Darryl K. Taft"
feed_url: "https://thenewstack.io/feed/"
---
<img alt="" class="webfeedsFeaturedVisual wp-post-image wp-stateless-item" height="683" src="https://cdn.thenewstack.io/media/2026/05/9560241d-sayyam-abbasi-5dcnacdz_fs-unsplash-1024x683.jpg" style="display: block; margin: auto; margin-bottom: 20px;" width="1024" />
<p><a class="local-link" href="https://thenewstack.io/ibm-tackles-shadow-ai-an-enterprise-blind-spot/">IBM</a> is betting that the next competitive frontier in <a class="local-link" href="https://thenewstack.io/three-ai-assisted-development-skills-you-can-start-using-today/">AI-assisted development</a> isn&#8217;t raw <span style="margin: 0px; padding: 0px;"><a class="local-link" href="https://thenewstack.io/ai-code-generation-trust-and-verify-always/" target="_blank">code-generation</a>&nbsp;speed &mdash; it&#8217;s governance, auditability, and the operational discipline to deploy AI within</span> enterprises that can&#8217;t afford to get it wrong.</p>



<p>That&#8217;s the pitch behind <a class="ext-link" href="https://bob.ibm.com/" rel="external nofollow">IBM Bob,</a> the company&#8217;s new <a class="local-link" href="https://thenewstack.io/agentic-ai-is-quickly-revolutionizing-ides-and-developer-productivity/">agentic development</a> platform released this week. Bob has been running internally at IBM since June 2025, scaling from 100 developers to more than 80,000 users across IBM&#8217;s global workforce.</p>



<p>Surveyed users report an average 45% increase in productivity. On specific teams, the numbers go higher. For instance, the <a class="ext-link" href="https://www.ibm.com/products/instana" rel="external nofollow">IBM Instana</a> team reported an average 70% reduction in time on selected tasks, while the <a class="ext-link" href="https://www.ibm.com/products/maximo" rel="external nofollow">Maximo</a> developer team estimated 69% time savings on code generation and refactoring work that normally takes days.</p>



<p>IBM notes that these are self-reported figures. That caveat matters. But the internal deployment itself is the more interesting data point.</p>



<p><a class="ext-link" href="https://www.linkedin.com/in/neel-sundaresan-a964a2/" rel="external nofollow">Neel Sundaresan</a>, GM of Automation and AI at IBM Software, was part of the team that built the original <a class="local-link" href="https://thenewstack.io/github-copilot-interaction-data/">Microsoft GitHub Copilot</a> before joining IBM. Sundaresan tells <em>The New Stack</em>, &#8220;We have all these enterprise workloads we are familiar with. Before we even go knock on the doors of a client, we have a story to tell.&#8221;</p>



<p>That story runs from <a class="local-link" href="https://thenewstack.io/java-at-30-the-genius-behind-the-code-that-changed-tech/">Java</a> app modernization to <a class="local-link" href="https://thenewstack.io/cobol-everywhere-will-maintain/">COBOL</a> maintenance to <a class="local-link" href="https://thenewstack.io/ship-fast-break-nothing-launchdarklys-winning-formula/">FedRAMP</a> compliance work &mdash; the kind of legacy-heavy, risk-sensitive development that most AI coding tools aren&#8217;t really built for, Sundaresan says. It&#8217;s a deliberate positioning move. IBM isn&#8217;t chasing Cursor or GitHub Copilot on its own terms.</p>



<h2 class="wp-block-heading" id="h-not-just-another-code-completion-tool">Not just another code completion tool</h2>



<p>Bob is structured around the full software development lifecycle &mdash; planning, coding, testing, deployment, and modernization &mdash; coordinating what IBM calls role-based specialized agents across each stage. The product ships with <a class="ext-link" href="https://bob.ibm.com/docs/shell" rel="external nofollow">Bob Shell</a>, a <a class="local-link" href="https://thenewstack.io/user-interfaces-in-agentic-cli-tools-what-developers-need/">CLI</a> that creates self-documenting audit trails in real time, so every agent action is traceable. Security controls &mdash; prompt normalization, sensitive data scanning, real-time policy enforcement, and AI red-teaming &mdash; are baked into the workflow rather than bolted on afterward.</p>



<p>IBM says that the last point is a direct response to a known problem: the company cites industry figures suggesting 45% of AI-generated code reaches production without sufficient review.</p>



<p>The multi-model orchestration layer is where Bob&#8217;s technical architecture gets interesting. Rather than asking developers to select a model, Bob routes tasks automatically &mdash; drawing on <a class="local-link" href="https://thenewstack.io/anthropic-doubles-claude-usage-outside-peak-hours/">Anthropic Claude</a>, <a class="local-link" href="https://thenewstack.io/mistral-vibe-cloud-agents/">Mistral</a> <span style="margin: 0px; padding: 0px;">open-source models,&nbsp;<a class="ext-link" href="https://www.ibm.com/granite" rel="external nofollow" target="_blank">IBM Granite</a>, and a set of proprietary,</span> fine-tuned models built specifically for the Bob environment. Lighter completions go to smaller, cheaper models. Complex reasoning tasks go to larger frontier models. Granite, which Sundaresan described as a small model suited primarily to code completion, plays a narrow role. &#8220;I would say 90-plus percent of it is all like bigger tasks,&#8221; he said.</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>&#8220;We&#8217;re not going to be cost-constrained, but we are going to be cost-informed&#8221;</p>
</blockquote>



<p>The cost-awareness framing is intentional. &#8220;We&#8217;re not going to be cost-constrained, but we are going to be cost-informed,&#8221; Sundaresan says. He compared letting developers self-select the latest frontier model for simple prompts to &#8220;taking your Ferrari to go buy milk&#8221; &mdash; technically functional, but expensive and unnecessary. IBM doesn&#8217;t expose the underlying model to users. The routing is managed automatically.</p>



<p>That&#8217;s a meaningful philosophical difference from tools that surface model selection as a feature, IBM says.</p>



<h2 class="wp-block-heading" id="h-bob-2-0">Bob 2.0?</h2>



<p>&ldquo;If you look at the popular coding assistants today, many are forks of VS Code, or forks of something that&#8217;s like VS Code, and that gives us the minimal functionality that&#8217;s required of an IDE. And then all of the AI goes on top, and you can build amazing experiences,&rdquo; Sundaresan says. Then, in 2025, &ldquo;people started saying, &#8216;Why do I even need an IDE? Why do I even need an IDE? Why can&#8217;t I do it in a shell?&#8217; So that&#8217;s why Claude Code came along. And that&rsquo;s why we have Bob Shell&hellip;,&rdquo; he notes.</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>&#8220;You don&#8217;t need an interface. The best interface is no interface&hellip; as we go forward to Bob, 2.0 Bob is going to be an agent.&#8221;</p>
</blockquote>



<p>Sundaresan argues, &ldquo;You don&#8217;t need an interface. The best interface is no interface, right? So, as we go forward to Bob, 2.0 Bob is going to be an agent. You can embed Bob pretty much anywhere you want to, and it&#8217;s an AI engine that makes your experience different.&rdquo;</p>



<p>He explains that Bob could be on your phone or in your application. It could be targeted at consultants, he says.</p>



<p>&ldquo;We have thousands of consultants,&rdquo; Sundaresan says. &ldquo;You could have a bunch of Bob consultants buried in there along with them, because a lot of the consulting workloads are very different from engineering work.&rdquo;</p>



<h2 class="wp-block-heading" id="h-proven-at-scale-with-caveats">Proven at scale &mdash; with caveats</h2>



<p>Meanwhile, the early customer results are a showcase of the type of work IBM typically does for customers. <a class="ext-link" href="https://www.ey.com/en_us" rel="external nofollow">Ernst &amp; Young</a> is using Bob to accelerate refactoring, test generation, and documentation on its global tax platform. <a class="ext-link" href="https://www.bluepearl.co.za/#about" rel="external nofollow">Blue Pearl</a>, a cloud solutions firm, said Bob compressed a typical 30-day Java upgrade into three days, saving more than 160 engineering hours with zero post-deployment defects. <a class="ext-link" href="https://www.apis-it.hr/web/naslovnica" rel="external nofollow">APIS IT</a>, working on government modernization with <a class="local-link" href="https://thenewstack.io/broadcom-investing-in-mainframe-success-beyond-code/">mainframe</a> and <a class="local-link" href="https://thenewstack.io/net-modernization-github-copilot-upgrade-eases-migrations/">.NET</a> systems, reported 10x faster architecture analysis and 100% accuracy documenting legacy JCL/PL/I code.</p>



<p>&ldquo;Developing enterprise platforms isn&rsquo;t just about speed. It&rsquo;s about understanding deeply embedded logic, maintaining architectural standards, and evolving systems responsibly,&rdquo; says <a class="ext-link" href="https://www.ey.com/en_us/people/christopher-d-aiken" rel="external nofollow">Christopher Aiken</a>, Tax Platforms Leader and Chief Product Officer, Ernst &amp; Young, LLP, in a statement. &ldquo;EY teams leveraged IBM Bob to apply AI to better interpret complex logic and streamline how changes are introduced, helping create a stronger foundation for scalable transformation.&rdquo;</p>



<p>The consistent thread across these cases is that all three involve the kind of deeply legacy-entangled enterprise environments that other tools tend to sidestep and that IBM specializes in.</p>



<h2 class="wp-block-heading" id="h-where-bob-fits">Where Bob fits</h2>



<p>The agentic coding market now has serious entries from AWS (Kiro), JetBrains (Central), GitHub (Copilot Workspace), and a bunch of other players. Sundaresan acknowledged the crowded field directly.</p>



<p>&#8220;I don&#8217;t think I&#8217;m there to take down one of those things,&#8221; he says. &#8220;There are leaderboards and stuff like that, but if you look under the cover, all of us have similar models. If you don&#8217;t have the right models, you don&#8217;t even have a play. So really, what value you add on top of these models, how you orchestrate these models, how you maintain costs &mdash; that&#8217;s the question.&#8221;</p>



<p>IBM&#8217;s answer is enterprise specificity: decades of Java, <a class="ext-link" href="https://www.ibm.com/history/eserver-zseries" rel="external nofollow">zSystems</a>, COBOL, and security compliance experience embedded into the tool&#8217;s workflows, not just its marketing. Whether that&#8217;s a genuine moat or a repositioning of capabilities the competition is also building toward is a question worth revisiting as the market matures.</p>



<p>Bob is available now as a SaaS offering with a 30-day free trial. On-premises deployment &mdash; which would address data residency requirements for regulated industries &mdash; is described as a future target with no firm timeline.</p>
<p>The post <a href="https://thenewstack.io/ibm-bob-agentic-development/">IBM Bob hits 80,000 developers with 45% productivity gains</a> appeared first on <a href="https://thenewstack.io">The New Stack</a>.</p>
