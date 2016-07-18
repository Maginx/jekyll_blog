---
layout: post
title:  "First step to Docker : 解决Proxy"
date:   2016-06-15 20:22:25 +0800
categories: Docker
---
1. 准备环境：
    1. Git Bash
    2. Docker Tool Box
    3. Windwos 7
2. 错误症状：
    {% highlight shell %}
    $ docker pull registry:2
    Pulling repository docker.io/library/registry
    Network timed out while trying to connect to https://index.docker.io/v1/repositories/library/registry/images. You may want to check your internet connection or if you are behind a proxy.
    {% endhighlight %}
3. 解决办法：
    1. docker-machine ssh <virtual box name>
    2. 找到 /var/lib/boot2docker/profile
    3. 修改Export
    export HTTP_PROXY=http://<proxy>:<port>
    export HTTPS_PROXY=http://<proxy>:<port>
    4. 重启环境 docker-machine restart <virtual box>
