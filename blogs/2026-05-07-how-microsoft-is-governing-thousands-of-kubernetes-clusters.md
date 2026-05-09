---
title: "How Microsoft is governing thousands of Kubernetes clusters without manual intervention"
url: "https://thenewstack.io/kubernetes-fleet-management-scale/"
date: "2026-05-07"
author: "Adrian Bridgwater"
feed_url: "https://thenewstack.io/feed/"
---
Kubernetes is complicated; everybody knows it. Logically enough, Kubernetes deployed as a cluster of collected and coalesced instances at “fleet scale” is unquestionably complicated. Synchronizing the configurations of thousands of clusters across massively distributed environments that span on-premises, cloud, and edge is a big ask, so how is it done? Small is beautiful, big is brutal In a more standard (smaller) environment, automated controllers in Git repositories sync the desired state of a cluster held in Git with the actual state in a given Kubernetes cluster.
