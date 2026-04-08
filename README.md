# AI 브랜치 프로젝트

> 신한은행 AI 브랜치 프로젝트 관리 저장소

## 프로젝트 개요

AI 기반 무인 은행 창구 시스템. LLM 에이전트를 활용하여 고객이 음성/터치로 은행 업무를 처리하는 서비스.

| 항목 | 내용 |
|------|------|
| 고객사 | 신한은행 |
| 파트너 | KT (봇프레임워크/SOE), 효성 (클라이언트/UI) |
| 운영 지점 | 서소문, 선릉 |
| Notion | [팀Projects/AI브랜치](https://www.notion.so/1263866c46d38083a8b4faea159ae407) |

---

## 서브 프로젝트

### 1. AICC 이행 (AI Contact Center)

무인 창구 핵심 업무(환전, 체크카드, 예적금, 청약, 증명서 등) 운영 이행.

| 항목 | 내용 |
|------|------|
| 현재 단계 | **운영 테스트 / 단계별 오픈** |
| 오픈 일정 | 체크카드 4/8 → 예적금/청약 4/9 → 선릉 확대 4/10 |
| 주요 이슈 | 서소문 운영 테스트 이슈 9건 조치 완료, 개선 보류 4건 다음 Phase |

→ [AICC 현황 대시보드](status/README.md)

### 2. 전세대출 PI (프로세스 개선)

전행 PI 관점에서 전세대출 업무 프로세스 개선. AI 창구(대면) + 슈퍼SOL(비대면) 양 채널.

| 항목 | 내용 |
|------|------|
| 현재 단계 | **PoC / 요건 정의** |
| 핵심 컨셉 | "AI 접수원" — 서류 필터링 + 상품 추천 + 상담 인계 |
| 일정 목표 | QA 6월 완료, 비대면 프로세스 9월 오픈 |

→ [전세대출 PI 현황](status/loan-pi.md)

---

## 디렉토리 구조

```
aibranch_project/
├── status/
│   ├── README.md                 # AICC 현황 대시보드
│   └── loan-pi.md                # 전세대출 PI 현황
├── docs/
│   ├── timeline.md               # 프로젝트 전체 타임라인
│   ├── requirements/
│   │   └── README.md             # AICC 요구사항 및 업무 범위
│   ├── decisions/
│   │   └── README.md             # 주요 의사결정 기록
│   └── meetings/
│       ├── _TEMPLATE.md          # 회의록 작성 템플릿
│       ├── YYYY-MM-DD-데일리.md  # AICC 데일리 회의록
│       ├── YYYY-MM-DD-주간.md    # 주간 회의록 (복합)
│       ├── YYYY-MM-DD-*PI*.md    # 전세대출 PI 회의록
│       └── archive/
│           └── 2025-meetings.md  # Notion 과거 회의 요약
├── meeting_stt/                  # 원본 STT 텍스트 (음성녹음)
└── README.md                     # 이 파일
```

## 빠른 링크

| 문서 | 설명 |
|------|------|
| [AICC 현황](status/README.md) | AICC 이행 상태, 이슈, 일정 |
| [전세대출 PI 현황](status/loan-pi.md) | 전세대출 PI 진행 현황 |
| [타임라인](docs/timeline.md) | 프로젝트 전체 히스토리 |
| [요구사항](docs/requirements/README.md) | AICC 업무 범위, 기능, 기술 구조 |
| [의사결정](docs/decisions/README.md) | 아키텍처/사업 주요 결정 |
| [회의록](docs/meetings/) | 데일리/주간/PI 회의록 |

## 운영 가이드

- **회의록 작성**: `docs/meetings/_TEMPLATE.md`를 복사하여 `YYYY-MM-DD-제목.md`로 저장
- **STT 원본**: `meeting_stt/YYYYMMDD_[type].txt`로 저장 (daily/weekly/loan 등)
- **현황 업데이트**: AICC → `status/README.md`, 전세대출 → `status/loan-pi.md`
