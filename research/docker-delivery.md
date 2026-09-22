# Docker 자체 호스팅과 CI/CD 검토

확인일: 2026-09-22. 공식 README와 구성 파일을 확인했으며 실제 컨테이너 실행·복구는 검증하지 않았다. 후속 사용자 합의로 집 서버 Docker 운영과 Tailscale 접속이 확정되었다. CI/CD 세부 구성은 [SDLC 기준안](../docs/sdlc.md)에서 관리한다.

## 사용자 의도

개발에는 TypeScript·pnpm·Node.js, Next.js·React, Turborepo를 사용한다. Vercel 생태계에 대한 선호는 개발 경험과 에이전트·스킬 통합성에 관한 것이며, Vercel 호스팅 확정이 아니다. Anchor와 Memos 같은 Docker 자체 호스팅에 긍정적이다.

## 관측

- [Anchor README](https://github.com/zhfahim/anchor): GHCR의 사전 빌드 이미지, Compose, `/data` 영속 볼륨을 안내한다. 오프라인 저장과 온라인 동기화는 앱 기능이다.
- [Anchor Dockerfile](https://github.com/zhfahim/anchor/blob/main/Dockerfile): Next.js standalone 웹, Nest API, PostgreSQL을 하나의 실행 이미지에 담고 supervisor로 관리한다. 다단계 빌드를 사용한다. 설치가 간단한 표면 뒤에 여러 프로세스가 있다.
- [Memos README](https://github.com/usememos/memos): 사전 빌드 이미지의 5230 포트와 호스트 폴더를 `/var/opt/memos`에 마운트하는 실행 예시를 제공한다. 이 조사에서 Memos의 내부 Dockerfile이나 DB 구성까지 검증하지는 않았다.
- [Next.js 자체 호스팅](https://nextjs.org/docs/app/guides/self-hosting): Node.js·Docker 기반 운영 경로를 지원한다.
- [GitHub 이미지 게시](https://docs.github.com/en/actions/tutorials/publish-packages/publish-docker-images): Actions에서 컨테이너 이미지를 빌드하고 레지스트리에 게시하는 흐름을 제공한다.

## na에 대한 제안

개발은 로컬 Node.js·pnpm, 배포 산출물은 Docker 이미지로 분리한다. 처음에는 하나의 Next.js 앱을 우선하고 별도 API 서비스·DB 서버 필요성은 데이터 요구로 판단한다. Anchor의 단일 컨테이너 내부 구성을 그대로 복제할 필요는 없다.

CI 제안: GitHub Actions에서 고정된 Node/pnpm 환경과 frozen lockfile 설치, 타입·정적 검사, 의미 있는 테스트, 빌드 검증. 브라우저의 실제 기록·재방문 흐름은 Playwright 후보로 검증한다. 테스트 도구는 미확정이다.

배포 흐름 제안: 검증 통과 → 커밋 SHA와 릴리스 버전으로 식별한 이미지 → GHCR 게시 → 운영자가 선택한 버전을 Compose로 업데이트. 초기에는 자동 게시와 수동 운영 반영을 분리한다. CI의 테스트 데이터와 운영 데이터를 분리한다.

컨테이너 교체와 데이터 보존은 분리한다. 볼륨은 백업이 아니며, 실행 중 DB 파일 단순 복사는 일관된 백업을 보장하지 않는다. 저장 기술에 맞는 백업·복원과 스키마 변경 절차를 정한다. 이미지 롤백이 데이터 마이그레이션을 되돌려 주지는 않는다.

## 초기 조사 질문과 후속 답변

1. 첫 사용 기기와 실행 장소: 노트북 자체, 상시 켜진 집 서버, VPS 중 무엇인가?
2. 외부에서 스마트폰 접근이 필요한가? 네트워크 없이 작성도 첫 MVP에 필요한가?
3. 개인 전용인가, 다른 사람도 계정을 갖는가? 인터넷 공개 범위는 어디까지인가?
4. 보존하려는 데이터 형식과 허용 가능한 유실량, 백업 장소는 무엇인가?

후속 답변: 노트북 검증 후 집 서버 Docker 운영, Tailscale 접속, 온라인 전용·개인 사용자 우선, 서버 영속 데이터가 원본. 파일/SQL 선택과 백업 정책은 미정이다. Docker 자체 호스팅과 오프라인 우선 설계는 별개의 선택이다.
