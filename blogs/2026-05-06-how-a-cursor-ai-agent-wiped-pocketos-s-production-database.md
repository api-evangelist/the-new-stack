---
title: "How a Cursor AI agent wiped PocketOS’s production database in under 10 seconds"
url: "https://thenewstack.io/ai-agents-credential-crisis/"
date: "2026-05-06"
author: "Janakiram MSV"
feed_url: "https://thenewstack.io/feed/"
---
Who gave agents root access? On April 25, 2026, a Cursor AI coding agent deleted the entire production database of PocketOS, a SaaS platform serving car rental businesses, in fewer than ten seconds. It deleted everything, including the volume-level backups stored in the same blast radius. The agent acted autonomously on a credential it had no business accessing. This AI agent had been assigned a routine staging task. It encountered a credential mismatch, did not stop to ask a human what to do, and autonomously scanned the codebase for a way forward.
