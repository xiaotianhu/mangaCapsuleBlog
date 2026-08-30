---
id: "komga-ios-client"
title: "Komga有iOS客户端吗？iPhone/iPad连接Komga漫画服务器方案（2026）"
excerpt: "Komga没有官方iOS客户端，但通过OPDS或直接挂载NAS目录，iPad照样流式读你的Komga书库"
category: "教程"
readTime: "5 min read"
date: "2026年7月9日"
tags: ["Komga", "NAS", "OPDS", "教程"]
image: "https://mangacapsule.com/images/blog/komga-ios-client_0.jpg"
author:
  name: "Rainy"
  avatar: "https://mangacapsule.com/images/rainyavatar.jpg"
  role: "Developer"
---

# Komga iOS 客户端，iPhone/iPad 连接 Komga 漫画服务器方案

首先说明，**Komga 没有官方 iOS 客户端**，只会网页版；在 iPad 上能用但体验一般（没有离线缓存、翻页手势和阅读模式都比较基础）。

实际可行的方案有两个：**通过 OPDS 协议连接**，或者**跳过 Komga、直接挂载底层文件目录**。两个方案「漫画胶囊」都支持，下面分别讲。

## 方案一：OPDS 连接 Komga

Komga 内置了 OPDS 目录服务，任何支持 OPDS 的阅读器都能浏览和拉取书库。

配置步骤（以漫画胶囊为例）：

1. 书架页侧边栏，添加网络书架 → 选择「OPDSv2」
2. 地址填：`http://你的Komga服务器地址:25600`（25600 是 Komga 默认端口，改过的换成自己的）
3. 填 Komga 的用户名密码，连接
4. 书库按 Komga 里的库结构展示，点开即读

这个方案的好处是保留 Komga 的库组织（系列、合集），适合已经在 Komga 里精心整理过元数据的用户。
漫画胶囊支持的是新版Komga，OPDS v2 协议，太老的Komga需要自己更新下哈。

## 方案二：直接挂载文件目录（我更推荐）

Komga 本质上是在你 NAS 的漫画文件夹上加了一层管理服务。如果你的目录本身就整理得不错（按作品分文件夹），其实可以**跳过 Komga 这一层**，用 SMB 或 WebDAV 直接把文件夹挂载进阅读器：

1. 书架页侧边栏「添加网络书架」→「SMB」或「WebDAV」
2. 填 NAS 地址和账号,选中漫画根目录
3. 文件夹结构直接映射成书架，封面自动生成

**为什么更推荐这个**：

链路少一层（不依赖 Komga 服务的状态）、支持流式加载（大文件点开即读，OPDS 拉取整个文件则要等下载）、NAS 上新增文件立刻可见,不用等 Komga 扫库。

## 两个方案怎么选

| 对比项 | OPDS 连 Komga | SMB/WebDAV 直挂 |
|--------|:---:|:---:|
| 保留 Komga 元数据/系列组织 | ✅ | ❌ 按文件夹结构 |
| 大文件打开速度 | 需拉取完整文件 | ✅ 流式秒开 |
| 依赖 Komga 服务在线 | 是 | 否 |
| 外网访问 | 都可以（需做端口转发/内网穿透，建议 HTTPS 或 VPN） | 同左 |

我的建议：家里主要设备是 iPad 的话直挂就够了；Komga 服务继续留着给桌面网页端和安卓端（Tachiyomi/Mihon 系）用，互不冲突。

## 常见问题 FAQ

**Q：Paperback、Panels 这些 App 能连 Komga 吗？**
A：Panels 支持 OPDS 可以连；Paperback 需要装扩展源。国内用户注意这两款对中文界面和条漫模式的支持有限。

**Q：出门在外怎么访问家里的 Komga/NAS？**
A：常见做法是 Tailscale/WireGuard 组网（推荐，安全），或者路由器端口转发+HTTPS。组网后 App 里填内网地址照常用。

**Q：Komga 的替代品 Kavita 也适用这套方案吗？**
A：适用。Kavita 同样提供 OPDS 接口，直挂文件目录的方案更是和服务端软件无关。

---

> 📥 [App Store 下载漫画胶囊](https://apps.apple.com/cn/app/%E6%BC%AB%E7%94%BB%E8%83%B6%E5%9B%8A-nas-%E6%9C%AC%E5%9C%B0%E6%BC%AB%E7%94%BB%E9%98%85%E8%AF%BB%E5%99%A8/id6737119574?ppid=a6c5ba86-6cba-430d-907c-bbdb1455847b)
>
> 🔗 相关阅读：
> - [NAS 里几百 G 漫画怎么用 iPad 直接看](/zh/blog/nas-stream-large-manga-ipad)
> - [iPad 搭配 NAS 看漫画：全品牌配置指南](/zh/blog/ipad-nas-manga-tutorial)
