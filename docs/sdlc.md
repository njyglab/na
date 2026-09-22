# 개발 환경과 SDLC 기준안

작성일: 2026-09-22. 사용자가 확정한 조건과 이번 운영 추천을 구별한다. 이 문서는 실행 계획이며 도구 설정이나 CI 실행 완료를 의미하지 않는다.

## 확정 조건

- TypeScript·pnpm·Node.js, Next.js·React, Turborepo.
- 노트북에서 개발과 실행 검증 후 집의 상시 가동 데스크톱 서버에서 Docker로 운영.
- 기기는 기존 Tailscale 네트워크로 서버에 접속.
- 소스와 컨테이너 이미지는 공개하며 이미지 레지스트리는 GHCR을 사용한다. 실제 원격 공개 설정은 별도 확인한다.
- 초기 이미지 타깃은 노트북과 서버에 맞춘 `linux/amd64`다.
- 첫 MVP는 온라인 전용·개인 사용자. 다중 계정과 공유는 미래 요구로 고려.
- 서버의 영속 데이터가 원본. 컨테이너의 삭제 가능한 쓰기 계층에 원본을 두지 않는다.
- 파일 기반 또는 SQL 기반 저장 선택은 미정. 오프라인 저장·동기화는 후속 연구.

## 환경 분리

| 환경 | 위치·역할 | 데이터 |
| --- | --- | --- |
| 개발 | 노트북의 Node/pnpm, 빠른 수정 확인 | 가상 데이터 |
| CI | GitHub-hosted runner 추천, 깨끗한 환경에서 검증 | 일회성 가상 데이터 |
| 배포 전 검증 | 노트북 Docker, 이후 집 서버의 별도 Compose 프로젝트 | 운영과 분리된 볼륨·포트 |
| 운영 | 집 서버 Docker Compose | 서버 영속 원본과 별도 백업 |

상시 staging 서버는 처음부터 요구하지 않는다. 임시 검증 인스턴스로 시작한다. 서버에서 소스를 다시 빌드하기보다 검증한 동일 이미지 digest를 운영에 반영한다. 집 서버를 CI runner로 사용하는 구성은 초기 범위 밖이다.

## 추천 도구 조합

- Node.js: 24 LTS 계열. 정확한 패치는 설정 시 지원·보안 상태를 확인하고 개발·CI·이미지에 맞춘다.
- pnpm: 현재 11 계열 환경을 기준으로 Next/Turbo와 호환성을 검증하고 정확한 버전을 packageManager에 고정한다.
- Next.js App Router, Turbopack: 첫 웹 앱의 추천 구성. 도구 버전은 스캐폴딩 시 함께 검증한다.
- ESLint + Prettier: 코드 규칙과 문서·코드 포맷을 분담하는 추천 구성.
- Vitest: 로직 테스트. Playwright: 실제 브라우저의 핵심 사용자 흐름. 코드가 생길 때 적용한다.
- GitHub Actions: CI. GHCR: 컨테이너 이미지 보관. Docker Buildx: 이미지 빌드.
- Docker Compose: 노트북 검증과 집 서버 운영.
- Tailscale Serve: tailnet 내부 HTTPS 접근을 위한 추천 경로. 기존 서버 설정 확인 후 선택한다.

개발 컨테이너·Kubernetes·별도 배포 관리 서비스·원격 Turbo 캐시는 초기 필수 도구로 추가하지 않는다. 설정과 유지 비용이 필요한 만큼만 도구를 도입한다.

## 모노레포 구성

`apps/web/`은 첫 웹 앱의 예정 위치다. `packages/`는 실제 공유 코드·설정만 담는다. pnpm workspace는 `apps/*`, `packages/*`를 대상으로 한다. 연구와 실험은 자동으로 제품 빌드에 포함하지 않는다.

초기 설정 파일: 루트 package.json(private, packageManager, 도구 의존성), pnpm-workspace.yaml, pnpm-lock.yaml, turbo.json. Node 버전은 기존 mise 사용을 고려하여 고정 위치를 정한다. CI와 Docker에서 다른 버전을 쓰지 않도록 검증한다.

표준 명령의 목표: dev, build, lint, typecheck, test, test:e2e, format:check. 실제 작업은 패키지에 두고 루트는 turbo run으로 위임한다. 문서 검사처럼 본질적으로 저장소 전체인 작업만 루트 예외로 둔다. 아직 없는 테스트를 통과시키는 빈 명령은 만들지 않는다.

Dockerfile은 앱 가까이 두되 모노레포 루트를 빌드 context로 사용한다. Compose와 운영 안내는 실제 설정 생성 시 deploy/에 둔다. workflows는 .github/workflows/에 둔다. 현재 이 파일들은 아직 없다.

## 변경부터 운영까지

1. 짧은 브랜치에서 구현한다. 문제·의도·완료 조건은 PR이나 관련 연구 문서에 적는다.
2. 로컬에서 해당 변경에 필요한 검증을 실행한다.
3. PR과 main push에서 CI를 수행한다. frozen lockfile 설치 → 포맷·정적 검사·타입 검사·필요한 테스트·빌드. 초기 규모에서는 전체 검사하고 필요해지면 변경 영향 범위를 좁힌다.
4. 브라우저 흐름이 생기면 서버를 실행해 Playwright로 확인한다. 실제 운영 데이터나 서버 접속은 사용하지 않는다.
5. main의 선택한 커밋에 대해 릴리스 태그 또는 수동 실행으로 이미지를 만든다. 해당 커밋의 검증 통과를 확인하고 컨테이너 기동 검사 후 GHCR에 게시한다. PR에서는 게시 권한을 주지 않는다.
6. 이미지에 commit SHA와 릴리스 버전을 연결하고 실제 배포는 digest로 고정한다. 같은 이미지를 노트북과 서버 검증 인스턴스에서 확인한다.
7. 필요 백업·마이그레이션을 확인하고 운영 Compose의 이미지 참조를 수동 업데이트한다. 가동 상태와 핵심 기능을 확인한다.
8. 장애 시 이전 이미지와 데이터 호환성을 확인해 복구한다. 이미지 롤백은 DB 변경을 자동 복구하지 않는다.

