---
id: komga-ios-client
title: Komga有iOS客戶端嗎？iPhone/iPad連接Komga漫畫伺服器方案（2026）
excerpt: Komga沒有官方iOS客戶端，但透過OPDS或直接掛載NAS目錄，iPad照樣串流讀你的Komga書庫
category: 教學
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
  role: 開發者
---

# Komga iOS 客戶端，iPhone/iPad 連接 Komga 漫畫伺服器方案

首先說明，**Komga 沒有官方 iOS 客戶端**，只會網頁版；在 iPad 上能用但體驗一般（沒有離線快取、翻頁手勢和閱讀模式都比較基礎）。

實際可行的方案有兩個：**透過 OPDS 協定連線**，或者**跳過 Komga、直接掛載底層檔案目錄**。兩個方案「漫畫膠囊」都支援，下面分別講。

## 方案一：OPDS 連線 Komga

Komga 內建了 OPDS 目錄服務，任何支援 OPDS 的閱讀器都能瀏覽和拉取書庫。

設定步驟（以漫畫膠囊為例）：

1. 書架頁側邊欄，添加網路書架 → 選擇「OPDSv2」
2. 位址填：`http://你的Komga伺服器位址:25600`（25600 是 Komga 預設連接埠，改過的換成自己的）
3. 填 Komga 的使用者名稱密碼，連線
4. 書庫按 Komga 裡的庫結構展示，點開即讀

這個方案的好處是保留 Komga 的庫組織（系列、合集），適合已經在 Komga 裡精心整理過元資料的使用者。
漫畫膠囊支援的是新版Komga，OPDS v2 協定，太老的Komga需要自己更新下哈。

## 方案二：直接掛載檔案目錄（我更推薦）

Komga 本質上是在你 NAS 的漫畫資料夾上加了一層管理服務。如果你的目錄本身就整理得不錯（按作品分資料夾），其實可以**跳過 Komga 這一層**，用 SMB 或 WebDAV 直接把資料夾掛載進閱讀器：

1. 書架頁側邊欄「添加網路書架」→「SMB」或「WebDAV」
2. 填 NAS 位址和帳號,選中漫畫根目錄
3. 資料夾結構直接映射成書架，封面自動生成

**為什麼更推薦這個**：

鏈路少一層（不依賴 Komga 服務的狀態）、支援串流載入（大檔案點開即讀，OPDS 拉取整個檔案則要等下載）、NAS 上新增檔案立刻可見,不用等 Komga 掃庫。

## 兩個方案怎麼選

| 對比項 | OPDS 連 Komga | SMB/WebDAV 直掛 |
|--------|:---:|:---:|
| 保留 Komga 元資料/系列組織 | ✅ | ❌ 按資料夾結構 |
| 大檔案開啟速度 | 需拉取完整檔案 | ✅ 串流秒開 |
| 依賴 Komga 服務線上 | 是 | 否 |
| 外網存取 | 都可以（需做連接埠轉發/內網穿透，建議 HTTPS 或 VPN） | 同左 |

我的建議：家裡主要設備是 iPad 的話直掛就夠了；Komga 服務繼續留著給桌面網頁端和安卓端（Tachiyomi/Mihon 系）用，互不衝突。

## 常見問題 FAQ

**Q：Paperback、Panels 這些 App 能連 Komga 嗎？**
A：Panels 支援 OPDS 可以連；Paperback 需要裝擴充來源。國內使用者注意這兩款對中文介面和條漫模式的支援有限。

**Q：出門在外怎麼存取家裡的 Komga/NAS？**
A：常見做法是 Tailscale/WireGuard 組網（推薦，安全），或者路由器連接埠轉發+HTTPS。組網後 App 裡填內網位址照常用。

**Q：Komga 的替代品 Kavita 也適用這套方案嗎？**
A：適用。Kavita 同樣提供 OPDS 介面，直掛檔案目錄的方案更是和伺服端軟體無關。

---

> 📥 [App Store 下載漫畫膠囊](https://apps.apple.com/cn/app/%E6%BC%AB%E7%94%BB%E8%83%B6%E5%9B%8A-nas-%E6%9C%AC%E5%9C%B0%E6%BC%AB%E7%94%BB%E9%98%85%E8%AF%BB%E5%99%A8/id6737119574?ppid=a6c5ba86-6cba-430d-907c-bbdb1455847b)
>
> 🔗 相關閱讀：
> - [NAS 裡幾百 G 漫畫怎麼用 iPad 直接看](/zh/blog/nas-stream-large-manga-ipad)
> - [iPad 搭配 NAS 看漫畫：全品牌設定指南](/zh/blog/ipad-nas-manga-tutorial)
