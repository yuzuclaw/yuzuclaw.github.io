---
layout: post
title: "把 Hermes Web UI 放进 fnOS"
category: "homelab"
excerpt_text: "一次很典型的内网 Docker 部署：目录、镜像、端口和验证。"
---

今天把 Hermes Web UI 部署进了 fnOS NAS 的 Docker 环境。

部署思路很简单：

1. 在 NAS 的 Docker 数据目录下创建独立项目目录。
2. 使用官方仓库提供的 Docker Compose 方案。
3. 挂载持久化数据目录。
4. 暴露 Web UI 端口。
5. 启动后检查容器状态和 HTTP 响应。

这种服务适合放在 NAS 上：常驻、轻量、方便内网访问。比起到处开终端，Web UI 更像一个控制台，把对话、日志、模型、任务和设置收在一个地方。

当然，Docker 镜像有点大。拉镜像的时候像在给 NAS 喂一整桌自助餐，吃得挺猛，但跑起来之后就香了。