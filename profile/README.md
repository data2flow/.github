<div align="center">

🌐 **한국어** | **[English](./README.en.md)** | **[日本語](./README.ja.md)** | **[简体中文](./README.zh.md)**

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./logo-dark.svg">
  <img alt="data2flow" src="./logo-light.svg" width="300">
</picture>

**지켜보는 운영은 끝났습니다. 이제, 스스로 해결합니다.**

건물 안 센서 데이터를 설정만으로 연결하고, 정리하고, 분석하고,<br>그 결과에 따라 장비까지 움직이는 AIoT 플랫폼


</div>

---

## data2flow는

> 실습실 CO2가 1,000ppm을 넘은 상태가 5분 동안 이어집니다.<br>
> → data2flow가 감지해 환기 장치를 켭니다.<br>
> → 15분 안에 내려가지 않으면 담당자에게 "제어 효과 없음" 알림을 보냅니다.<br>
> → 한 달 뒤 기준 초과 시간이 얼마나 줄었는지 리포트로 보여 줍니다.

이 과정 전체를 코드 배포 없이 **화면의 설정과 플로우(그림)** 로 만듭니다. 이름 그대로 **data**가 **flow**를 따라 정제 → 분석 → 행동으로 이어집니다.

## 다섯 단계

| 단계 | 하는 일 |
|---|---|
| **연결** | LoRaWAN(ChirpStack)·MQTT·Webhook·엣지 게이트웨이 센서를 화면 설정만으로 붙이고, 들어온 데이터로 새 기기를 찾아 관리자 승인으로 등록 |
| **정제** | 회사마다 다른 데이터를 같은 모양으로. 샌드박스 JavaScript 스크립트, 품질 코드, 원본 보관과 재처리 |
| **이해** | 고르기만 하면 실행되는 분석 템플릿(쾌적도·공간 활용·이상 탐지·에너지)과 AI의 한국어 해설 |
| **행동** | 플로우 편집기와 규칙으로 감지하고, 제조사와 관계없이 같은 제어 창구로 장비를 움직이고, 텔레그램으로 알림 |
| **재현** | 실제 장비 없이 가상 공간·가상 센서·시나리오로 자동화를 먼저 검증 |

## 무엇이 다른가

- **측정 → 기준 → 행동 → 증빙**이 한 제품에 이어집니다. 실내공기질 기준 판정과 준수 리포트까지.
- **데이터 유실 0, 무중단 배포.** 재배포 중에도 들어온 메시지를 한 건도 잃지 않습니다.
- **라이브 편집.** 플로우를 고쳐도 엔진을 멈추지 않고 바로 반영합니다.
- **벤더 중립 제어.** Capability + Driver + Control Facade로 화면·플로우·AI가 같은 창구를 씁니다.
- **오픈소스 라이선스 정책.** Apache·MIT·BSD 등 허용 라이선스만 제품에 담습니다.

## 저장소

| 저장소 | 역할 | 기술 |
|---|---|---|
| [data2flow-docs](https://github.com/data2flow/data2flow-docs) | 스펙·설계·결정 기록·스토리보드 | Markdown |
| data2flow-web | 화면 + BFF (서버 렌더링, 세션) | React Router v7, TypeScript |
| data2flow-api-gateway | 라우팅, 토큰 확인, 신원 전달 | Spring Cloud Gateway |
| data2flow-auth | 로그인, 토큰 발급·폐기 | Spring Boot 4 |
| data2flow-core-api | 회원·기기·공간·소스·플로우 정의·규칙·대시보드 | Spring Boot 4 |
| data2flow-ingress | MQTT 구독, Webhook·엣지 수신 | Spring Boot 4 |
| data2flow-pipeline | 디코딩, 스크립트, 저장, 집계 | Spring Boot 4, GraalJS |
| data2flow-flow-engine | 플로우·규칙 실행, 라이브 리로드 | Spring Boot 4, GraalJS |
| data2flow-action | 장비 제어, 알림, 외부 출력 | Spring Boot 4 |
| data2flow-simulator | 가상 공간·센서·장비, 시나리오 | Spring Boot 4 |
| data2flow-ai | 결과 해설, 리포트, 챗봇, MCP 서버 | Spring AI |
| data2flow-analytics | 분석 템플릿, 실시간 추론 | Python, FastAPI |
| data2flow-contracts | 메시지 스키마, 공통 응답·오류 형식 | Java, JSON Schema |
| data2flow-manifests | Kubernetes 배포 (GitOps) | Kustomize, Argo CD |

## 기술 스택

`React Router v7` `TypeScript` `Spring Boot 4` `Java 21` `Spring AI` `Python FastAPI` `PostgreSQL 18 + pgvector` `RabbitMQ Streams` `Redis` `GraalJS` `Kubernetes` `Argo CD`

## 릴리스

버전마다 릴리스 노트를 4개 언어(한국어·English·日本語·简体中文)로 공개하고, 서비스 저장소 전부에 같은 git 태그(`vX.Y`)를 남깁니다. 첫 릴리스 전입니다.

## 지금 단계

문서 우선으로 진행하고 있습니다. 스펙 763개, 인수 테스트 1,096개, 화면 스토리보드 155장면, ERD, OpenAPI·AsyncAPI 명세를 마쳤고 첫 구현 마일스톤(M0)을 준비하고 있습니다.

<div align="center"><sub>Made at NHN Academy · data → flow</sub></div>
