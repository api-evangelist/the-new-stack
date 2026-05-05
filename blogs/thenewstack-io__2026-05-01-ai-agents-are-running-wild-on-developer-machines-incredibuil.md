---
title: "AI agents are running wild on developer machines. Incredibuild has a fix."
url: "https://thenewstack.io/incredibuild-ai-agents-sandbox-coding/"
date: "Fri, 01 May 2026 20:21:31 +0000"
author: "Darryl K. Taft"
feed_url: "https://thenewstack.io/feed/"
---
<img alt="" class="webfeedsFeaturedVisual wp-post-image wp-stateless-item" height="683" src="https://cdn.thenewstack.io/media/2026/05/a2be03c6-willian-reis-o6avr7ma15q-unsplash-1024x683.jpg" style="display: block; margin: auto; margin-bottom: 20px;" width="1024" />
<p>Somewhere out there, a developer is walking around with their laptop half-open, so their AI coding agent doesn&#8217;t die.</p>



<p>That&#8217;s the state of enterprise AI development in 2026 &mdash; and the problem <a class="ext-link" href="https://www.incredibuild.com/" rel="external nofollow">Incredibuild</a> is trying to fix with Islo, a sandbox that gives every agent its own persistent, isolated cloud environment.</p>



<p>The company, best known for its <a class="ext-link" href="https://www.incredibuild.com/glossary/build-acceleration" rel="external nofollow">build acceleration platform</a> used by Microsoft, Take-Two, and Nintendo, has announced Islo, a sandbox purpose-built for <a class="local-link" href="https://thenewstack.io/ai-coding-agents-level-up-from-helpers-to-team-players/">AI coding agents</a>.</p>



<p>The goal is to give every agent its own dedicated, isolated cloud environment, governed by explicit policies, so engineering teams can run agents continuously without the security and governance headaches that come with letting them loose on developer machines or unmanaged infrastructure.</p>



<h2 class="wp-block-heading" id="h-agents-don-t-fit-the-one-developer-one-machine-model">Agents don&#8217;t fit the one developer, one machine model</h2>



<p>&#8220;Coding agents are capable of doing real work now, but they all run on the developer&#8217;s laptop,&#8221; <a class="ext-link" href="https://www.linkedin.com/in/adamgold7/" rel="external nofollow">Adam Gold</a>, Director of Product Engineering at Incredibuild, says in a press release. &#8220;That means they die when the lid closes, and they have access to everything on the machine. </p>



<p>&#8220;We built Islo because we believe that every AI agent needs its own computer &mdash; not an ephemeral container, but a long-running dev environment with its own running services, scoped credentials, and a lifecycle that doesn&#8217;t depend on human supervision.&#8221;</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>&#8220;We built Islo because we believe that every AI agent needs its own computer&#8221;</p>
</blockquote>



<p>The &#8220;every agent needs its own computer&#8221; statement is more than a tagline. The current industry model is one developer, one machine &mdash; which works because a developer is a single, supervised actor who sits down, does the work, and comes back the next day.</p>



<p>However, agents break that model in three specific ways, according to the company. Their lifecycles don&#8217;t match human ones &mdash; people are reportedly walking around with laptops half-open so agents keep running, which the company flatly describes as &#8220;not a workflow.&#8221; They carry a large blast radius, inheriting all the credentials a developer has accumulated &mdash; SSH keys, AWS profiles, browser cookies &mdash; with none of the judgment about when not to use them. And they need warm, persistent environments with running services, databases, and build caches that ephemeral containers throw away on every run.</p>



<h2 class="wp-block-heading" id="h-not-codespaces-not-a-container">Not Codespaces, not a container</h2>



<p>What Incredibuild is building toward is a persistent, addressable machine per agent &mdash; with its own scoped credentials and a lifecycle that doesn&#8217;t end when a human goes to dinner.</p>



<p>That distinction also separates Islo from the closest existing alternatives, the company says. Cloud dev environments like <a class="local-link" href="https://thenewstack.io/codeanywhere-founders-take-on-github-codespaces-with-daytona/">GitHub Codespaces</a>, <a class="local-link" href="https://thenewstack.io/codeanywhere-founders-take-on-github-codespaces-with-daytona/">Daytona</a>, and <a class="local-link" href="https://thenewstack.io/self-hosted-cdes-preferred-to-saas-in-large-orgs-says-coder/">Coder</a> were built for humans &mdash; they assume an IDE is attached, idle out, and operate on the security premise that the developer is trusted. </p>



