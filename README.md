# na · 나

na는 나의 사고와 활동이 이어지는 개인 인지 환경이다. 기록과 도구를 나의 확장으로 바라보며, 불완전함과 실패도 보완하고 다시 참조할 재료로 남긴다.

이 저장소는 연구와 소프트웨어 개발이 함께 이루어지는 모노레포다. 현재 실행 가능한 앱은 없으며, TypeScript·pnpm·Node.js, Next.js·React, Turborepo를 기본 방향으로 채택했다. 운영은 집 서버의 Docker와 Tailscale을 사용한다. 소스와 이미지는 공개하며 이미지 레지스트리는 GHCR을 사용한다. 저장 방식과 정확한 도구 버전은 추가 연구 후 결정한다. 아직 도구 설치와 앱 생성은 하지 않았다.

첫 MVP는 **Memos의 제목 없는 Block 피드와 날짜 탐색을 바탕으로, Bullet Journal 방식의 수동 daily log를 남기고 다시 읽는 환경**이다.

## 현재 우선순위

다음 세션에서는 리서치와 사례 연구로 도메인·데이터 모델을 구체화한다. [다음 세션 안내](research/next-session.md)를 먼저 읽는다. [개발 기반 검증 5개](docs/tasks.md)는 미착수 후속 과제로 남겨둔다.

## 시작하기

- [워크스페이스 사용법](docs/workspace.md)
- [버전관리와 기여 방법](CONTRIBUTING.md)
- [개발 환경과 SDLC 기준안](docs/sdlc.md)
- [방향·용어·MVP 범위](docs/product.md)
- [결정 기록](docs/decisions/README.md)

```text
na/
├─ README.md
├─ CONTRIBUTING.md
├─ AGENTS.md
├─ docs/                 # 현재 합의와 운영 규칙
│  └─ decisions/         # 중요한 결정과 이유
├─ research/             # 출처·비교·열린 질문
├─ apps/                 # 실행·배포하는 앱
├─ packages/             # 재사용 라이브러리·공통 설정
└─ experiments/          # 작은 프로토타입과 검증 결과
```

설치·실행 방법은 구현되는 각 패키지의 README에 둔다. 실제 개인 로그·첨부파일·자격 증명은 이 저장소에 넣지 않는다.
