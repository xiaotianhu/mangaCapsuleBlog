---
id: '3'
title: 'NAS 사용자 가이드: 최적의 경험을 위한 WebDAV 구성 방법'
excerpt: 'Synology, QNAP, 극공간... 집의 NAS를 휴대한 클라우드 만화 저장소로 만드는 방법을 단계별로 알려드립니다.'
category: 튜토리얼
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

WebDAV는 현재 호환성이 가장 좋고 성능이 가장 균형 잡힌 파일 전송 프로토콜 중 하나입니다. Manga Capsule과 함께하면 회사에서 집에 있는 NAS의 만화를 읽을 수 있습니다 (농담입니다).

## 사전 준비

먼저 NAS에서 WebDAV 서비스가 활성화되어 있고, 라우터에서 포트 포워딩이 구성되어 있는지 확인하세요 (외부 접근 시).

```
// 일반적인 WebDAV URL 구조
http://[도메인 또는 IP]:[포트]/[공유 폴더 경로]
```

Manga Capsule의 "연결" 페이지에서 WebDAV를 선택하고 위 정보를 입력하세요. 연결에 성공하면 즉시 파일 목록을 볼 수 있습니다.
