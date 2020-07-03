---
author: Feynman
title: How to Add a Registry Mirror in Docker
date: 2020-05-31T12:00:06+09:00
description: Add a Registry Mirror in Docker
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
image: images/feature3/code-file.png
---


## My Environment

CentOS Linux release 7.6 on QingCloud Platform

## Configure the Docker daemon

Either pass the --registry-mirror option when starting dockerd manually, or edit /etc/docker/daemon.json and add the registry-mirrors key and value, to make the change persistent.

```
{
  "registry-mirrors": ["https://<my-docker-mirror-host>"]
}
```

Save the file and reload Docker for the change to take effect.

## Reload Docker

Flush changes and restart Docker:

```
sudo systemctl daemon-reload
sudo systemctl restart docker
```

## Reference

- [Control Docker with systemd](https://docs.docker.com/config/daemon/systemd/)
- [Registry as a pull through cache](https://docs.docker.com/registry/recipes/mirror/#configure-the-docker-daemon)
