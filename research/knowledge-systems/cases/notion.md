# Notion — 문서·구조화 데이터 결합의 기준 사례

조사일: 2026-09-27 / 조사자: Codex. 상태: 공식 API·도움말 기반 초기 기술. 실행·효과·내부 구현 미검증.

범위: 현재 공개 문서. API 설명은 2025-09-03 이후 database/data source 구분을 따른다. 실제 호출 버전과 요금제·설정은 실행 시 고정한다. 부가 제품 전체나 AI 기능을 포괄하지 않는다.

## 사례 기술

| 항목 | 초기 기술 | 근거 |
|---|---|---|
| Problem | 문서와 구조화된 항목을 함께 작성·조회하는 흐름을 설명할 기준 사례로 선정 | 연구자의 선정 이유 |
| Primitive | block, page, data source, database를 구별 | C01–C02 |
| Core Operations | 본문 작성·속성 입력·관계 연결·여러 조건으로 조회 | C01–C03. 문서상 재구성 |
| Temporality | 생성·수정 시각과 식별자를 구분하는 block 계약 | C01; 전체 변경 이력은 별도 조사 |
| Organization / Retrieval | 스키마·관계·뷰를 설계하고 조건을 통해 접근 | C02–C03; 유지 비용 미측정 |
| Human burden | 속성·관계·뷰 정의와 변경 부담, 기록 도중 구조화 시점을 조사할 필요 | 가설 |

## 출처와 주장

열람일은 모두 2026-09-27. 가변 웹 문서이며 원문 해당 절을 열람했다. 공개 API 모델을 내부 저장 구조로 해석하지 않는다.

| ID | 출처·위치 |
|---|---|
| S01 | [Block reference](https://developers.notion.com/reference/block), 소개·Keys |
| S02 | [Working with databases](https://developers.notion.com/guides/data-apis/working-with-databases), Overview·Structure·Iterate over a database object |
| S03 | [Relations and rollups](https://www.notion.com/help/relations-and-rollups), 관계·rollup 설명·FAQ의 CSV 질문 |
| S04 | [Export your content](https://www.notion.com/help/export-your-content), workspace export 주의사항 |

| Claim | 문서에서 확인한 범위 | 근거·한계 |
|---|---|---|
| C01 | block에는 id·parent·type과 시간 정보가 있고 본문 종류에 따른 표현이 있다 | S01, API 계약 확인 |
| C02 | database는 data sources와 views를 담으며 data source가 schema와 소속 pages를 연결한다. page의 속성값과 본문 blocks는 구별된다 | S02, Structure. 예전 database.properties 설명과 혼용 금지 |
| C03 | relation은 페이지를 연결하고 rollup은 관계를 이용한 집계를 제공한다 | S03, 공식 기능 설명. 일반 온톨로지 추론이라는 뜻은 아님 |
| C04 | 관계를 CSV로 내보내면 텍스트 URL이 되고 그 CSV를 다시 가져오는 것만으로 관계가 재구성되지 않는다고 안내한다 | S03 FAQ, 실제 왕복 미실행 |
| C05 | workspace export를 재업로드하는 것만으로 원래 workspace를 즉시 재생성할 수 없다고 안내한다 | S04. 모든 별도 복구 방법이 불가능하다는 뜻은 아님 |

## 네 층 초기 분석

- **Knowledge**: 서술과 구조화 속성을 함께 다룰 수 있다는 C02를 출발점으로 삼는다. 표현 가능성이 이해·학습을 보장하는 것은 아니다. 원문과 개인 해석의 혼합 여부는 실제 인스턴스에서 관찰한다.
- **Knowledge System**: 내용, 식별, 스키마, 관계, 조회 표현을 구별한다. C04–C05는 ‘내용을 꺼냄’과 ‘동작하는 시스템을 재구성함’의 차이를 보여주는 조사 근거다.
- **Interaction**: 같은 항목을 다른 뷰로 조작할 때 사용자가 데이터 구조를 얼마나 알아야 하는지 확인한다. 간단한 입력과 정교한 모델을 같은 복잡도로 취급하지 않는다.
- **Human Outcome**: 재탐색·판단·창작·협업 성과는 이번 자료로 검증하지 않았다. API 표현력이 성과의 대리 지표가 아니다.

## 다음 조사

[연구 방향](../notion-research-direction.md)의 가상 인스턴스에서 이동·삭제·속성 변경·내보내기를 추적한다. 지원되는 API 연산과 UI 가능 범위, views·permissions·history의 이식성을 각각 확인한다. 관계와 본문 링크·synced block의 의미를 동일시하지 않는다. 내부 DB·협업 알고리즘·프론트엔드 스택은 아직 조사하지 않았다.
