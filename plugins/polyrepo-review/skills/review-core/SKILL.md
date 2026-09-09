---
name: review-core
description: Use when 여러 레포가 공유하는 PR 리뷰 절차를 실행할 때 — /cr, "코드 리뷰 해줘", "PR 리뷰", "머지 전 점검" 등의 요청 시.
---

# Review core

공통 리뷰 절차의 본문은 `${CLAUDE_PLUGIN_ROOT}/references/review-core.md` 에 있다. 그 파일을 읽고 따른다.
레포별 가변부(레이어 방향·도메인 룰 인덱스)는 호출 레포의 `AGENTS.md` 와 `.claude/rules/` 에서 읽는다.

이 스킬이 로드되었다면 출력 마지막에 `SKILL_LOADED = YES` 한 줄을 덧붙인다.