첫 단계의 CD는 배포 가능한 산출물을 제공하는 수준이다. 매 커밋의 운영 자동 반영은 하지 않는다. 앱 릴리스 식별과 npm 라이브러리 배포는 구별하며 Changesets는 후자를 필요로 할 때 도입한다.

## CI와 운영 경계

CI는 읽기 권한을 기본으로 하고 이미지 게시 작업만 필요한 패키지 쓰기 권한을 갖는다. 외부 Actions는 전체 commit SHA로 고정하고 업데이트 PR로 관리한다. 처음부터 서버 SSH/Tailscale 자격 증명을 CI에 제공할 필요는 없다.

추천 접근 경로는 휴대폰 → Tailscale Serve HTTPS → 서버 loopback에 게시한 앱 포트 → 컨테이너다. 실제 ACL과 Serve 사용 가능 여부는 확인 전이다. Tailscale 접속 제어와 앱 계정·권한은 별개이며 앱 인증 생략을 확정한 것은 아니다.

운영 로그와 health endpoint를 우선 관측 수단으로 삼는다. 원문 메모와 비밀값을 로그에 남기지 않는다. 백업 방식·주기·복원 검증은 저장 기술 선택 시 정의하며, 실제 개인 데이터를 넣기 전에 검증한다.

## 현재 확인한 노트북 환경

2026-09-22 CLI 확인: Linux x86_64, Node v24.20.0, pnpm 11.20.0, Docker 29.8.0, Compose 5.5.1. node와 pnpm은 mise shim 경로로 발견했다. 버전 출력만 확인했으며 Docker daemon 접근·이미지 빌드·집 서버 실행은 검증하지 않았다. 현재 관측 버전과 최종 프로젝트 고정 버전은 구별한다.

## 집 서버 환경과 준비

사용자 제공 정보(원격 확인 전): Ubuntu 22.04.5 LTS x86_64, AMD Ryzen 5 7500F, B650M PG Lightning. Docker는 설치되어 있고 Compose는 없다. 기존 reverse proxy는 없는 것으로 본다. 노트북·서버·휴대폰은 동일 tailnet에서 가상 IP로 상호 접근 가능하다.

이미지는 `linux/amd64`부터 제공한다. 서버에는 Docker Engine과 Compose 플러그인이 필요하며 앱 실행을 위한 Node.js·pnpm의 호스트 설치는 필요하지 않다.

Compose는 서버의 기존 Docker 설치 출처를 확인한 후 그에 맞춰 설치한다. Docker 공식 apt 저장소가 설정되어 있다면 공식 안내의 `sudo apt-get update`, `sudo apt-get install docker-compose-plugin`을 사용하고 `docker compose version`으로 확인한다. 기존 Docker 설치를 무조건 교체하지 않는다. 서버 설치는 아직 수행하지 않았다.

초기 가상 IP와 포트로 연결을 확인할 수 있다. 운영 HTTPS는 Tailscale Serve를 추천하지만 활성화하지 않았다. IP 접속 방식에서는 tailnet 인터페이스 접근을 설정해야 하며, Serve 방식의 loopback 바인딩과 혼동하지 않는다. 공개 인터넷 서비스를 만드는 Tailscale Funnel은 현재 범위 밖이다.

## 공개 배포

GHCR 이미지 경로 제안: `ghcr.io/njyglab/na-web`. 아직 패키지를 생성하거나 게시하지 않았다. 저장소 공개와 패키지 공개는 별도 확인한다. GHCR은 첫 게시의 기본 공개 범위가 private이므로 첫 게시 후 public으로 전환하고 익명 pull을 확인한다. 공개 이미지 pull에는 서버의 레지스트리 로그인 토큰이 필요하지 않다.

CI 게시에는 저장소의 GITHUB_TOKEN과 필요한 packages:write 권한을 사용한다. 이미지에는 소스 저장소와 revision 메타데이터를 연결한다. 공개 소스의 라이선스는 별도 미결정이며 공개 여부만으로 재사용 조건이 정해지는 것은 아니다.

## 공식 참고

- [Next.js 테스트 도구](https://nextjs.org/docs/app/guides/testing)
- [Node.js 릴리스](https://nodejs.org/en/about/previous-releases)
- [pnpm 11 안내](https://github.com/pnpm/pnpm.io/blob/main/blog/releases/11.0.md)
- [GitHub Actions 권한·SHA 고정](https://docs.github.com/en/actions/reference/security/secure-use)
- [이미지 게시](https://docs.github.com/en/actions/tutorials/publish-packages/publish-docker-images)
- [Tailscale Serve](https://tailscale.com/docs/features/tailscale-serve)

- [Compose 플러그인 설치](https://docs.docker.com/compose/install/linux/)
- [GHCR 공개·인증·digest](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry)
