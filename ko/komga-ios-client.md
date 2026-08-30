---
id: komga-ios-client
title: Komga에 iOS 클라이언트가 있나요? iPhone/iPad로 Komga 만화 서버 연결 방법 (2026)
excerpt: >-
  Komga에는 공식 iOS 클라이언트가 없지만, OPDS 또는 NAS 디렉토리 직접 마운트를 통해 iPad에서도 Komga 서재를
  스트리밍으로 읽을 수 있습니다
category: 튜토리얼
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

# Komga iOS 클라이언트, iPhone/iPad로 Komga 만화 서버 연결 방법

먼저 설명하자면, **Komga에는 공식 iOS 클라이언트가 없으며** 웹 버전만 제공한다. iPad에서도 사용할 수 있지만 경험은 그저 그뿐이다(오프라인 캐시 없음, 페이지 넘기기 제스처와 읽기 모드가 기본적이다).

실제로可行的인 방법은 두 가지가 있다: **OPDS 프로토콜을 통해 연결**하거나, **Komga를 건너뛰고 NAS 폴더를 직접 마운트**. 두 방법 모두 「漫画캡슐」에서 지원하므로, 각각 설명한다.

## 방법 1: OPDS로 Komga 연결

Komga는 내장된 OPDS 디렉토리 서비스를 제공하며, OPDS를 지원하는 모든 리더기에서 서재를 탐색하고 가져올 수 있다.

설정 단계(漫画캡슐 예시):

1. 서재 페이지 사이드바에서 네트워크 서재 추가 → 「OPDSv2」 선택
2. 주소 입력: `http://Komga 서버 주소:25600` (25600은 Komga 기본 포트, 변경했다면 자신의 포트로)
3. Komga 사용자 이름과 비밀번호 입력, 연결
4. 서재는 Komga의 라이브러리 구조로 표시되며, 클릭하면 바로 읽기 가능

이 방법의 장점은 Komga의 라이브러리 구성(시리즈, 컬렉션)을 유지할 수 있다는 것이다. 이미 Komga에서 메타데이터를 정성스럽게 정리한 사용자에게 적합하다.
漫画캡슐은 새 버전 Komga를 지원하며, OPDS v2 프로토콜을 사용한다. 너무 오래된 Komga는 직접 업데이트해야 한다.

## 방법 2: 파일 디렉토리 직접 마운트 (더 권장)

Komga는 기본적으로 NAS의 만화 폴더 위에 관리 레이어를 추가한 것이다. 만약 디렉토리 자체가 잘 정리되어 있다면(작품별로 폴더 구분), **Komga 레이어를 건너뛰고** SMB 또는 WebDAV를 사용하여 폴더를 직접 리더기에 마운트할 수 있다:

1. 서재 페이지 사이드바「네트워크 서재 추가」→「SMB」또는「WebDAV」
2. NAS 주소와 계정 입력, 만화 루트 디렉토리 선택
3. 폴더 구조가 서재로 직접 매핑되고, 표지가 자동 생성

**왜 이것을 더 권장하는지**:

레이어가 하나 줄어들고(Komga 서비스 상태에 의존하지 않음), 스트리딩 로딩 지원(큰 파일은 클릭하면 바로 읽기, OPDS는 전체 파일을 다운로드해야 함), NAS에 새 파일이 즉시 표시됨(Komga 스캔 대기 필요 없음).

## 두 방법 중 선택

| 비교 항목 | OPDS Komga 연결 | SMB/WebDAV 직접 마운트 |
|--------|:---:|:---:|
| Komga 메타데이터/시리즈 구성 유지 | ✅ | ❌ 폴더 구조 기준 |
| 큰 파일 열기 속도 | 전체 파일 다운로드 필요 | ✅ 스트리밍 즉시 열기 |
| Komga 서비스 온라인 필요 여부 | 예 | 아니오 |
| 외부 접근 | 모두 가능(포트 포워딩/내망穿透 필요, HTTPS 또는 VPN 권장) | 좌동 |

내 제안: 집에서 주요 기기가 iPad라면 직접 마운트로 충분; Komga 서비스는 데스크톱 웹端과 안드로이드端(Tachiyomi/Mihon 계열)에 계속 두고 사용하면 충돌하지 않는다.

## 자주 묻는 질문 FAQ

**Q: Paperback, Panels 같은 앱으로 Komga에 연결할 수 있나요?**
A: Panels는 OPDS를 지원하므로 연결 가능; Paperback는 확장 소스 설치 필요. 국내 사용자는 이 두 가지의 중국어 인터페이스와 웹툰 모드 지원이 제한적이라는 점에 주의.

**Q:外出时怎么访问家里的 Komga/NAS?**
A: 일반적인 방법은 Tailscale/WireGuard 네트워킹(권장, 안전), 또는 라우터 포트 포워딩+HTTPS. 네트워킹 후 앱에서 내부 주소 그대로 사용.

**Q: Komga 대안인 Kavita도 이 방법을 적용할 수 있나요?**
A: 적용 가능. Kavita도同样 OPDS 인터페이스를 제공하며, 파일 디렉토리 직접 마운트 방법은服务端 소프트웨어와 무관하다.

---

> 📥 [App Store에서 漫画캡슐 다운로드](https://apps.apple.com/cn/app/%E6%BC%AB%E7%94%BB%E8%83%B6%E5%9B%8A-nas-%E6%9C%AC%E5%9C%B0%E6%BC%AB%E7%94%BB%E9%98%85%E8%AF%BB%E5%99%A8/id6737119574?ppid=a6c5ba86-6cba-430d-907c-bbdb1455847b)
>
> 🔗 관련 읽기:
> - [NAS에 있는 수백 G 만화를 iPad에서 직접 보는 방법](/zh/blog/nas-stream-large-manga-ipad)
> - [iPad와 NAS로 만화 보기:全 브랜드 설정 가이드](/zh/blog/ipad-nas-manga-tutorial)
