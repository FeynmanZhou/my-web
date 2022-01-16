---
author: Feynman
title: Karmada 0.7 released! The Next-gen Multi-Cloud and Multi-Cluster Kubernetes Orchestration
date: 2021-09-24T12:00:06+09:00
description: Karmada 0.7, featuring a promising Kubernetes management system in the hybrid cloud era, became available on July 12, 2021. It brought multi-cluster service discovery, precise cluster status management, replica scheduling based on cluster resources, and more convenient APIs to divide replicas by weight list.
draft: false
hideToc: false
enableToc: true
enableTocContent: true
tocPosition: inner
tags:
- news
series:
- InfoQ-news
categories: 
-
image: /posts/images/karmada-architecture.png
---

Karmada 0.7, featuring a promising Kubernetes management system in the hybrid cloud era, became available on July 12, 2021. It brought multi-cluster service discovery, precise cluster status management, replica scheduling based on cluster resources, and more convenient APIs to divide replicas by weight list.

Karmada (Kubernetes Armada) is designed for multi-cloud and multi-cluster Kubernetes orchestration with a Kubernetes-native implementation. It provides centralized multi-cloud management, high availability, failure recovery, and traffic scheduling, which enables users to run their cloud-native applications across multiple Kubernetes clusters and clouds with no changes to applications.

Kubernetes Federation is the only official multi-cluster management solution that the SIG Multicluster initiated and maintained. After two major versions, KubeFed has a resilient design and architecture. Karmada is developed in continuation of Kubernetes Federation v1 and v2 and inherited some basic concepts from these two versions. However, Federation v2 (KubeFed) is still in beta and some of the features are still in alpha. Its lack of maturity and community activity are blocking a lot of users from adopting it in production.

![Karmada Architecture](/posts/images/karmada-architecture.png)

Apart from the new features that have been added in this release, the installation scripts support installing Karmada components on both Kind clusters and standalone clusters; other notable improvements related to the Karmada’s components can be found in the release notes.   

Karmada is fully compatible with the Kubernetes native API as it evolved from KubeFed, so users can deploy their cloud-native applications from single-cluster to multi-cluster with zero changes.

This example below demonstrates how to propagate an nginx application to the multi-cluster environments by leveraging the reusable propagation policy. This propagation policy configures the multi-AZ and HA deployment scheme for all target Kubernetes deployments, then users can deploy the application to the multi-cluster environments by speaking Kubernetes-native APIs.

![Sample code](/posts/images/karmada-sample-code.png)

As a promising newcomer of the multi-cloud and multi-cluster solutions, it has a new release almost every month. Karmada’s active contributors include Huawei, ICBC, Tencent, and other organizations so far.

Going forward, they plan to add support for more fruitful multi-cluster HA scheduling policies, aggregated Kubernetes API endpoints, multi-cluster service mesh, observability, and GitOps.

![Roadmap for 2021](/posts/images/karmada-roadmap.png)

Karmada can be installed within minutes. Get started with Karmada by following the Quick Start and demo. Support is also available via Slack and community meetings.

