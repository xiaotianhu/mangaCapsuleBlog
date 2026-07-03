---
id: ipad-nas-manga-tutorial
title: >-
  iPad + NAS Manga Reading Tutorial: Synology/ZSpace/FN OS/UGREEN Complete Brand
  Configuration Guide
excerpt: >-
  iPad + NAS manga reading tutorial covering Synology, ZSpace, FN OS, UGREEN and
  other major brands
category: Public
readTime: 10 min read
date: 2026年5月21日
tags:
  - NAS
  - 漫画
  - 教程
image: 'https://mangacapsule.com/images/blog/ipad-nas-tutorial_0.jpg'
author:
  name: Rainy
  avatar: 'https://mangacapsule.com/images/rainyavatar.jpg'
  role: Developer
---

# iPad + NAS Manga Reading Tutorial: Synology/ZSpace/FN OS/UGREEN Complete Brand Configuration Guide

You bought a NAS, stored your manga, and want to read comfortably on your iPad while lying down — this sounds simple, but many people get stuck on configuration details when actually trying to set it up.

This article covers **Synology, ZSpace, FN OS, UGREEN, and QNAP** — five major brands. From NAS-side protocol configuration to iPad-side connection settings, we'll walk you through step by step. No matter which brand of NAS you use, you'll find the corresponding instructions.

**End result**: Browse your NAS manga directory directly on your iPad, tap to read instantly — no downloads needed, page turning as fast as local files.

---

## Prerequisites

Before starting, confirm three things:

1. ✅ Your NAS and iPad are connected to the **same router** (required during setup, remote access works after)
2. ✅ You have a shared folder on your NAS for manga (e.g., `/Manga` or `/漫画`)
3. ✅ You know your NAS **login credentials**

---

## General Principle (Understand This First)

Regardless of NAS brand, the path for iPad to connect to NAS for manga reading is always the same:

```
Manga files on NAS hard drive
    ↓
Shared protocol (SMB / WebDAV)
    ↓
Manga reader app on iPad
    ↓
Streaming read, load while viewing
```

You only need to do two things:
1. **NAS side**: Confirm/enable a shared protocol
2. **iPad side**: Enter connection info in your reader app

Below are the NAS-side configuration steps for each brand.

---

## 🟢 Synology — Largest User Base

Synology is the traditional leader in the NAS market with the largest existing user base. Configuration is also the most mature.

### NAS Side Configuration

**Option A: SMB (Recommended, Zero Config)**

Synology has SMB enabled by default, no extra settings needed. You just need to confirm:

1. Log into Synology DSM → **Control Panel** → **File Services** → **SMB** tab
2. Confirm "Enable SMB service" is checked
3. Note your Synology **IP address** (visible at top right of DSM desktop, e.g., `192.168.1.100`)
4. Note your **shared folder name** (e.g., `Manga`)

Done, no other NAS-side operations needed.

**Option B: WebDAV (Better for External Access)**

1. Synology DSM → **Package Center** → Search and install **WebDAV Server**
2. Open WebDAV Server → Check "Enable HTTP" and "Enable HTTPS"
3. Note the port number (default 5005 for HTTP, 5006 for HTTPS)
4. WebDAV address format: `http://192.168.1.100:5005`

### iPad Side Connection

Open **Manga Capsule** → Tap "+" in top right → Add Disk:

- SMB method: Select SMB → Enter IP `192.168.1.100` → Shared folder `Manga` → Enter Synology credentials
- WebDAV method: Select WebDAV → Enter address `http://192.168.1.100:5005` → Enter Synology credentials

---

## ⚪ ZSpace — New Domestic Force

ZSpace is known for "simple and easy to use," and many first-time NAS buyers chose it. Manga functionality is also one of ZSpace's built-in highlights.

### NAS Side Configuration

**Option A: SMB**

SMB is enabled by default on ZSpace. In the ZSpace app on your phone:

1. **System Settings** → **File & Sharing Services** → Confirm SMB (Samba) is enabled
2. Note the NAS IP address (ZSpace app home → Device Info → IP Address)

**Option B: WebDAV**

1. ZSpace App → **System Settings** → **File & Sharing Services** → **WebDAV**
2. Enable WebDAV service, set port (default 8080)
3. WebDAV address format: `http://192.168.1.xxx:8080`

**Option C: Jimanhua (ZSpace Built-in Solution)**

ZSpace has a built-in "Jimanhua" app that can scrape covers and manage metadata. To use with iPad:

1. Use Jimanhua on ZSpace to organize your manga library
2. Enable WebDAV service
3. Connect via WebDAV on iPad to read Jimanhua's directory structure

> 💡 **Jimanhua + Manga Capsule combo**: Jimanhua handles metadata scraping, Manga Capsule handles iOS streaming reading experience. They complement each other — currently the best practice for ZSpace users.

### iPad Side Connection

Same steps as Synology. SMB is simplest — just enter IP and shared folder name.

---

## 🟡 FN OS — Fastest Growing Domestic NAS System

FN OS is the fastest growing domestic NAS system in recent years (free, full-featured, friendly interface), and our user data confirms this — FN OS user growth has already surpassed Synology.

### NAS Side Configuration

**SMB (Recommended)**

