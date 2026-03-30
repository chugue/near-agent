# NEAR AI Career Agent Platform

## What This Is

NEAR 블록체인 기반 AI 커리어 에이전트 플랫폼. 구직자가 GitHub, Slack, Discord, 정부24 등을 연동하면 AI가 자동으로 이력 데이터를 수집·분석하여 이력서를 생성·최신화하고, 잡 마켓에서 매칭된 채용공고에 대해 AI 에이전트가 구직자/채용측 양방향으로 연봉·조건 협상을 수행한다. NEAR AI Cloud TEE 환경에서 에이전트가 실행되며, 토큰 결제로 이력서 열람 권한을 관리한다.

## Core Value

"나의 커리어를 자동으로 관리하고, 대신 팔아주고, 협상까지 해주는 AI 에이전트" — 사용자는 계정만 연동하면 AI가 이력서 생성·최신화·매칭·협상을 모두 대행한다.

## Requirements

### Validated

(None yet — ship to validate)

### Active

- [ ] NEAR AI Cloud TEE 환경 세팅 및 API 연동
- [ ] 이력서 분석/업데이트 프롬프트 설계
- [ ] 협상 에이전트 프롬프트 설계 (구직자측 + 채용측)
- [ ] 에이전트 입출력 테스트 (이력서 데이터 → 정상 업데이트 확인)
- [ ] 벡터 임베딩 (Qwen3-Embedding) API 연동
- [ ] 리랭킹 (Qwen3-Reranker) API 연동
- [ ] 협상 플로우 구현 (채용조건 → 구직자 에이전트 → 리턴 → 반복)
- [ ] 최대 라운드 정의 및 관리 로직
- [ ] 협상 히스토리 저장/조회 API
- [ ] NEAR 지갑 로그인 (구직자 + 채용담당자)
- [ ] OAuth 연동 (Slack, Discord, GitHub)
- [ ] 이력서 PDF 업로드 + 텍스트 추출
- [ ] 이력서 DB 저장 및 에이전트 결과 반영
- [ ] DB 스키마 설계 (전체)
- [ ] 채용공고 CRUD (업로드, 연봉테이블, 복지 입력)
- [ ] 매칭 로직 (임베딩 유사도 기반 랭킹)
- [ ] 토큰 결제 연동 (지갑 → 결제 → 이력서 열람 권한)

### Out of Scope

- 프론트엔드 구현 — 파트 E 담당자가 별도 진행
- 모바일 앱 — 웹 우선
- 실시간 채팅 — v1 범위 외

## Context

- **팀 구성:** 5명 (A: AI Agent, B: 협상 백엔드, C: 써드파티/회원/이력서, D: 매칭/토큰/채용공고, E: 프론트엔드)
- **본인 역할:** 백엔드 전체 담당, 우선순위 1순위는 파트 A (AI Agent 인프라 + 프롬프트)
- **기술 스택:** NestJS (이미 /backend에 초기화), NEAR AI Cloud TEE, Qwen3-Embedding, Qwen3-Reranker
- **해커톤 프로젝트:** 3주 개발 일정 (Week 1: 기반, Week 2: 핵심, Week 3: 통합)
- **의존관계:** A(에이전트 API) → D(매칭), B(협상) / C(DB + OAuth) → D, B
- **써드파티 연동:** GitHub, Slack, Discord, 정부24 → AI가 이력 데이터 자동 수집
- **NEAR 참고 문서:** https://docs.near.org/getting-started/hackathons

## Constraints

- **Timeline**: 3주 해커톤 일정 — 빠른 MVP 필요
- **Tech Stack**: NestJS 백엔드, NEAR 블록체인, NEAR AI Cloud TEE
- **AI Models**: Qwen3-Embedding (벡터 임베딩), Qwen3-Reranker (리랭킹)
- **Priority**: 파트 A 먼저 구현 후 B/C/D 순차 진행

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| NestJS 백엔드 | 이미 초기화 완료, TypeScript 기반 | — Pending |
| NEAR AI Cloud TEE 사용 | 해커톤 요구사항, 신뢰 실행 환경 | — Pending |
| Qwen3 모델군 사용 | 임베딩 + 리랭킹 통합 | — Pending |

## Undefined Items

- 협상 최대 라운드 수
- 재시도 최대 횟수
- 토큰 결제 금액

---
*Last updated: 2026-03-31 after initialization*
