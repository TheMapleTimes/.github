# 🍁 The Maple Times
**The Maple Times**는 넥슨 메이플스토리(KMS) OpenAPI를 활용한 데이터 서비스 프로젝트입니다.  
이곳은 대용량 게임 데이터를 다루기 위한 **백엔드 및 배치 시스템**과, <br/>생태계 기여를 위해 직접 개발한 **오픈소스 라이브러리**를 통합 관리하는 공간입니다.

[홈페이지 바로가기](https://kmstimes.com/)  

## 🗺️ Project Architecture & Repositories

### 1. ⚙️ [Server](https://github.com/TheMapleTimes/Server) `서비스 코어 API`
The Maple Times 프론트엔드 및 외부 요청에 데이터를 제공하고 핵심 비즈니스 로직을 처리하는 REST API 서버입니다.
* **주요 역할:** 클라이언트 요청 처리, DB 데이터 조회 및 가공

### 2. 🔄 [Batch](https://github.com/TheMapleTimes/Batch) `대용량 데이터 수집 파이프라인`
넥슨 OpenAPI로부터 방대한 유저 및 게임 데이터를 주기적으로 수집하고, 서비스에 맞게 정제하여 데이터베이스에 적재하는 자동화 시스템입니다.
* **주요 역할:** 데이터 수집 자동화, Rate Limit 대응, 데이터 정합성 관리

### 3. 📦 [nexon-kms-openapi](https://github.com/TheMapleTimes/nexon-kms-openapi) `오픈소스 라이브러리`
저뿐만 아니라 다른 개발자들도 자바/코틀린 환경에서 넥슨 OpenAPI를 손쉽게 사용할 수 있도록 **직접 설계하고 배포한 오픈소스 클라이언트 라이브러리**입니다.
* **주요 역할:** API 통신 모듈화, 요청 로직 캡슐화

## 🛠️ Tech Stack
The Maple Times를 구축하는 데 사용된 주요 기술 스택입니다.
*(상세한 기술 도입 배경 및 트러블슈팅 과정은 각 리포지토리의 README에 기록되어 있습니다.)*

### Frontend
- **Design:** stitch
- **Language:** Type Script
- **Library:** React19
- **Build Tool:** Vite

### Backend
- **Language**: Java 21
- **Framework**: Spring Boot 3.5.4, Spring Batch 5.2.4

### Database & Cache
- **Database**: Oracle Database (멀티 스키마 운영)
- **OLAP Database:** DuckDB (통계 집계 및 분석용 임베디드 DB)
- **Cache**: Valkey, Cloudflare KV

### Build & CI/CD
- **Build Tool:** Gradle (Kotlin DSL)
- **CI/CD:** GitHub Actions (Dockerizing & ARM64 Image Build)
- **Infrastructure**: Oracle Cloud Infrastructure (OCI)
- **Monitoring**: Micrometer Tracing, Zipkin, OCI Monitoring
