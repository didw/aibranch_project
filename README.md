# AI 브랜치 프로젝트

> 신한은행 AI 브랜치 AICC(AI Contact Center) 프로젝트 관리 저장소

## 프로젝트 개요

AI 기반 무인 은행 창구 시스템. LLM 에이전트를 활용하여 고객이 음성/터치로 은행 업무(입출금, 체크카드, 증명서 등)를 처리하는 서비스.

| 항목 | 내용 |
|------|------|
| 고객사 | 신한은행 |
| 파트너 | KT (봇프레임워크/SOE), 효성 (클라이언트/UI) |
| 운영 지점 | 서소문, 신림동 |
| 현재 단계 | **이행 준비** (4/2 운영 이행 예정) |
| Notion | [팀Projects/AI브랜치](https://www.notion.so/1263866c46d38083a8b4faea159ae407) |

## 디렉토리 구조

```
aibranch_project/
├── status/
│   └── README.md                 # 프로젝트 현황 대시보드
├── docs/
│   ├── timeline.md               # 프로젝트 전체 타임라인
│   ├── requirements/
│   │   └── README.md             # 요구사항 및 업무 범위
│   ├── decisions/
│   │   └── README.md             # 주요 의사결정 기록
│   └── meetings/
│       ├── _TEMPLATE.md          # 회의록 작성 템플릿
│       ├── YYYY-MM-DD-제목.md    # 개별 회의록
│       └── archive/
│           └── 2025-meetings.md  # Notion 과거 회의 요약
├── meeting_stt/                  # 원본 STT 텍스트 (음성녹음)
└── README.md                     # 이 파일
```

## 빠른 링크

| 문서 | 설명 |
|------|------|
| [현황 대시보드](status/README.md) | 현재 상태, 이슈, 다가오는 일정 |
| [타임라인](docs/timeline.md) | 프로젝트 전체 히스토리 |
| [요구사항](docs/requirements/README.md) | 업무 범위, 기능 목록, 기술 구조 |
| [의사결정](docs/decisions/README.md) | 아키텍처/사업 주요 결정 |
| [최신 회의록](docs/meetings/) | 데일리/주간 회의록 |
| [과거 회의 요약](docs/meetings/archive/2025-meetings.md) | Notion 기반 과거 회의 정리 |

## 운영 가이드

- **회의록 작성**: `docs/meetings/_TEMPLATE.md`를 복사하여 `YYYY-MM-DD-제목.md`로 저장
- **STT 원본**: `meeting_stt/YYYYMMDD.txt`로 저장 (Clova Note 등 STT 결과)
- **현황 업데이트**: 주요 변경 시 `status/README.md` 상단 테이블 갱신
