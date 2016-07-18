---
layout: post
title:  "First step to Docker : 解决Proxy"
date:   2016-06-15 20:22:25 +0800
categories: Docker
---

1. 准备环境：
    - Git Bash
    - Docker Tool Box
    - Windwos 7

2. 错误症状：
    >$ docker pull registry:2
    Pulling repository docker.io/library/registry
    Network timed out while trying to connect to https://index.docker.io/v1/repositories/library/registry/images. You may want to check your internet connection or if you are behind a proxy.

3. 解决办法：
    - docker-machine ssh virtual_box
    - 找到 /var/lib/boot2docker/profile
    - 修改Export
        &emsp;&emsp;export HTTP_PROXY=http://proxy:port
        &emsp;&emsp;export HTTPS_PROXY=http://proxy:port
    - 重启环境 docker-machine restart virtual_box
