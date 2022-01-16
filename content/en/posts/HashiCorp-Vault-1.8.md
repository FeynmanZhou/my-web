---
author: Feynman
title: HashiCorp Vault 1.8 Adds Diagnose Command, Key Management Secrets Engine, and Expiration Manager
date: 2021-11-12T12:00:06+09:00
description: HashiCorp Vault 1.8 brings notable features and improvements to the secrecy and privacy product including Vault Diagnose, integrated-storage autopilot, Key Management secrets engine for AWS, expiration manager improvements, and control-group triggers.
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
image: /posts/images/hashicorp-vault.png
---

HashiCorp Vault 1.8 brings notable features and improvements to the secrecy and privacy product including Vault Diagnose, integrated-storage autopilot, Key Management secrets engine for AWS, expiration manager improvements, and control-group triggers.

Vault helps users to manage secrets and protect sensitive data using UI, CLI, or HTTP API.

In the community office hours of Vault, Stephen Wayne, software engineer of HashiCorp, highlighted the major improvements of the expiration manager and why it does matter for Vault. Expiration manager is used to manage the lifecycle of leases. All dynamic secrets in Vault are required to have a lease.

Vault 1.7 and earlier versions have some obvious limitations especially in revocation, such as leases must be revoked from the system they are associated with, one worker per revocation, irrevocable lease revocation retried on Vault start, and many concurrent revocations consume resources needed by other Vault components. Revocation is critical since it assists in key rolling as well as locking down systems in the case of an intrusion.

![xxx](/posts/images/hashicorp-vault.png)

With Vault 1.8, it has the ability to mark some leases as irrevocable, offers fair-sharing logic to help with lease revocations, and adds an HTTP API and a CLI for operators to obtain information about irrevocable leases. Fortunately, Vault 1.8 reaches the expected outcomes from the end-user perspective, such as more efficient use of resources, more observability into the state of leases, and no more freezes on startup. Now Vault has improved support for lease revocation.

Vault Diagnose has been introduced in Vault 1.8 to enable faster troubleshooting and user-friendly diagnostics when Vault fails to boot or crashes. It means the diagnose command can be used safely regardless of the state Vault is in. Hridoy Roy, software engineer of HashiCorp, walks through the Vault Diagnose command and explains why and how Vault Diagnose is in the community office hours.

Since the customers are facing the challenges of vault configurations such as misconfigured TLS and certification issues, HashiCorp  designed Vault Diagnose to catch some of the common causes for vault misbehavior before they arise. Vault Diagnose uses OpenTelemetry spans to store diagnostic information. It walks the tree and warns, fails, or passes each check with extensive human-readable messages. Hridoy also showed a live demo to introduce the basic use of the diagnose operator command with misconfigured storage or even when Vault is down.

The changelog and release notes list all the changes in Vault 1.8. You can also check out the official announcement to find the enterprise features.