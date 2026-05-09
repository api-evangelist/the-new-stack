---
title: "How NetEase Games cut LLM cold starts from 42 minutes to 30 seconds"
url: "https://thenewstack.io/netease-fluid-llm-inference/"
date: "2026-05-06"
author: "Monica White"
feed_url: "https://thenewstack.io/feed/"
---
At NetEase Games, we learned a hard lesson about large language model (LLM) inference in production: elastic compute is only useful if data can move just as fast. “Elastic compute is only useful if data can move just as fast.” On paper, serverless GPU infrastructure looked like a good fit for inference workloads. Game traffic is bursty, peaks differ by title and time of day, and reserving GPU capacity for every possible spike is expensive. But once we started scaling LLM services across regions, a different bottleneck emerged. The real problem was not scheduling containers.
