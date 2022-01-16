---
author: Feynman
title: Litmus 2.0 Release Includes Multi-Tenancy, Chaos Workflows, GitOps, and Observability
date: 2021-09-24T12:00:06+09:00
description: Litmus 2.0 was released for general availability, with the goal of simplifying chaos engineering by adding new features like chaos center, chaos workflows, GitOps for chaos, multi-tenancy, observability, and private chaos hubs.
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
image: /posts/images/litmus-2.png
---

Litmus, the first chaos engineering project to join the CNCF sandbox program, applies a programmable, declarative approach to chaos engineering. Last month, Litmus 2.0 was released for general availability, with the goal of simplifying chaos engineering by adding new features like chaos center, chaos workflows, GitOps for chaos, multi-tenancy, observability, and private chaos hubs.

InfoQ interviewed Umasankar Mukkara, CEO of ChaosNative and co-creator and maintainer of Litmus engineering platform.

InfoQ: Litmus was the first chaos engineering project to join the CNCF. Can you tell us about the technical evolution of Litmus after it became a CNCF sandbox project?

Umasankar Mukkara: Four years ago, the original idea of Litmus was conceived out of the need for doing chaos engineering in a cloud-native way. The first thing was to build a "chaos operator" so that the idea of chaos can be managed in a Kubernetes-native way using CRDs. We build chaos experiments as ChaosExperiment custom resources and the operator can run or execute them and store the result in another custom resource called ChaosResult. With this in place, we built a community around chaos experiments and created a public hub called "Litmus Chaos Hub" for community users. This is the stage at which we donated Litmus to CNCF as a sandbox project. I would call it Litmus 1.0.

Chaos engineering is the process SRE teams and developers willfully engineer faults and observe where there are any issues in the system. So, we introduced the concept of Chaos Center into the Litmus project and made it the central point to coordinate the chaos efforts or reliability efforts in a team or an organization. Chaos Center is also the place where SREs or developers can build complex experiments as a Litmus workflow. A Litmus workflow can be thought of as a complete chaos scenario that gives a definite outcome, whether the system is resilient for a given scenario or not.

One of the strong lessons from the community was the requirement to define or build a steady state hypothesis around a chaos experiment. We developed Litmus probes to granularly define and tune the steady state hypothesis in a declarative way. Once you have the ability to construct the chaos scenarios and build the chaos culture in your org, you will reach a stage where you want complete automation around chaos engineering. This is where we introduced Chaos GitOps. With Chaos GitOps, you will be able to trigger a Litmus Workflow after a change is applied to a Kubernetes Deployment or microservice.

Observability is the key to successful operations. When you introduce chaos engineering, you want to be able to bring the context of it into your existing observability systems. We built Prometheus chaos metrics in such a way you can easily superimpose the context of a chaos experiment onto your Grafana or other similar dashboards.

All in all, to summarize the technical evolution of Litmus after it became a CNCF sandbox project, we built Chaos Center, Workflows, GitOps, Litmus probes, and the beginnings of chaos observability.

InfoQ: Litmus 2.0 introduces chaos workflows to enable users to run multiple experiments together; how can this simplify the chaos engineering practice for users compared to the previous version of the toolkit?

Mukkara: Chaos experiments are like Lego blocks, Litmus workflows are like Lego toys, they are complete and make sense to an end user. Litmus workflows enable users to reuse a lot of work done by their team members and enhance them to build new chaos scenarios.

Chaos center allows rerunning of chaos workflows, cloning of workflows, starting off from a chaos template, and importing a readily shipped workflow. This makes the idea of real chaos engineering easy for users, as you are not starting with a blank slate.

InfoQ: Litmus 2.0 expands beyond Kubernetes by injecting chaos on infrastructure (cloud) resources such as VMs, bare-metal servers, and disks (AWS, GCP, Azure, VMWare). Will this bring more complexity to the development and maintenance of the project when facing hybrid infrastructure?

Mukkara: The architecture of the Litmus project allows the chaos experiments to be completely independent and plug-and-play. The Litmus platform is written as a Kubernetes application and chaos experiments are wrapped in Kubernetes custom resources. But the experiments themselves need not be limited to targeting Kubernetes resources. This enables Litmus to be used in a real environment where you see cloud-native and cloud-based services coexisting together.

A chaos scenario or a Litmus workflow can now be defined with chaos experiments targeting a complete hybrid scenario. This makes Litmus more useful and enables practical chaos engineering. We expect more chaos experiments to be contributed in the near future by the community.

![litmus 2.0](/posts/images/litmus-2.png)

More details of the Litmus 2.0 release can be found in the release notes.

