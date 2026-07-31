<div align="center">

# 📈 톡톡스 (TockTalks)

### (S)TOCK + TALKS

**실시간 시세 기반 모의투자 배틀 & 투자 커뮤니티**

**TEAM TockTalks**

[![Backend](https://img.shields.io/badge/Backend-ureca__TockTalks-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/TockTalks/ureca_TockTalks)
[![Frontend](https://img.shields.io/badge/Frontend-ureca__TockTalks--frontend-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/TockTalks/ureca_TockTalks-frontend)

</div>

---

## 목차

* [프로젝트 정보](#프로젝트-정보)
* [Getting Started](#getting-started)
* [프로젝트 비전](#프로젝트-비전)
* [주요 기능](#주요-기능)
* [사용자 시나리오](#사용자-시나리오)
* [팀 구성](#팀-구성)
* [개발 기간](#개발-기간)
* [기술 스택](#기술-스택)
* [시스템 아키텍처](#시스템-아키텍처)
* [대표 문서](#대표-문서)
* [라이선스 및 문의](#라이선스-및-문의)

---

## 프로젝트 정보

| 항목 | 내용 |
|---|---|
| **팀명** | **TockTalks** |
| **프로젝트명** | **톡톡스 (TockTalks)** |
| **한 줄 소개** | 실시간 시세 기반 모의투자 배틀 & 투자 커뮤니티 |
| **개발 기간** | 2026.07.16 ~ 2026.07.27 (2주) |
| **팀 구성** | 백엔드 개발자 5명 |
| **배포 환경** | 별도 프로덕션 배포 없이, 로컬/팀 공유(Docker) 환경에서 개발·검증 |

---

## Getting Started

이 저장소는 코드가 아니라 팀 프로필/공통 문서를 관리하는 저장소입니다. 실제 실행 방법은 각 레포를 참고하세요.

* **백엔드**: [ureca_TockTalks](https://github.com/TockTalks/ureca_TockTalks#getting-started) — `docker-compose up -d` → `./gradlew bootRun`
* **프론트엔드**: [ureca_TockTalks-frontend](https://github.com/TockTalks/ureca_TockTalks-frontend) — Vite dev 서버, 백엔드(`:8080`)로 API 프록시

---

## 프로젝트 비전

기존 모의투자 서비스는 대부분 개인이 혼자 가상 자산으로 매매 연습을 하는 데 그칩니다.

* 혼자 하는 연습은 금방 흥미가 떨어진다
* 실제 시세와 동떨어진 가상 데이터라 실감이 안 난다
* 투자 기록을 남겨도 공유하고 비교할 곳이 없다

톡톡스는 여기에 **"같은 조건에서 경쟁한다"** 는 재미를 더했습니다. 유저가 직접 **방(Room)** 을 만들어 시드머니와 기간을 정하면, 같은 조건에서 시작한 사람들끼리 실시간 시세를 기반으로 수익률을 겨룹니다. 거래 내역은 커뮤니티에 투자 인증 카드로 공유할 수 있어, 신뢰도 있는 투자 인증 문화를 만듭니다.

### 핵심 가치 제안

| 가치 | 설명 |
|---|---|
| **공정한 경쟁** | 같은 시드머니·같은 기간으로 시작해 실력만으로 겨루는 방(Room) 배틀 |
| **정확한 체결** | 동시에 여러 참가자가 매수/매도해도 잔고·보유 수량이 어긋나지 않는 동시성 제어 |
| **실감 나는 시세** | 한국투자증권(KIS) Open API 기반 실시간 국내 주식 시세 |
| **꾸준한 동기부여** | 실시간 랭킹과 투자 인증 카드로 성과를 바로 확인하고 공유 |

---

## 주요 기능

| 기능 | 설명 |
|---|---|
| 🔐 회원가입 / 로그인 | 자체 로그인 + 카카오 소셜 로그인 |
| 💰 모의투자 | 실시간 시세 기반 매수/매도, 동시성 제어 |
| 🏆 방(Room) 배틀 | 시드머니·기간 설정, 공개/비공개 방, 실시간 랭킹, 종료 후 아카이브 |
| 📊 포트폴리오 | 보유 종목, 평가손익, 자산 변동 히스토리 |
| 💬 커뮤니티 | 종목 태그 게시글, 실거래 기반 투자 인증 카드, 좋아요/댓글 |
| 🛠️ 백오피스 | 회원/신고/공지/방 관리, 가입자·거래·랭킹·커뮤니티 통계 대시보드 |

---

## 사용자 시나리오

### 페르소나 설계 원칙

톡톡스의 페르소나는 각 기능이 "누구의 어떤 불편을 해결하는지"를 보여주는 기준입니다.

| 페르소나 | 핵심 연결 기능 |
|---|---|
| **박현우** — 경쟁을 즐기는 직장인 | 방(Room) 배틀, 동시성 제어, 실시간 랭킹 |
| **최유나** — 투자를 처음 배우는 사회초년생 | 포트폴리오, 자산 변동 히스토리, 관심종목 |
| **정다인** — 기록을 남기고 나누고 싶은 투자자 | 커뮤니티, 투자 인증 카드, 댓글/좋아요 |

### 1. 페르소나 — 박현우 (27세, 마케팅 사원)

**Goal**: 친구들과 같은 조건으로 시작해서, 누가 더 잘 파는지 공정하게 겨루고 싶다.

**Pain Point**: 기존 모의투자 앱은 혼자 하니 긴장감이 없고, 금방 흥미를 잃는다.

**시나리오**: 친구 4명과 같은 시드머니·같은 기간으로 방을 만든다 → 실시간 시세를 보며 매수/매도한다 → 여러 명이 거의 동시에 주문을 넣어도 체결이 꼬이지 않는다 → 실시간 랭킹으로 지금 몇 등인지 바로 확인한다.

### 2. 페르소나 — 최유나 (24세, 사회초년생)

**Goal**: 큰돈을 잃을 걱정 없이, 내 투자 습관과 성과를 눈으로 확인하고 싶다.

**Pain Point**: 실제 계좌로 연습하자니 무섭고, 그렇다고 그냥 눈으로만 보자니 실감이 안 난다.

**시나리오**: 관심 있는 종목을 관심종목에 등록한다 → 모의투자로 매수해본다 → 포트폴리오에서 평가손익과 자산 변동 히스토리를 시간순으로 확인한다 → 다음 방에서는 이전 기록을 참고해 다른 전략을 시도한다.

### 3. 페르소나 — 정다인 (31세, 투자 커뮤니티 활동가)

**Goal**: 내가 어떤 판단으로 어떤 종목을 샀는지 기록하고, 다른 사람과 이야기 나누고 싶다.

**Pain Point**: 캡처나 말로만 인증하면 신뢰가 안 가고, 대화도 이어지지 않는다.

**시나리오**: 실제 거래 내역을 바탕으로 투자 인증 카드를 만들어 커뮤니티에 올린다 → 종목 태그로 같은 종목에 관심 있는 사람들과 댓글로 의견을 나눈다 → 다른 사람의 인증 카드에 좋아요를 남긴다.

---

## 팀 구성

| 역할 | 이름 | 담당 도메인 |
|---|---|---|
| 팀장 | 이진희 | Portfolio, Backoffice |
| 팀원 | 윤태형 | Auth, Room |
| 팀원 | 안제홍 | Ranking, Community |
| 팀원 | 최재웅 | Price, Member |
| 팀원 | 박지훈 | Trade |

---

## 개발 기간

```
2026.07.16 ~ 2026.07.27 (2주)
```

---

## 기술 스택

### Backend

| 분류 | 기술 |
|---|---|
| 언어 / 프레임워크 | ![Java](https://img.shields.io/badge/Java-21-007396?style=for-the-badge&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1-6DB33F?style=for-the-badge&logo=springboot&logoColor=white) ![Gradle](https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white) |
| ORM | ![Spring Data JPA](https://img.shields.io/badge/Spring%20Data%20JPA-59666C?style=for-the-badge&logo=hibernate&logoColor=white) |
| 인증 | ![Spring Security](https://img.shields.io/badge/Spring%20Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white) ![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white) |
| 실시간 통신 | ![WebSocket](https://img.shields.io/badge/WebSocket-010101?style=for-the-badge) ![STOMP](https://img.shields.io/badge/STOMP-6DB33F?style=for-the-badge) |
| 캐시 / 락 / Pub-Sub | ![Redis](https://img.shields.io/badge/Redis-7-DC382D?style=for-the-badge&logo=redis&logoColor=white) |

### Database

| 분류 | 기술 |
|---|---|
| RDBMS | ![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white) |
| 캐시 스토어 | ![Redis](https://img.shields.io/badge/Redis-7-DC382D?style=for-the-badge&logo=redis&logoColor=white) ![Upstash](https://img.shields.io/badge/Upstash-00E9A3?style=for-the-badge&logo=upstash&logoColor=black) |

### Frontend

| 분류 | 기술 |
|---|---|
| 프레임워크 | ![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white) |
| 실시간 통신 | ![StompJS](https://img.shields.io/badge/%40stomp%2Fstompjs-010101?style=for-the-badge) |
| 차트 | ![Recharts](https://img.shields.io/badge/Recharts-22B5BF?style=for-the-badge) |

### 외부 연동

| 분류 | 기술 |
|---|---|
| 시세 | ![KIS](https://img.shields.io/badge/한국투자증권-KIS%20Open%20API-00857C?style=for-the-badge) |
| 소셜 로그인 | ![Kakao](https://img.shields.io/badge/Kakao%20OAuth2-FFCD00?style=for-the-badge&logo=kakaotalk&logoColor=black) |

---

## 시스템 아키텍처

```
[클라이언트 — React (Vite)]
        │ REST / STOMP over WebSocket
        ▼
[백엔드 — Spring Boot]
   ├─▶ [MySQL]  회원 / 방 / 거래 / 커뮤니티 등 영속 데이터
   └─▶ [Redis]  랭킹, 시세 캐시, 인증 토큰 캐시, Pub/Sub

[한국투자증권 KIS Open API] ◀─ WebSocket(실시간 시세) / REST(현재가·차트)
[카카오 로그인 API]        ◀─ OAuth2
```

자세한 아키텍처와 핵심 기능 설명은 [백엔드 README](https://github.com/TockTalks/ureca_TockTalks#4-시스템-아키텍처)를 참고하세요.

---

## 대표 문서

* [백엔드 README](https://github.com/TockTalks/ureca_TockTalks) — 시스템 아키텍처, ERD, 핵심 기능(공유 Redis 최적화, 동시성 제어, 실시간 시세 파이프라인, 장애 대응), 트러블슈팅
* [프론트엔드 README](https://github.com/TockTalks/ureca_TockTalks-frontend) — 프론트엔드 실행/구조

---

## 라이선스 및 문의

이 프로젝트는 백엔드 부트캠프 미니프로젝트로 제작되었습니다.

Copyright (c) 2026 TockTalks Team. All Rights Reserved.

**문의**: [TockTalks GitHub Organization](https://github.com/TockTalks)
