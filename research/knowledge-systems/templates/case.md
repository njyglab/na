# 사례 조사 템플릿

이 파일을 복사해 `cases/<case-id>.md`로 작성한다. 빈칸을 추정으로 채우지 않는다. 첫 패스는 사례 기술과 핵심 근거만 작성하고, deep dive에서 네 층 분석을 확장한다. 모든 capability를 조사해야 사례 기술을 시작할 수 있는 것은 아니다.

## 0. 대상과 경계

- 사례명 / case-id:
- 종류: 소프트웨어 / 방법론 / 역사적 실천 / 개념·명세
- 범위: 제품 버전·설정·플러그인 / 역사적 시기·자료군 / 방법론 판본
- 조사일 / 조사자:
- 상태: 미착수 / 기술 중 / 근거 검토 중 / 비교 가능
- 당사자 용어와 연구자 용어의 차이:
- 직접 확인한 자료·실행 범위:
- 이번 조사에서 다루지 않은 범위:

## 1. Case description — 사례 자체를 먼저 기술

| 항목 | 사례 자체의 기술 | 근거 ID | 상태·한계 |
|---|---|---|---|
| Problem / failure mode | | | 미확인 |
| Primitive: 내용·식별·UI·저장 단위 | | | 미확인 |
| Core Operations | | | 미확인 |
| Temporality | | | 미확인 |
| Organization timing/cost | | | 미확인 |
| Retrieval / entry points | | | 미확인 |
| Human burden | | | 미확인 |
| Evidence/source quality | | | 미확인 |

### 사용자의 10분 행동 서술

출발 상황 → 실제 행동 → 시스템/종이의 변화 → 사용자가 판단한 것 → 다시 찾거나 사용한 결과.

실행 관찰 / 문헌상 재구성 / 제안 시나리오 중 무엇인지 표시한다. 역사 사례에서 관찰하지 못한 사용 장면을 사실처럼 재현하지 않는다.

## 2. 근거 장부

### 자료 목록

| Source ID | 제목·저자/기관 | URL 또는 보존 위치 | 유형·판본·날짜 | 열람일 | 정확한 위치·접근 한계 |
|---|---|---|---|---|---|
| S01 | | | 원자료/당사자/공식/학술/후대 | | |

### 주장 목록

| Claim ID | 한 가지 검증 가능한 주장 | 상태 | Source ID·위치 | 근거와 한계 / 대안 해석 |
|---|---|---|---|---|
| C01 | | 확인된 사실/해석/미확인 | | |

확인된 사실은 ‘공식 문서가 X라고 설명한다’와 ‘실행해 X가 동작했다’를 구분한다. 짧은 인용, 요약, 연구자 해석을 섞지 않는다. 원문 미열람 상태에서 검색 요약만으로 확인 처리하지 않는다. 자료가 충돌하면 각각의 시기·범위와 미해결 지점을 남긴다.

## 3. Knowledge — fit 분석

| 지식 성질·실제 예시 | 표현 방식 | 가능한 연산 | 보존되는 것 | 변형·손실되는 것 | 근거·상태 |
|---|---|---|---|---|---|
| | | | | | |

검토 렌즈: 명제적/비명제적, tacit/explicit, factual/conceptual/procedural/metacognitive, a priori/a posteriori, 전달 가능성, 맥락·일반화 범위, 학문 영역, 이론/실전·응용. 모든 칸을 채우기보다 사례 차이를 설명하는 렌즈를 선택하고 이유를 적는다.

## 4. Knowledge System — capabilities

| 역량 | 구현·관행과 지원 방식 | 조작 단위·범위 | 누가 유지하는가? | 근거·한계 |
|---|---|---|---|---|
| ontology/semantics/claim/context | | | | |
| evidence/justification/confidence/inference/contradiction | | | | |
| identity/schema/metadata/document/block/record/triple/graph | | | | |
| hierarchy/taxonomy/tag/link | | | | |
| version/history/provenance | | | | |
| index/query/search/retrieval | | | | |
| validation/update/deprecation | | | | |
| governance/access/license/privacy | | | | |

지원 방식: native / extension / user convention / external tool / not supported / unknown / not applicable. 종이 방법론은 software-native 여부 대신 해당 방법론의 명시 규칙인지 개인 관행인지 설명한다.

### Epistemic lineage 추적

하나의 실제 자료를 선택해 `원출처 → 발췌 → 해석 → 파생 주장 → 재사용 → 수정`을 추적한다.

- Source: 어느 원자료·판본인가?
- Citation: 어느 기록이 어느 위치를 가리키는가?
- Provenance: 누가 언제 무엇을 어떤 과정으로 바꾸었는가?
- 누락된 연결 / 사후 복원 가능한 연결:
- 사람이 작성한 부분 / AI 또는 자동 처리 부분:
- 근거가 철회·변경될 때 파생 결과를 찾고 수정할 수 있는가?

### Lifecycle

| 단계 | 실제 동작·상태 변화 | 사람/시스템 역할 | 비용·실패·복구 | 근거 |
|---|---|---|---|---|
| capture | | | | |
| normalize | | | | |
| organize | | | | |
| connect | | | | |
| validate | | | | |
| retrieve | | | | |
| use/derive | | | | |
| revise | | | | |
| supersede/deprecate | | | | |

## 5. Interaction

- Capture friction과 semantic richness를 각각 어떻게 관찰했는가?
- Explicit/inferred structure의 주도권과 수락·수정·거부 경로는?
- User-driven/system-driven resurfacing의 계기와 방해 비용은?
- 내부 모델 중 사용자가 반드시 알아야 하는 것은?
- 정리 비용은 입력/검토/검색 중 언제 발생하는가?
- 중단·실수·자동화 오류에서 어떻게 복구하는가?

## 6. Human Outcome

| 결과 | 의도·가설 | 관찰 또는 연구 근거 | 아직 말할 수 없는 것 |
|---|---|---|---|
| remember / understand / decide / learn / create / communicate / act 중 관련 항목 | | | |

## 7. 비교 및 na implications — 기술 후 작성

- 공통 시나리오 ID / 동일하게 유지한 조건:
- 이 사례가 드러낸 차이 / 비교가 성립하지 않는 부분:
- 귀납적으로 추가·수정할 vocabulary:
- MVP 후보 / 실험 가설 / 장기 탐색 중 분류:
- 근거 → 제안 → 기대 결과 → 비용 → 반증 조건:
- 미확인 사항과 다음 확인 작업:
