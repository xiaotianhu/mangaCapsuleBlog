---
id: release-log-1.45
title: Manga Capsule 1.45 Released~
excerpt: >-
  A batch of optimizations during the National Day holiday: CBR fixes, faster
  ZIP/EPUB parsing, PDF streaming parsing...
category: Public
readTime: 2 min read
date: 2026年10月13日
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

## Manga Capsule 1.45 Released~

I didn't go anywhere during the National Day holiday and stayed home to work on a batch of optimizations, first releasing 1.44. But within a few days, I received feedback that CBR files couldn't be opened. I quickly located and fixed the issue, then followed up with 1.45. Since both versions were essentially one batch of work, I'm writing about them together~

### CBR Opening Issue Fixed

Let's start with this one, since it was the one being chased for a fix. CBR is a classic comic format packed with RAR, and many old resources online use this format. After this update, some users reported that files couldn't be opened. I found it was a parsing issue and have fixed it. If there are still files that can't be opened, keep sending them to me.

### ZIP/EPUB Parsing Is Much Faster

Comic files are often hundreds of megabytes with thousands of pages, and previously opening the directory would take a long time with a loading spinner. This version cleaned up the parsing backend, merging scattered reads into block reads, significantly reducing wait times for both the directory and page turning. The thicker the book, the more noticeable the improvement.

### PDF Streaming Parsing Continues to Improve

Large PDFs no longer need to be fully loaded before viewing; opening and page turning are now lighter and faster. We've been refining this line for several versions and will continue to do so.

### Large Files on 123 Cloud Drive Can Now Be Parsed

Previously, large files on 123 Cloud Drive would fail to parse. This version fixes that.

### Mounted iCloud on Mac Can Now Be Read

Users running the App on Mac (designed for iPad) previously reported that mounted iCloud directories couldn't be read. This version fixes that. The scenario on iOS with a single folder containing many images has also been optimized.

### OS26 Window Size Adaptation

OS26 changed its window management logic, causing the window to automatically split-screen when dragged, which was quite disruptive. This version includes adaptation, so after resizing, it will display correctly according to single or double pages.

### Pop-ups No Longer Appear Repeatedly

Some users reported that the onboarding guide and "old user return" pop-ups would appear repeatedly. The root cause was a lack of boundary checks in the display flow. This version adds those checks, so they won't appear when they shouldn't.

### Also Tidied Up the Membership Purchase Flow

Product information now prioritizes cache, making the purchase page open faster; eligibility checks no longer block the entire flow. Buying a membership shouldn't be more hassle than reading comics.

As usual, if you find it convenient, please give a five-star rating to encourage us—that's the most practical support. If you have any issues, feel free to report them in the app. Sending love ❤️
