---
id: '3'
title: NAS ユーザーガイド：最適な体験のためのWebDAV設定方法
excerpt: Synology、QNAP、ZSpace...自宅のNASを持ち運び可能なクラウド漫画ライブラリにする方法をステップバイステップで解説。
category: チュートリアル
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

WebDAV は現在、互換性が最も高く、性能が最も均衡したファイル転送プロトコルの一つです。Manga Capsule と組み合わせることで、公司でサボって自宅NAS上の漫画を読むことができます（嘘）。

## 準備作業

まず、NAS の WebDAV サービスを有効にし、ルーターでポート転送を設定する必要があります（外部アクセスする場合）。

```
// 典型的な WebDAV URL 構造
http://[あなたのドメイン名またはIP]:[ポート]/[共有フォルダパス]
```

Manga Capsule の「接続」ページで WebDAV を選択し、上記の情報を入力します。接続に成功すると、ファイルリストがすぐに表示されます。