<p>Ephemeral sandboxes are optimized for sub-second cold starts and designed to be torn down, the company says. Islo is built around the opposite assumption: the agent is the principal user, sessions are persistent with no session ceiling, and there&#8217;s a policy layer between the agent and everything outside the sandbox.</p>



<h2 class="wp-block-heading" id="h-choke-points-not-policy-languages">Choke points, not policy languages</h2>



<p>That policy layer is worth understanding in some detail, because &#8220;granular policy control&#8221; could mean almost anything, Incredibuild says. In Islo&#8217;s case, it doesn&#8217;t mean a policy language like <a class="ext-link" href="https://www.openpolicyagent.org/" rel="external nofollow">Open Policy Agent</a> or <a class="local-link" href="https://thenewstack.io/all-about-cedar-an-open-source-solution-for-fine-tuning-kubernetes-authorization/">Cedar</a> &mdash; it means enforcement at specific, well-defined choke points.</p>



<p>The network gateway sits outside the <a class="local-link" href="https://thenewstack.io/the-future-of-vms-on-kubernetes-building-on-kubevirt/">VM</a> and handles every outbound call the agent makes. Enterprises configure an allowlist of hosts, ports, and methods, and the agent has no way around it because the gateway is outside its control. The filesystem boundary enforces read and write rules per path &mdash; an agent might be permitted to write to /workspace, but blocked from reading <code>~/.ssh</code> or <code>~/.aws</code>. An audit log records every shell command, file change, network call, and credential use.</p>



<p>The choke points are independent, so teams can run a wide-open network policy alongside a tight filesystem policy depending on what a given agent is doing.</p>



<h2 class="wp-block-heading" id="h-credential-blind-by-design">Credential-blind by design</h2>



<p>Credential handling follows a similar logic of keeping enforcement outside the agent&#8217;s reach. Credentials never live in the sandbox &mdash; not in the VM image, not in environment variables, not in the agent&#8217;s filesystem.</p>



<p>The sandbox is what Incredibuild calls &#8220;credential-blind.&#8221; Instead, a host-side proxy sits outside the VM and injects credentials at the network boundary based on the agent&#8217;s identity and per-sandbox policy. The agent makes API calls without credentials; the Islo gateway attaches them per request.</p>



<p>&#8220;We&#8217;ve spent years helping teams ship quickly,&#8221; <a class="ext-link" href="https://www.linkedin.com/in/shimon-hason/" rel="external nofollow">Shimon Hason</a>, CEO of Incredibuild, says in a press release. &#8220;Islo is making sure AI can ship safely. We&#8217;re introducing a missing layer in the stack: a super-powered sandbox that provides the infrastructure necessary for organizations to safely run AI agents as part of real production workflows.&#8221;</p>



<h2 class="wp-block-heading" id="h-pricing-and-availability">Pricing and availability</h2>



<p>While Islo can run independently, Incredibuild is positioning it alongside its existing acceleration technology to speed up compute-heavy steps in build, test, and <a class="local-link" href="https://thenewstack.io/ci-cd/">CI/CD</a> workflows. The company is also targeting AI research workflows through a partnership with the <a class="ext-link" href="https://www.harborframework.com/" rel="external nofollow">Harbor Framework</a> community &mdash; an open-source infrastructure project for authoring and executing agent benchmarks and evaluations.</p>



<p>Islo launches with three tiers: a free plan supporting up to five concurrent sandboxes; a Team plan at $0.07 per CPU-hour and $0.04 per GB-hour supporting up to 50 concurrent sandboxes; and an Enterprise tier with custom packages. The company says it is working with a small group of design partners through a private beta.</p>



<p>Islo is available now at islo.dev. Incredibuild serves more than 600 customers across its platform. Whether the market is ready for that missing layer in the stack is a question the private beta will start to answer.</p>



<p></p>
<p>The post <a href="https://thenewstack.io/incredibuild-ai-agents-sandbox-coding/">AI agents are running wild on developer machines. Incredibuild has a fix.</a> appeared first on <a href="https://thenewstack.io">The New Stack</a>.</p>
