---
id: cbz-cbr-open-iphone-ipad
title: iPhone/iPad 打不開 CBZ、CBR 檔案？漫畫格式一篇講清（2026）
excerpt: CBZ/CBR 是什麼、為什麼 iOS 內建應用打不開、怎麼在 iPhone 和 iPad 上正確閱讀
category: 教學
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

# iPhone/iPad 打不開 CBZ、CBR 檔案？漫畫格式一篇講清

先說答案：**CBZ/CBR 是漫畫專用的壓縮包格式，iOS 內建的「圖書」和「檔案」App 不支援,需要一個漫畫閱讀器來打開**。裝一個支援這兩種格式的閱讀器（如「漫畫膠囊」），檔案分享或匯入進去就能直接看，不需要解壓、不需要轉格式。

## CBZ/CBR 到底是什麼？

很簡單：

- **CBZ** = Comic Book Zip，就是一個 **ZIP 壓縮包**改了副檔名，裡面是按順序命名的漫畫圖片
- **CBR** = Comic Book RAR，同理，**RAR 壓縮包**改副檔名

改副檔名的意義是讓閱讀器知道「這是一本漫畫」，按頁碼順序渲染，而不是當作普通壓縮檔。所以理論上你把 .cbz 改回 .zip 也能解壓出圖片——但一頁一頁在相簿裡看漫畫，就太原始了。

## 為什麼 iOS 打不開？

- 「圖書」App 只認 EPUB 和 PDF
- 「檔案」App 能解壓 ZIP,但 CBZ 副檔名不認識；解壓後也只能在預覽裡單張看圖
- App Store 下載的通用壓縮工具能解開,但沒有漫畫閱讀體驗（方向、雙頁、進度）

## 正確姿勢：三步

1. **裝一個漫畫閱讀器**：App Store 搜「漫畫膠囊」（免費下載,CBZ/CBR 都支援,還包括 ZIP/RAR/7Z/PDF/EPUB/MOBI/AZW3 等 10+ 格式）
2. **匯入檔案**,方式任選：
   - 微信/QQ/瀏覽器收到檔案 → 分享選單 → 「漫畫膠囊」
   - 電腦傳輸 → WiFi 導書（同一區域網路網頁拖曳上傳）或 USB 傳輸線
   - 檔案在雲端/NAS → 直接掛載,不用匯入（見文末相關閱讀）
3. **點開閱讀**：自動生成封面、記住進度,日漫方向、雙頁、裁白邊都有

## iOS 漫畫格式支援速查表

| 格式 | 本質 | 圖書App | 檔案App | 漫畫膠囊 |
|------|------|:---:|:---:|:---:|
| CBZ | ZIP 改副檔名 | ❌ | ❌ | ✅ |
| CBR | RAR 改副檔名 | ❌ | ❌ | ✅ |
| ZIP | 圖片壓縮包 | ❌ | 🟡 僅解壓 | ✅ |
| RAR / 7Z | 圖片壓縮包 | ❌ | ❌ | ✅ |
| PDF | 文件 | ✅ 無漫畫優化 | 🟡 預覽 | ✅ 含裁白邊/條漫 |
| EPUB | 電子書 | ✅ 無漫畫優化 | ❌ | ✅ |
| MOBI / AZW3 | Kindle 格式 | ❌ | ❌ | ✅ |

## 常見問題 FAQ

**Q：CBZ 需要先解壓嗎？**
A：不需要。漫畫閱讀器直接讀壓縮包內部,還能串流載入——幾百 MB 的檔案秒開。

**Q：CBR 開啟報錯「檔案損壞」怎麼辦？**
A：優先懷疑下載不完整（比對檔案大小），其次是分卷壓縮包只下了一卷。可參考[檔案損壞常見原因](/zh/blog/blog-brokenfile)。

**Q：cbz 和 zip 哪個格式存漫畫更好？**
A：內容一樣，隨意。分享給別人建議用 .cbz，語意清楚；自己存 NAS 用 .zip 也完全沒問題。

**Q：幾個 G 的 CBZ 大合集 iPhone 能打開嗎？**
A：能。串流載入不需要把檔案全部讀入記憶體，大檔案也是點開即讀；存在 NAS/雲端的話連本機空間都不佔。

---

> 📥 [App Store 下載漫畫膠囊](https://apps.apple.com/cn/app/%E6%BC%AB%E7%94%BB%E8%83%B6%E5%9B%8A-nas-%E6%9C%AC%E5%9C%B0%E6%BC%AB%E7%94%BB%E9%98%85%E8%AF%BB%E5%99%A8/id6737119574?ppid=a6c5ba86-6cba-430d-907c-bbdb1455847b)
>
> 🔗 相關閱讀：
> - [Kindle 裡的漫畫怎麼轉到 iPad 上看](/zh/blog/kindle-manga-to-ipad)
> - [百度雲端硬碟漫畫 iPad 直讀方案](/zh/blog/baidu-pan-manga-ipad)
