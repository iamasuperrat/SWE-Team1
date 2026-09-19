# HARNESS.md — why this repo is set up this way

## What's here and why

- **`AGENTS.md`** is the single source of truth for how agents should work in this repo. `CLAUDE.md` just points to it, so the rules never live in two places that could drift apart.
- **Verification:** 아직 테스트 커맨드가 없습니다 (스택 미정). 스택이 정해지면 AGENTS.md의 표를 채우고, 그때부터는 그 커맨드가 통과해야 변경이 완료된 것으로 간주합니다. CI는 아직 없음 — 스택이 정해지면 `verify.yml` 같은 최소 워크플로(lint+test on PR) 추가를 권장합니다.
- **Danger zone:** force-push, 공유/보호 브랜치 직접 push, `.env`/시크릿 수정, CI·권한 설정 변경 등은 자율 세션 중에도 사람의 확인이 필요합니다 — 되돌리기 어렵기 때문입니다.
- **Handoff:** PR 설명에 무엇을/왜 했는지 남기고, 진행 중인 결정/이슈는 파일로 기록합니다 (아래 참고).
- **Multi-agent:** 5명이 병렬로 다른 기능을 작업하는 팀이라, 충돌을 "기억해서 피하는 것"이 아니라 구조적으로 막기 위해 아래 파일-단위 규칙을 씁니다.
- **결정과 열린 이슈는 항목당 파일 하나씩**, `docs/decisions/`와 `docs/status-defects/`에 저장합니다 — 공유 테이블이 아닙니다. 같은 주에 두 사람이 같은 테이블을 고치는 것이 바로 시간 압박 속에서 잘못 풀리는 충돌 유형이기 때문입니다. 새 파일은 다른 것과 충돌할 수 없습니다.
- **문서도 코드처럼 감사합니다:** 각 결정 파일은 자신이 어떤 다른 문서를 낡게 만드는지 명시해서, "문서 업데이트하는 거 기억하기"가 희망이 아니라 체크리스트 항목이 되게 합니다.
- **`python scripts/status.py`**는 열린 이슈, 최근 결정, 최근 커밋, 커밋 안 된 변경사항을 한 화면에 보여줍니다 — "지금 상태가 어떤지" 볼 때 여기 하나만 보면 됩니다.

## Self-check

가끔, 특히 새 팀원을 온보딩하기 전에 아래를 확인하세요:

- [ ] AGENTS.md가 아직 정확한가, 아니면 프로젝트가 거기 적힌 내용에서 벗어났는가?
- [ ] AGENTS.md의 build/test/verify 커맨드가 실제로 작동하는가? (스택이 정해진 뒤)
- [ ] danger-zone 목록이 적당한 길이인가 — 너무 길어서 아무도 안 읽지도, 실제로 위험해진 항목이 빠지지도 않았는가?
- [ ] 새로운 기여자(사람이든 에이전트든)가 진행 중인 작업의 맥락을 어디서 찾을지 알 수 있는가?
- [ ] 결정/열린 이슈가 여전히 항목당 파일 하나로 유지되고 있는가, 아니면 공유 테이블로 다시 돌아갔는가?
- [ ] 최근 결정 파일들의 "Canon updates"가 실제로 바뀐 내용과 일치하는가?