1. FN OS admin panel → **Settings** → **File Services** → **SMB/Samba**
2. Confirm SMB service is enabled
3. Note the NAS IP address (top of admin panel or in network settings)

**WebDAV**

1. FN OS → **Settings** → **File Services** → **WebDAV**
2. Enable WebDAV, set port number
3. WebDAV address format: `http://IP:port`

### iPad Side Connection

Same as Synology and ZSpace. Open Manga Capsule → Add Disk → Select SMB or WebDAV → Enter info → Done.

---

## 🟠 UGREEN — Best Entry-Level Choice

UGREEN NAS is known for high cost-performance and simple operation. Many users' first NAS is a UGREEN.

### NAS Side Configuration

1. UGREEN NAS admin panel (access NAS IP in browser)
2. **Control Panel** → **File Services** → **SMB** → Confirm enabled
3. If WebDAV needed: **Control Panel** → **File Services** → **WebDAV** → Enable and note port

UGREEN's system is relatively simple, SMB is on by default. Just get the IP address and you're ready to use.

### iPad Side Connection

Same as above. Open Manga Capsule → Add Disk → SMB or WebDAV → Enter IP and credentials.

---

## ⚫ QNAP — Power User's Choice

QNAP is powerful but configuration is slightly more complex.

### NAS Side Configuration

1. Log into QNAP QTS → **Control Panel** → **Network & File Services** → **Win/Mac/NFS/WebDAV**
2. **Microsoft Networking** tab → Check "Enable Microsoft Networking Service (SMB)"
3. **WebDAV** tab → Check "Enable WebDAV" → Note port number

### iPad Side Connection

Same as above. Choose either SMB or WebDAV.

---

## Advanced: Remote Access (Read Even When Away from Home)

After configuring LAN access, you might want to read manga on your NAS during commute, business trips, or travel. Here are some options:

| Solution | Difficulty | Speed | Recommendation |
|------|:---:|------|:---:|
| **Tailscale** | ⭐ Minimal | Depends on network | ⭐⭐⭐ Most Recommended |
| **ZeroTier** | ⭐⭐ Simple | Depends on network | ⭐⭐ |
| **Synology QuickConnect** | ⭐ Minimal | Slower | ⭐⭐ Synology users only |
| **Public IP + Port Forwarding** | ⭐⭐⭐ Complex | Fastest | ⭐ Not recommended for beginners |
| **Baidu Netdisk/Aliyun Drive Sync** | ⭐⭐ Medium | Depends on cloud | ⭐⭐ Alternative |

### Tailscale Solution (Recommended for Everyone)

This is currently the simplest and most stable remote access solution:

1. Install Tailscale on NAS (Synology Package Center / Docker / command line all work)
2. Install Tailscale App on iPad
3. Log into the same Tailscale account on both devices
4. When Manga Capsule on iPad connects to NAS, use the virtual IP assigned by Tailscale (`100.x.x.x`)

After that, no matter where you are, as long as you have network, you can stream read manga on your NAS just like at home. Tailscale free version supports up to 100 devices, completely sufficient for personal use.

### Cloud Drive Sync Solution (Alternative)

If you don't want to deal with network configuration, there's a "detour" option:

1. Set up Baidu Netdisk/Aliyun Drive sync task on NAS to sync manga folder to cloud
2. Manga Capsule on iPad directly mounts Baidu Netdisk or Aliyun Drive
3. Also supports streaming reading, no download needed

The benefit of this solution is **zero network configuration**; the downside is relying on cloud drive service, speed limited by cloud drive servers.

---

## FAQ

### Q: Why does connecting to NAS in Manga Capsule keep failing?

Troubleshoot in order:
1. Is iPad on the same WiFi as NAS? (Required during setup)
2. Is the IP address correct? (IP may change after NAS restart, recommend setting fixed IP on router)
3. Are credentials correct? (Not app login password, but NAS system user password)
4. Is shared folder name correct? (Case sensitive)

### Q: Hundreds of manga in a folder, will browsing on iPad be slow?

Manga Capsule's directory browsing uses paginated loading, only loading content currently displayed on screen. Hundreds of folders scroll smoothly, no need to load everything at once.

### Q: Manga file names are messy, any way to auto-organize?

Currently two approaches:
- Use tools like **Komga / Jimanhua** on NAS side to scrape covers and metadata, then iPad connects via OPDS / WebDAV
- Manga Capsule may consider adding **intelligent filename recognition** in the future, automatically extracting series name and volume number from filenames

---

## Summary

No matter what brand of NAS, the core process for iPad connecting to NAS for manga reading is the same: **Enable protocol → Enter IP → Start reading**. What truly differentiates the experience is whether the iPad reader can do **streaming loading** — making you feel like the remote files don't exist.

If you're still using the traditional "download first then extract" mode, try this solution — you'll open a new world.

> 📥 [Download Manga Capsule - App Store](https://apps.apple.com/cn/app/漫画胶囊-ai高清漫画阅读器/id6737119574)
>
> 🔗 Related Reading:
> - [NAS Manga Ultimate Solution: Instant Access to Your Private Manga Library on iPad](/zh/blog/nas-manga-reading-complete-guide)
> - [How to Read Hundreds of GB of Manga on NAS Directly with iPad?](/zh/blog/nas-stream-large-manga-ipad)
