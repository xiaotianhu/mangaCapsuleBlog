---
id: komga-ios-client
title: Komga iOS Client? iPhone/iPad Connection to Komga Manga Server Solution (2026)
excerpt: >-
  Komga has no official iOS client, but through OPDS or directly mounting a NAS
  directory, iPad can still stream read your Komga library
category: Tutorial
readTime: 5 min read
date: 2026年7月9日
tags:
  - Komga
  - NAS
  - OPDS
  - 教程
image: 'https://mangacapsule.com/images/blog/komga-ios-client_0.jpg'
author:
  name: Rainy
  avatar: 'https://mangacapsule.com/images/rainyavatar.jpg'
  role: Developer
---

# Komga iOS Client, iPhone/iPad Connection to Komga Manga Server Solution

First, **Komga has no official iOS client**, only the web version; it can be used on iPad but the experience is average (no offline cache, page turning gestures and reading mode are quite basic).

There are two practical solutions: **connect through OPDS protocol**, or **skip Komga and directly mount the underlying file directory**. Both solutions are supported by Manga Capsule, explained below.

## Solution 1: Connect to Komga via OPDS

Komga has a built-in OPDS catalog service, and any OPDS-supported reader can browse and fetch the library.

Configuration steps (using Manga Capsule as example):

1. On the bookshelf page sidebar, add network bookshelf → select "OPDSv2"
2. Enter address: `http://your-Komga-server-address:25600` (25600 is Komga's default port, change to your own if modified)
3. Enter Komga username and password, connect
4. Library displays according to Komga's folder structure, tap to read

The benefit of this solution is preserving Komga's library organization (series, collections), suitable for users who have carefully organized metadata in Komga.
Manga Capsule supports the new Komga with OPDS v2 protocol. If your Komga is too old, you'll need to update it.

## Solution 2: Directly Mount File Directory (Recommended)

Komga essentially adds a management layer over your NAS manga folders. If your directory is already well-organized (folders by work), you can **skip the Komga layer** and directly mount the folder into the reader via SMB or WebDAV:

1. On bookshelf page sidebar "Add Network Bookshelf" → "SMB" or "WebDAV"
2. Enter NAS address and account, select manga root directory
3. Folder structure directly maps to bookshelf, covers auto-generated

**Why this is more recommended:**

One less layer (doesn't depend on Komga service status), supports streaming loading (large files open instantly, OPDS requires downloading the entire file), new files on NAS are immediately visible without waiting for Komga to scan.

## How to Choose Between the Two Solutions

| Comparison | OPDS Connect to Komga | SMB/WebDAV Direct Mount |
|--------|:---:|:---:|
| Preserve Komga metadata/series organization | ✅ | ❌ Folder structure |
| Large file open speed | Requires fetching full file | ✅ Streaming instant open |
| Depends on Komga service online | Yes | No |
| External access | Both work (need port forwarding/inner network penetration, recommend HTTPS or VPN) | Same as left |

My suggestion: If the main home device is iPad, direct mount is enough; keep Komga service for desktop web and Android (Tachiyomi/Mihon family) use, they don't conflict.

## FAQ

**Q: Can apps like Paperback and Panels connect to Komga?**
A: Panels supports OPDS and can connect; Paperback requires installing extension sources. Chinese users should note that both have limited support for Chinese interface and vertical scroll mode.

**Q: How to access home Komga/NAS while outside?**
A: Common methods are Tailscale/WireGuard networking (recommended, secure), or router port forwarding + HTTPS. After networking, just enter the internal address in the app as usual.

**Q: Does Kavita, an alternative to Komga, also work with this solution?**
A: Yes. Kavita also provides OPDS interface, and the direct mount file directory solution is even independent of server software.

---

> 📥 [Download Manga Capsule from App Store](https://apps.apple.com/cn/app/%E6%BC%AB%E7%94%BB%E8%83%B6%E5%9B%8A-nas-%E6%9C%AC%E5%9C%B0%E6%BC%AB%E7%94%BB%E9%98%85%E8%AF%BB%E5%99%A8/id6737119574?ppid=a6c5ba86-6cba-430d-907c-bbdb1455847b)
>
> 🔗 Related Reading:
> - [How to Read Hundreds of GB of Manga on iPad Directly with NAS](/zh/blog/nas-stream-large-manga-ipad)
> - [iPad with NAS for Manga: Full Brand Configuration Guide](/zh/blog/ipad-nas-manga-tutorial)
