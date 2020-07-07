---
author: Feynman
title: Install and Set Up kubectl Tool
date: 2020-05-31T12:00:06+09:00
description: How to install Kind to provision a Kubernetes cluster, and install KubeSphere on existing K8s
draft: false
hideToc: false
enableToc: true
enableTocContent: true
tocPosition: inner
tags:
- shortcode
series:
-
categories:
-
image: images/feature2/mathbook.png
---

## Intro

The Kubernetes command-line tool, kubectl, allows you to run commands against Kubernetes clusters. You can use kubectl to deploy applications, inspect and manage cluster resources, and view logs.

## My Environment

CentOS Linux release 7.6 on QingCloud Platform

## Install kubectl

- For users who can access google api, refer to the [Kubernetes Documentation](https://kubernetes.io/docs/tasks/tools/install-kubectl/).

- For users who can not access google api, please refer to the following steps:

1. Add source repository for Kubernetes.

```
cat <<EOF > /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://mirrors.aliyun.com/kubernetes/yum/repos/kubernetes-el7-x86_64/
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://mirrors.aliyun.com/kubernetes/yum/doc/yum-key.gpg https://mirrors.aliyun.com/kubernetes/yum/doc/rpm-package-key.gpg
EOF
```

2. Install kubectl using yum.

```
yum install -y kubectl
```

## Reference

- [Blog - Install and Configure Kubernetes]
- [Install and Set Up kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
