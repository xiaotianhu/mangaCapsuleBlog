---
id: release-log-1.43
title: Manga Capsule 1.43 Released~
excerpt: >-
  A bunch of minor updates, fixing various issues reported by users. Please keep
  the feedback coming~
category: Public
readTime: 1 min read
date: 2026年08月30日
tags:
  - 资源
  - 漫画
  - 工具
image: 'https://mangacapsule.com/images/blog-release-log.jpg'
author:
  name: Rainy
  avatar: 'https://mangacapsule.com/images/rainyavatar.jpg'
  role: Developer
---

## Manga Capsule 1.43 Released~

This version doesn't have any major features, just minor fixes. The reason is simple — last month I went through the feedback list I've been collecting for a year, reading through each item, and found that many issues weren't actually that hard to fix, they just kept getting pushed back by more urgent matters. I felt a bit guilty, so this version is dedicated to clearing out a bunch of these issues.

### OPDS V1 Protocol Support

In version 1.34, we started supporting OPDS, but only adapted it for Komga using the new protocol. This time we've added V1 support as well. Some friends with older NAS servers running legacy services that only recognize V1 couldn't connect before — now they can. Honestly, these protocol adaptations are quite tedious, as every service implements them differently, but every additional user who can use it makes it worth it.

### Local Disk Now Supports Opening Encrypted PDFs

These are password-protected PDFs that previously would throw an error when opened, not even giving you a chance to enter a password. Now you can enter a password and read local files. For encrypted PDFs on cloud drives, you'll still need to download them first before opening — streaming read can't work around encryption for cloud files, so cloud drive users will need to download first.

### Fixed Issue with Failing to Open Next Book in Komga

Previously, when reading one book continuously and trying to open the next, it would often get stuck on the loading screen, requiring you to exit and re-enter. After investigation, it turned out to be a resource release timing issue. After the fix, continuous reading is much smoother.

### Optimized Landscape Experience on Mobile

Previously, when viewing comics in landscape mode, some page layouts would get messed up, and menus were easy to accidentally touch. This time I've reorganized everything. Friends who prefer landscape viewing can give it a try.

### Fixed Several Crash Issues

Every time I see crash logs, I feel pretty guilty. People will call you out for missing features, but when a crash happens, they're right in the middle of reading a comic, and suddenly it's gone — they leave without a word. That silence hurts the most. Fixing crashes has no trick to it, just going through logs one by one to find reproduction paths. This version fixes a few high-frequency ones, so it should be quieter for a while.

When releasing these small version updates, I have mixed feelings. On one hand, I feel like, why is it just more patches again, without anything new to show. On the other hand, I think, someone took the time to provide feedback, which means they're actually using it to read comics — that's more valuable than any new feature.

Keep the feedback coming — your feedback is my changelog. Sending love ❤️
