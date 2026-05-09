---
title: "Kubernetes finally lands user namespace support, but shared kernel problem remains"
url: "https://thenewstack.io/kubernetes-user-namespace-security/"
date: "2026-05-06"
author: "Monica White"
feed_url: "https://thenewstack.io/feed/"
---
Kubernetes shipped a long-awaited security feature last week: user namespace support for pods. It may sound like an obscure feature in a 1.36 release, but it represents progress against a specific class of privilege-escalation attacks in cloud-native environments. User namespaces can reduce the impact of certain container escapes by preventing a root process inside a pod from being treated as a root on the host. User namespaces reinforce a pattern that has existed since Docker’s early design decisions: running containers as root by default.
