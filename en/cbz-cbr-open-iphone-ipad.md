---
id: cbz-cbr-open-iphone-ipad
title: >-
  iPhone/iPad Can't Open CBZ, CBR Files? Comic Format Explained in One Article
  (2026)
excerpt: >-
  What is CBZ/CBR, why iOS built-in apps can't open them, how to read correctly
  on iPhone and iPad
category: Tutorial
readTime: 5 min read
date: 2026年7月9日
tags:
  - CBZ
  - CBR
  - 格式
  - 教程
image: 'https://mangacapsule.com/images/blog/cbz-cbr-open-iphone-ipad_0.jpg'
author:
  name: Rainy
  avatar: 'https://mangacapsule.com/images/rainyavatar.jpg'
  role: Developer
---

# Can't Open CBZ, CBR Files on iPhone/iPad? Comic Format Explained in One Article

Here's the answer: **CBZ/CBR are compression formats specifically for comics, and iOS's built-in Books and Files apps don't support them—you need a comic reader to open them.** Install a reader that supports both formats (like Manga Capsule), share or import the file, and you can read it directly without extracting or converting.

## What Exactly Are CBZ and CBR?

Simple:

- **CBZ** = Comic Book Zip, essentially a **ZIP archive** with a renamed extension, containing sequentially named comic images
- **CBR** = Comic Book Rar, similarly a **RAR archive** with a renamed extension

The purpose of renaming the extension is to let the reader know "this is a comic book" and render pages in order, rather than treating it as a regular compressed file. So in theory, you can rename .cbz back to .zip and extract the images—but viewing comics one by one in the photo gallery is too primitive.

## Why Can't iOS Open Them?

- The Books app only supports EPUB and PDF
- The Files app can extract ZIP, but doesn't recognize the CBZ extension; after extraction, you can only view images one at a time in preview
- General compression tools downloaded from the App Store can extract, but lack comic reading experience (orientation, double-page, progress tracking)

## The Right Way: Three Steps

1. **Install a comic reader**: Search "Manga Capsule" in the App Store (free download, supports both CBZ and CBR, plus 10+ formats including ZIP/RAR/7Z/PDF/EPUB/MOBI/AZW3)
2. **Import files**, choose any method:
   - Received via WeChat/QQ/browser → Share menu → "Manga Capsule"
   - Computer transfer → WiFi book transfer (drag and drop on the same local network webpage) or USB cable
   - Files on cloud storage/NAS → mount directly, no import needed (see related readings at the end)
3. **Open to read**: automatically generates covers, remembers progress, supports manga direction, double-page, and white margin cropping

## iOS Comic Format Support Quick Reference

| Format | Nature | Books App | Files App | Manga Capsule |
|------|------|:---:|:---:|:---:|
| CBZ | ZIP renamed | ❌ | ❌ | ✅ |
| CBR | RAR renamed | ❌ | ❌ | ✅ |
| ZIP | Image archive | ❌ | 🟡 Extract only | ✅ |
| RAR / 7Z | Image archive | ❌ | ❌ | ✅ |
| PDF | Document | ✅ No comic optimization | 🟡 Preview | ✅ With crop/double-spread |
| EPUB | E-book | ✅ No comic optimization | ❌ | ✅ |
| MOBI / AZW3 | Kindle format | ❌ | ❌ | ✅ |

## FAQ

**Q: Do I need to extract CBZ first?**
A: No need. Comic readers read directly from inside the archive and can stream-load—files hundreds of MB open instantly.

**Q: CBR shows "file corrupted" error?**
A: First suspect incomplete download (check file size), then check if you only downloaded one part of a multi-volume archive. See [common file corruption causes](/zh/blog/blog-brokenfile).

**Q: Which is better for storing comics, cbz or zip?**
A: They're identical in content, use whichever you prefer. Use .cbz when sharing with others for clarity; .zip is fine for personal NAS storage.

**Q: Can iPhone open multi-GB CBZ collections?**
A: Yes. Streaming loading doesn't require loading the entire file into memory, large files open instantly; if stored on NAS/cloud, they don't take up local space at all.

---

> 📥 [Download Manga Capsule from App Store](https://apps.apple.com/cn/app/%E6%BC%AB%E7%94%BB%E8%83%B6%E5%9B%8A-nas-%E6%9C%AC%E5%9C%B0%E6%BC%AB%E7%94%BB%E9%98%85%E8%AF%BB%E5%99%A8/id6737119574?ppid=a6c5ba86-6cba-430d-907c-bbdb1455847b)
>
> 🔗 Related Readings:
> - [How to Transfer Comics from Kindle to iPad](/zh/blog/kindle-manga-to-ipad)
> - [Direct Baidu Cloud Comic Reading on iPad](/zh/blog/baidu-pan-manga-ipad)
