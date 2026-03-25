---
id: '3'
title: NAS 使用者指南：如何設定 WebDAV 以獲得最佳體驗
excerpt: Synology、QNAP、極空間... 一步步教你如何將家裡的 NAS 變成隨身攜帶的雲端漫畫庫。
category: 教學
readTime: 12 min read
date: 2024年3月15日
tags:
  - Tutorial
  - NAS
image: 'https://picsum.photos/seed/nas_setup/800/600'
author:
  name: Rainy
  avatar: 'https://mangacapsule.com/images/rainyavatar.jpg'
  role: Developer
---

WebDAV 是目前相容性最好、效能最均衡的檔案傳輸協定之一。配合 Manga Capsule，你可以實現在公司摸魚看家裡 NAS 上的漫畫（誤）。

## 準備工作

首先，你需要確保你的 NAS 已經開啟了 WebDAV 服務，並且在路由器上設定了連接埠轉發（如果是外網存取）。

```
// 典型的 WebDAV URL 結構
http://[你的網域或IP]:[連接埠]/[共用資料夾路徑]
```

在 Manga Capsule 的「連線」頁面，選擇 WebDAV，填入上述資訊。如果連線成功，你應該能立即看到檔案列表。
