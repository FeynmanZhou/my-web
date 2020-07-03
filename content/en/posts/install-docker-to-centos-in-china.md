---
author: Feynman
title: How to Install Docker on CentOS in China
date: 2020-07-02T12:00:06+09:00
description: How to Install Docker on CentOS 7.6 in China, with China registry mirror
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

## My Installation OS

CentOS Linux release 7.6 on QingCloud Platform

## Add source for docker-ce yum

1. Extend yum function

```
$ yum install -y yum-utils
```

2. Add software source information

```
$ yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo  
```

3. Automatically select the fastest yum registry source

```
yum makecache fast
```

## List the current version of docker-ce that can be installed

1. View the version list:

```
$ yum list docker-ce --showduplicates | sort -r
docker-ce.x86_64            3:19.03.9-3.el7                    docker-ce-stable
docker-ce.x86_64            3:19.03.8-3.el7                    docker-ce-stable
docker-ce.x86_64            3:19.03.7-3.el7                    docker-ce-stable
docker-ce.x86_64            3:19.03.6-3.el7                    docker-ce-stable
docker-ce.x86_64            3:19.03.5-3.el7                    docker-ce-stable
docker-ce.x86_64            3:19.03.4-3.el7                    docker-ce-stable
docker-ce.x86_64            3:19.03.3-3.el7                    docker-ce-stable
docker-ce.x86_64            3:19.03.2-3.el7                    docker-ce-stable
docker-ce.x86_64            3:19.03.12-3.el7                   docker-ce-stable
docker-ce.x86_64            3:19.03.11-3.el7                   docker-ce-stable
docker-ce.x86_64            3:19.03.10-3.el7                   docker-ce-stable
docker-ce.x86_64            3:19.03.1-3.el7                    docker-ce-stable
docker-ce.x86_64            3:19.03.0-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.9-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.8-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.7-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.6-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.5-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.4-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.3-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.2-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.1-3.el7                    docker-ce-stable
docker-ce.x86_64            3:18.09.0-3.el7                    docker-ce-stable
docker-ce.x86_64            18.06.3.ce-3.el7                   docker-ce-stable
docker-ce.x86_64            18.06.3.ce-3.el7                   @docker-ce-stable
docker-ce.x86_64            18.06.2.ce-3.el7                   docker-ce-stable
docker-ce.x86_64            18.06.1.ce-3.el7                   docker-ce-stable
docker-ce.x86_64            18.06.0.ce-3.el7                   docker-ce-stable
docker-ce.x86_64            18.03.1.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            18.03.0.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.12.1.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.12.0.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.09.1.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.09.0.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.06.2.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.06.1.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.06.0.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.03.3.ce-1.el7                   docker-ce-stable
docker-ce.x86_64            17.03.2.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.03.1.ce-1.el7.centos            docker-ce-stable
docker-ce.x86_64            17.03.0.ce-1.el7.centos            docker-ce-stable
Loading mirror speeds from cached hostfile
Loaded plugins: fastestmirror
Installed Packages
Available Packages
 * updates: mirrors.tuna.tsinghua.edu.cn
 * extras: mirrors.tuna.tsinghua.edu.cn
 * epel: mirrors.tuna.tsinghua.edu.cn
 * base: mirrors.tuna.tsinghua.edu.cn
```

2. Install the specified version

```
# yum -y install docker-ce-[VERSION]   
$ yum install -y docker-ce-18.06.3.ce-3.el7
```

## Start Docker

1. Start Docker

```
$ systemctl start docker
```

2. Verify the docker information:

```
$ docker info
Containers: 0
 Running: 0
 Paused: 0
 Stopped: 0
Images: 0
Server Version: 18.06.3-ce
Storage Driver: overlay2
 Backing Filesystem: extfs
 Supports d_type: true
 Native Overlay Diff: true
Logging Driver: json-file
Cgroup Driver: cgroupfs
Plugins:
 Volume: local
 Network: bridge host macvlan null overlay
 Log: awslogs fluentd gcplogs gelf journald json-file logentries splunk syslog
Swarm: inactive
Runtimes: runc
Default Runtime: runc
Init Binary: docker-init
containerd version: 468a545b9edcd5932818eb9de8e72413e616e86e
runc version: a592beb5bc4c4092b1b1bac971afed27687340c5
init version: fec3683
Security Options:
 seccomp
  Profile: default
Kernel Version: 3.10.0-957.21.3.el7.x86_64
Operating System: CentOS Linux 7 (Core)
OSType: linux
Architecture: x86_64
CPUs: 8
Total Memory: 15.51GiB
Name: i-3f8hoeou
ID: 7MHA:FO5V:YCH6:ED46:KWDZ:OY3E:TE6Y:HRNC:F2KU:GSGF:NYDA:KHYA
Docker Root Dir: /var/lib/docker
Debug Mode (client): false
Debug Mode (server): false
Registry: https://index.docker.io/v1/
Labels:
Experimental: false
Insecure Registries:
 127.0.0.0/8
Live Restore Enabled: false
```

3. At last, let's verify the docker version, it demonstrates the Docker CE has been installed successfully.

```
$ docker version
Client:
 Version:           18.06.3-ce
 API version:       1.38
 Go version:        go1.10.3
 Git commit:        d7080c1
 Built:             Wed Feb 20 02:26:51 2019
 OS/Arch:           linux/amd64
 Experimental:      false

Server:
 Engine:
  Version:          18.06.3-ce
  API version:      1.38 (minimum version 1.12)
  Go version:       go1.10.3
  Git commit:       d7080c1
  Built:            Wed Feb 20 02:28:17 2019
  OS/Arch:          linux/amd64
  Experimental:     false
```
