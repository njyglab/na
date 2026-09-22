# na · 나

na는 나의 사고와 활동이 이어지는 개인 인지 환경이다. 기록과 도구를 나의 확장으로 바라보며, 불완전함과 실패도 보완하고 다시 참조할 재료로 남긴다.

이 저장소는 연구와 소프트웨어 개발이 함께 이루어지는 모노레포다. 현재 실행 가능한 앱은 없으며, 언어·기술 스택·패키지 관리·저장·배포 방식은 추가 연구 후 결정한다.

첫 MVP는 **Memos의 제목 없는 Block 피드와 날짜 탐색을 바탕으로, Bullet Journal 방식의 수동 daily log를 남기고 다시 읽는 환경**이다.

## 시작하기

- [워크스페이스 사용법](docs/workspace.md)
- [버전관리와 기여 방법](CONTRIBUTING.md)
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
├─ packages/             # 실제 앱·라이브러리·도구
└─ experiments/          # 작은 프로토타입과 검증 결과
```

설치·실행 방법은 구현되는 각 패키지의 README에 둔다. 실제 개인 로그·첨부파일·자격 증명은 이 저장소에 넣지 않는다.
