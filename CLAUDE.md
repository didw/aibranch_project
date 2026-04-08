# AI 브랜치 프로젝트 관리 가이드

## 프로젝트 개요

신한은행 AI 브랜치 프로젝트. 서브 프로젝트: **AICC 이행**, **전세대출 PI**. 상세 내용은 `README.md` 참고.

## 회의록 처리 워크플로우

사용자가 STT 파일(음성녹음 → 텍스트 변환 결과)을 제공하면 아래 순서로 처리한다.

### 1단계: STT 분석 및 회의록 작성

- 원본 STT: `meeting_stt/YYYYMMDD_[type].txt` (type: daily/weekly/loan 등)
- 출력: `docs/meetings/YYYY-MM-DD-제목.md`
- 템플릿: `docs/meetings/_TEMPLATE.md` 형식을 따름
- 회의록에 `분류` 태그 포함: AICC 이행, 전세대출 PI, 복합 등

STT 변환 시 주의사항:
- STT는 음성인식 결과로 오탈자, 고유명사 오인식이 많음. 문맥에 맞게 교정할 것
  - 예: "콩트" → "Conte", "단테" → "Dante", "폰트" → "Conte(폰트)" 등
  - 프로젝트 용어는 `docs/requirements/README.md`의 시스템 구조 참고
- "참석자 N" 형태의 화자 구분을 유지하되, 역할이 파악되면 (PM, 개발팀 등) 표기
- 논의 사항은 주제별로 그룹핑하여 간결하게 정리
- 액션 아이템은 반드시 담당/내용/기한을 추출
- 결정 사항은 명확히 분리하여 기록

### 2단계: 연관 문서 업데이트

회의록 작성 후, 회의 내용에 따라 아래 문서들을 함께 갱신한다.

| 문서 | 갱신 조건 | 갱신 내용 |
|------|-----------|-----------|
| `status/README.md` | AICC 관련 | 최종 업데이트 날짜, 주요 현황 테이블, 미해결 이슈, 일정, 최근 완료 항목 |
| `status/loan-pi.md` | 전세대출 관련 | 과제 현황, 의사결정, 일정 |
| `docs/decisions/README.md` | 새로운 의사결정이 있을 때 | 테이블에 행 추가 (일자/결정/배경/출처) |
| `docs/timeline.md` | 중요 마일스톤이 있을 때 | 해당 월 섹션에 항목 추가 |
| `docs/requirements/README.md` | 범위/요구사항 변경 시 | 업무 범위 테이블, 제약사항 등 갱신 |

### 3단계: 갱신 요약

처리 완료 후 사용자에게 아래 내용을 간결히 보고:
- 회의록 핵심 요약 (3줄 이내)
- 액션 아이템 수
- 함께 갱신한 문서 목록

## 디렉토리 구조

```
aibranch_project/
├── status/
│   ├── README.md                      # AICC 현황 대시보드
│   └── loan-pi.md                     # 전세대출 PI 현황
├── docs/
│   ├── timeline.md                    # 통합 타임라인
│   ├── requirements/README.md         # AICC 요구사항/범위
│   ├── decisions/README.md            # 의사결정 기록 (서브프로젝트 태그)
│   └── meetings/
│       ├── _TEMPLATE.md               # 회의록 템플릿
│       ├── YYYY-MM-DD-데일리.md       # AICC 데일리
│       ├── YYYY-MM-DD-주간.md         # 주간 (복합)
│       ├── YYYY-MM-DD-*PI*.md         # 전세대출 PI
│       └── archive/                   # 과거 회의 요약
├── meeting_stt/                       # 원본 STT (daily/weekly/loan)
└── CLAUDE.md                          # 이 파일
```

## 문서 작성 원칙

- **간결함 우선**: 불필요한 서술 없이 핵심만 기록
- **테이블 활용**: 현황, 이슈, 액션아이템은 테이블 형태로
- **상태 이모지**: ✅ 완료, 🔄 진행중, ⚠️ 주의, ❌ 불가
- **날짜 형식**: YYYY-MM-DD (파일명, 문서 내 모두)
- **링크 연결**: 문서 간 상대경로로 상호 참조

## 참고 자원

- Notion: [팀Projects/AI브랜치](https://www.notion.so/1263866c46d38083a8b4faea159ae407)
- Notion 회의록 DB: [회의록](https://www.notion.so/802759234235497aa7957c7cbb5eb2c7)
