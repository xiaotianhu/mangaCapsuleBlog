---
id: "3"
title: "NAS 用户指南：如何配置 WebDAV 以获得最佳体验"
excerpt: "群晖、威联通、极空间... 手把手教你如何将家里的 NAS 变成随身携带的云端漫画库。"
category: "教程"
readTime: "12 min read"
date: "2024年3月15日"
tags: ["Tutorial", "NAS"]
image: "https://picsum.photos/seed/nas_setup/800/600"
author:
  name: "Rainy"
  avatar: "https://mangacapsule.com/images/rainyavatar.jpg"
  role: "Developer"
---

WebDAV 是目前兼容性最好、性能最均衡的文件传输协议之一。配合 Manga Capsule，你可以实现在公司摸鱼看家里 NAS 上的漫画（误）。

## 准备工作

首先，你需要确保你的 NAS 已经开启了 WebDAV 服务，并且在路由器上配置了端口转发（如果是外网访问）。

```
// 典型的 WebDAV URL 结构
http://[你的域名或IP]:[端口]/[共享文件夹路径]
```

在 Manga Capsule 的"连接"页面，选择 WebDAV，填入上述信息。如果连接成功，你应该能立即看到文件列表。
