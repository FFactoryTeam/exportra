# Exportra

Exportra는 공공 무역·산업 데이터와 AI를 활용하여 제조기업의 해외시장 진출 의사결정을 돕는 AI Export Copilot입니다.

> AI-powered export market intelligence platform for manufacturers.

## Overview

제조기업, 특히 중소 제조기업은 좋은 제품을 보유하고 있어도 해외시장 진출 과정에서 많은 어려움을 겪습니다.

어떤 국가가 유망한지, 제품에 맞는 HS코드는 무엇인지, 시장성·경쟁 강도·인증·규제·지원사업을 어디서 확인해야 하는지 판단하기 어렵습니다.

Exportra는 공공데이터와 AI를 활용하여 제조기업 담당자가 제품 정보를 입력하면 유망 수출국, HS코드 후보, 시장성 분석, 리스크, 인증 고려사항, 지원사업, 실행 로드맵을 한 번에 확인할 수 있도록 돕는 것을 목표로 합니다.

## Key Features

- 제품 및 기업 정보 입력
- 제품 설명 기반 HS코드 후보 추천
- 유망 수출국 TOP3 추천
- 국가별 시장성, 경쟁, 리스크 분석
- 인증 및 규제 체크포인트 정리
- 정부 지원사업 또는 수출지원 정보 추천
- 3개월 실행 로드맵 생성
- 공공데이터 활용 근거 표시
- AI 기반 분석 결과 요약

## Target Users

Exportra는 다음 사용자를 주요 대상으로 합니다.

- 해외 진출을 준비하는 중소 제조기업
- 수출 경험이 부족한 창업기업 또는 소규모 제조기업
- 지역 제조기업
- 제품은 있지만 해외시장 분석 경험이 부족한 기업
- 기업지원기관 또는 지자체 담당자

MVP에서는 “제품을 보유한 제조기업 담당자”를 핵심 사용자로 봅니다.

## How It Works

1. 사용자가 기업명, 소재 지역, 제품명, 제품 설명, 주요 특징, 희망 진출 지역 등을 입력합니다.
2. Exportra는 입력 정보를 바탕으로 제품 특성과 수출 가능성을 분석합니다.
3. 공공데이터와 AI 분석을 활용하여 유망 수출국 TOP3를 추천합니다.
4. 국가별 추천 이유, 시장성, 리스크, 인증 고려사항, 지원사업 정보를 제공합니다.
5. 사용자는 분석 결과와 3개월 실행 로드맵을 참고하여 다음 의사결정을 준비할 수 있습니다.

## Data Sources

Exportra는 공공 무역·산업 데이터를 역할별로 분리하여 활용합니다. 일부 데이터는 유망 수출국 추천 점수 계산에 직접 사용하고, 일부 데이터는 AI 리포트의 설명 근거로 사용합니다.

### Core Data

유망 수출국 TOP3 추천 점수 계산에 직접 활용하는 데이터입니다.

- 관세청 국가별 수출입실적 API: HS Code 기준 국가별 수출 규모와 성장성 분석
- 관세청 시도별 성질별 수출입실적 API: 지역별 수출 흐름과 품목 연관성 분석
- 한국무역보험공사 국가신용등급 데이터: 국가별 수출 리스크 반영

### Supporting Data

AI 리포트의 국가별 추천 이유, 인증 준비사항, 지원사업 추천, 실행 로드맵 생성에 활용하는 데이터입니다.

- KOTRA 국가정보 데이터: 국가별 시장환경과 진출 여건 설명
- KOTRA 해외인증정보 API: 국가·품목별 인증 준비사항 참고
- 기업마당 지원사업 API: 수출, 인증, 마케팅 관련 지원사업 추천
- KOTRA 수출바우처사업 모집공고: 수출 준비 단계별 지원사업 연결

### Regional & Expansion Data

지역 제조기업 분석과 전국 제조기업 확장을 위한 근거 데이터입니다.

- 공장등록현황 통계정보: 지역별·업종별 제조 기반 분석
- 관세청 시도별 성질별 수출입실적 API: 지역 수출 흐름 분석

자세한 데이터 활용 계획과 연동 우선순위는 `docs/product/DATA_SOURCES.md`에서 관리합니다.

## AI Usage Principles

Exportra의 AI는 최종 판단을 대신하지 않고, 사용자가 공공데이터를 더 쉽게 이해하고 비교할 수 있도록 돕는 보조 역할을 합니다.

- HS코드는 확정값이 아니라 후보로 제시합니다.
- 인증, 규제, 통관 정보는 참고용으로 제공하며 최종 확인이 필요합니다.
- 검증되지 않은 수치를 사실처럼 단정하지 않습니다.
- 공공데이터 기반 정보와 AI 생성 설명을 구분합니다.
- 실제 수출, 법률, 인증, 통관 의사결정은 전문가 또는 관련 기관 확인이 필요합니다.

## MVP Scope

초기 MVP는 공모전 시연과 오픈소스 확장을 모두 고려하여 작고 명확한 범위로 개발합니다.

포함할 기능:

- 제품/기업 정보 입력 화면
- 분석 요청 API
- OpenAI API 기반 분석 결과 생성
- 유망 수출국 TOP3 출력
- 국가별 분석 카드 출력
- 인증, 리스크, 지원사업, 로드맵 출력
- 공공데이터 활용 근거 표시
- 기본 실행 방법 문서화

초기 MVP에서 제외하는 기능:

- 회원가입/로그인
- 결제
- 관리자 페이지
- 복잡한 권한 관리
- 실시간 크롤링
- 모바일 앱
- 다국어 지원
- Redis
- Kubernetes
- MSA
- OAuth
- 대규모 데이터 파이프라인

## Tech Stack

Frontend:

- React 또는 Next.js
- TypeScript
- Tailwind CSS

Backend:

- Java
- Spring Boot
- Spring Web
- Spring Data JPA

Database:

- MySQL

AI:

- OpenAI API

Infrastructure:

- 로컬 실행 우선
- Docker Compose 선택 도입
- 이후 AWS EC2 배포 검토

## Documentation

문서는 다음 구조로 관리할 예정입니다.

```text
docs/
├── product/
│   ├── IA.md
│   ├── USER_FLOW.md
│   ├── SCREEN_SPEC.md
│   └── DATA_SOURCES.md
├── architecture/
│   ├── API_SPEC.md
│   ├── DB_SCHEMA.md
│   └── SYSTEM_ARCHITECTURE.md
├── contests/
│   ├── motie/
│   │   └── SUBMISSION_STRATEGY.md
│   └── oss/
│       └── OPEN_SOURCE_STRATEGY.md
└── team/
    └── ONBOARDING.md
```

## Team

FFactory는 Fail Fast 철학을 바탕으로 빠르게 만들고, 빠르게 검증하고, 빠르게 배우며 개선하는 개발 문화를 지향합니다.

> Fail Fast.

Team members:

- 김문기
- 반건우
- 하동현
- 전황준

## License

This project will be released under the MIT License.
