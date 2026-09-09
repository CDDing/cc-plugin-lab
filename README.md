# cc-plugin-lab

Claude Code 플러그인/마켓플레이스 동작을 검증하는 실험용 레포.

검증 대상:

1. 프로젝트 `.claude/settings.json` 의 `extraKnownMarketplaces` 로 마켓플레이스가 자동 등록되는가 (폴더 trust 필요)
2. `enabledPlugins` 만으로 플러그인이 설치되는가 (아니오 — `claude plugin install` 1회 필요)
3. 플러그인이 제공하는 커맨드/스킬/에이전트가 **호출 레포의** `AGENTS.md` · `.claude/rules/*.md` 를 읽을 수 있는가
4. `${CLAUDE_PLUGIN_ROOT}` 로 플러그인 내부 문서를 읽을 수 있는가
5. GitHub Actions(`claude-code-action`) 안에서 `plugin_marketplaces` + `plugins` 로 같은 플러그인이 동작하는가

`plugins/polyrepo-review` 는 실제 리뷰 로직이 아니라 위 항목을 출력으로 증명하는 프로브다.
