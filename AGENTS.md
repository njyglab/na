# na 작업 지침

- 루트 README와 관련 문서를 먼저 읽는다. 하위 AGENTS.md가 있으면 함께 따른다.
- 현재 제품 범위와 용어는 `docs/product.md`, 폴더 운영은 `docs/workspace.md`, Git 흐름은 `CONTRIBUTING.md`를 따른다.
- 수동 daily log를 우선한다. Block에 제목·태그·분류를 필수로 요구하지 않는다. Bullet Journal을 할 일 관리로만 축소하지 않는다.
- 미래 구상과 연구 가설을 확정 요구사항으로 취급하지 않는다. 애매한 용어는 확인한다.
- JavaScript 계열, Next.js·React, Turborepo는 채택했다. 세부 기준은 `docs/decisions/0002-js-turborepo.md`를 따른다. TypeScript·pnpm·Node.js도 채택했다. 집 서버 Docker·Tailscale 운영과 온라인 전용 첫 MVP는 합의했다. 저장 방식은 미정이다. SDLC 기준안은 `docs/sdlc.md`를 참조한다. 설치와 앱 생성 전 실행 계획을 합의한다.
- 관련 없는 인접 프로젝트의 관례를 자동으로 가져오지 않는다.
- 변경 전에 Git 상태를 확인하고 기존 작업을 보존한다. 개인 데이터와 자격 증명은 커밋하지 않는다.
- 수동 기록·자동 관측·도구 생성 내용을 구별하고, 원본과 파생 결과의 출처를 보존한다.
- 중요한 결정과 실패의 이유를 남기되 모든 작업에 보고서를 요구하지 않는다.
- 필요한 범위만 검증하고 실제 수행한 검증과 남은 한계를 보고한다.
