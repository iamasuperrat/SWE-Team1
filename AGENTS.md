# AGENTS.md

## Project

성균관대학교 학생들의 캠퍼스 생활을 돕는 AI 에이전트를 만드는 팀 프로젝트입니다. 구체적인 기능 범위와 아키텍처는 아직 확정되지 않았습니다.

## Stack

TBD — 아직 언어/프레임워크가 정해지지 않았습니다. 정해지는 대로 이 섹션과 아래 표를 실제 명령어로 채워주세요.

## Setup

```
# TBD: 스택이 정해지면 fresh clone → 실행까지의 명령어를 여기에 채우세요.
```

## Build, run, and verify

| Task | Command |
|---|---|
| Run the app | TBD |
| Run tests | TBD |
| Lint / format | TBD |
| Type-check (if applicable) | TBD |

아직 테스트/빌드 커맨드가 없습니다. 스택을 정하는 사람이 이 표를 채우고, 그 다음부터는 **이 커맨드가 통과해야 작업이 끝난 것**으로 간주합니다.

## Code conventions

아직 정해진 컨벤션 없음. 스택이 정해지면 린터/포매터 설정과 함께 여기에 추가하세요 (린터가 이미 잡아주는 규칙은 여기 다시 적지 않기).

## Permissions / danger zone

다음 항목은 자율 세션 중이라도 사람의 명시적 확인이 필요합니다:

- Force-push, 또는 공유 브랜치의 히스토리 재작성
- 다른 사람이 쓰고 있는 브랜치 삭제
- `.env`, credentials, 시크릿 관련 파일을 읽거나 수정하거나 커밋하는 것
- CI 설정이나 저장소 권한 변경
- `main` 브랜치에 직접 병합하거나 push
- 이 파일, 어댑터 파일, 훅 스크립트에 시크릿/API 키를 커밋하는 것

## Branches

5명이 동시에 다른 기능을 작업하므로, 각자 기능 브랜치(`<이름>/<기능>` 형식 권장)에서 작업하고 PR로 `main`에 병합합니다. `main`은 보호 브랜치로 취급하고 직접 push하지 않습니다.

## Handoff

작업을 넘길 때는 PR 설명에 무엇을/왜 했는지 남기세요. 진행 중인 결정/이슈는 아래 Repo map에 설명된 대로 `docs/decisions/`, `docs/status-defects/`에 파일 단위로 기록합니다.

**Status line format:** `<phase> · <지금 구체적으로 하고 있는 작업> · <관련 이슈/결정 파일>`
Good: `Phase 0 · 캠퍼스 지도 API 스펙 조사 중 · docs/decisions/2026-09-19-map-api.md`
Bad: `Phase 0 · 진행중`

## Multi-agent notes

5명이 서로 다른 기능을 동시에 작업합니다. 같은 파일/영역을 동시에 건드릴 가능성이 있으면 미리 팀 채널에 알리세요. 충돌 방지를 위한 세부 구조는 아래 Repo map을 참고하세요.

## Repo map

- **결정(decisions):** 결정 하나당 파일 하나, `docs/decisions/`에 저장 (표나 공유 로그에 추가하지 않기 — 템플릿은 `docs/decisions/TEMPLATE.md`).
- **열린 이슈(open issues):** 이슈 하나당 파일 하나, `docs/status-defects/`에 저장 (템플릿은 `docs/status-defects/TEMPLATE.md`).
- **한눈에 현황 보기:** `python scripts/status.py` — 열린 이슈, 최근 결정, 최근 커밋, 커밋 안 된 변경사항을 한 화면에 보여줍니다.
