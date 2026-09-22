# 0002 — JavaScript 계열과 Turborepo 채택

날짜: 2026-09-22

상태: Next.js·React·Turborepo 및 TypeScript·pnpm·Node.js 채택. 세부 버전과 아래 후속 선택은 미확정.

## 맥락과 결정

사용자는 Next.js·React와 JavaScript 계열을 우선하고 Turborepo로 개발하기를 원한다. Vercel 생태계 도구를 우선 검토한다. Go·Python은 필요에 따라 부분 도입할 수 있다.

Turborepo를 모노레포 작업 조율 도구로 채택한다. `apps/`는 실행·배포 앱, `packages/`는 재사용 코드·설정으로 구분한다. 0001의 단일 저장소·연구 공존 원칙은 유지하며, 앱 위치와 빌드 도구 보류 부분을 이 결정으로 갱신한다.

## 역할과 추천안

Git은 이력, 패키지 관리자는 설치와 workspace, Turborepo는 작업 그래프와 캐시를 담당한다. Turbopack은 Next.js 앱의 번들러로 별개다.

후속 사용자 합의로 TypeScript, pnpm workspace, Node.js를 채택했다. 지원 LTS 버전 선택, Next.js App Router, Turbopack 세부 설정은 후속 확정한다. 도구 버전과 호환성은 실제 설치 전에 확인한다. 테스트·포매터·UI·에디터·저장 기술은 후속 연구한다.

## 대안과 결과

언어 중립적 폴더 구성만 유지하는 대신 JS 생태계 중심 개발 방향을 정한다. 처음부터 별도 Go/Python 서버를 만드는 것은 보류한다. 모든 컴포넌트를 JS로 강제하지는 않는다.

Vercel 도구 채택은 호스팅·원격 캐시·저장 서비스 채택을 뜻하지 않는다. 로컬 실행과 자체 호스팅 가능성을 유지하면서 배포와 데이터 위치를 별도로 정한다.

## 구현 상태

문서와 폴더 운영 규칙만 변경했다. package.json, turbo.json, workspace 설정, lockfile, 앱 코드, CI는 아직 생성하지 않았다.

## 공식 참고 자료

- [Turborepo 구조](https://turborepo.dev/docs/crafting-your-repository/structuring-a-repository)
- [패키지·작업 그래프](https://turborepo.dev/docs/core-concepts/package-and-task-graph)
- [라이브러리 배포와 Changesets](https://turborepo.dev/docs/guides/publishing-libraries)
- [Next.js Turbopack](https://nextjs.org/docs/app/api-reference/turbopack)
- [Next.js 자체 호스팅](https://nextjs.org/docs/app/guides/self-hosting)

확인일: 2026-09-22. 문서상의 기능을 확인했으며 로컬 실행 검증은 아직 하지 않았다.
