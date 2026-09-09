---
description: 플러그인이 호출 레포의 규칙 파일과 플러그인 내부 문서를 모두 읽을 수 있는지 검증하는 프로브
---

# Plugin capability probe

아래 6개 항목을 순서대로 수행하고, 결과를 `KEY = VALUE` 형태로 **한 줄씩만** 출력한다.
실패한 항목은 `KEY = FAIL: <이유>` 로 적는다. 그 외 설명·서론·요약은 쓰지 않는다.

1. `CWD` — Bash `pwd` 결과.
2. `ARGS` — 이 커맨드에 전달된 인자를 그대로 출력한다: $ARGUMENTS
3. `PROJECT_AGENTS` — 프로젝트 루트의 `AGENTS.md` 를 Read로 읽어 `PROBE_TOKEN_AGENTS` 값을 출력한다.
4. `PLUGIN_INTERNAL` — `${CLAUDE_PLUGIN_ROOT}/references/review-core.md` 를 Read로 읽어 `PROBE_TOKEN_PLUGIN` 값과 실제로 사용한 절대 경로를 함께 출력한다.
5. `AGENT_PROBE` — Agent 도구로 `probe-reviewer` 에이전트 1개를 띄우고, 그 에이전트가 반환한 문자열을 그대로 출력한다.
6. `PY_RULE` — `sample.py` 를 Read 한다. 그 직후 **네가 직접 Read하지 않았는데도** 파이썬 관련 규칙 내용이 컨텍스트에 주어졌다면 `AUTOINJECTED` 를, 주어지지 않았다면 `NOT_AUTOINJECTED` 를 출력한다.
