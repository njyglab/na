# 다음 세션 인수인계

## 현재 목표

PKM / Personal Knowledge Systems 사례연구를 시작한다. 소프트웨어 기능 비교를 넘어 각 시스템의 문제의식, primitive, 인간 행동, 지식 표현·손실, 출처·계보, 실제 인간 성과를 살핀다. na의 데이터 모델을 미리 정하지 않고 사례에서 공통 개념을 얻는 것이 목적이다.

## 먼저 읽을 파일

1. [pkm-study.md](pkm-study.md): 합의된 연구 방향과 4-layer lens.
2. [research-plan.md](research-plan.md): 조사 묶음과 공통 시나리오.
3. [case-template.md](case-template.md): 사례·근거 기록 양식.

## 바꾸지 말아야 할 연구 순서

`사례 자체의 기술 → Knowledge → Knowledge System → Interaction → Human Outcome → na implications`

- 지형도는 case description schema, 네 층은 analysis lens다.
- 처음부터 na의 Block/Bullet/Memo/Daily Log/Entity/Project ontology를 적용하지 않는다.
- 지식 유형은 완벽한 taxonomy를 만들기 위한 것이 아니라 knowledge-system fit을 살피는 렌즈다.
- Source(어디서), Citation(무엇을 명시적으로 참조), Provenance(어떤 변형 과정을 거쳤는지)를 구분한다.
- Knowledge-model richness와 interaction complexity를 분리한다.
- 저장 구조와 검색 구조는 같을 필요가 없다.
- 의도한 효과, 실제 관찰, 연구자 해석, 미확인을 구분한다.
- 문서 저장을 곧바로 지식 모델링으로, 정교한 모델을 곧바로 좋은 인간 성과로 취급하지 않는다.

## 현재 완료된 것과 아직 하지 않은 것

완료: 접근 가능한 원대화 확인, 연구 프레임 통합, 범위·진행 순서·템플릿·공통 시나리오 작성.

미수행: 원자료 웹 조사, 제품 기능·버전 검증, Anchor 저장소 확인, 역사 자료 대조, 실제 실행 비교, 사용자 실험, na 구현 또는 MVP 결정.

과거 대화의 검색 인용 토큰은 정확한 URL·위치로 복원되지 않았다. 기존 사례 설명을 복사해 ‘확인된 사실’로 쓰지 말고 다시 확인한다. 연구의 틀은 보존하되 구체적 역사·제품 주장은 검증 대상이다.

## 첫 작업 — 바로 시작 가능한 순서

1. 현재 프로젝트의 지침과 연구 파일 위치를 확인한다. 이 패키지를 가져왔다면 상대 링크를 유지한다.
2. Memos의 정확한 프로젝트 및 공식 문서, Bullet Journal 당사자 자료를 찾는다. 후보 식별이 모호하면 모호한 대상만 확인하고 다른 사례 조사는 진행한다.
3. 각 사례를 템플릿으로 생성하고 Problem/Primitive/Core Operations와 출처부터 작성한다.
4. 시간성·조직 시점·검색·인간 부담을 추가하고 중요한 주장마다 source ID·위치·상태를 붙인다.
5. S1 포착과 S5 검토·행동을 중심으로 초기 비교를 작성한다. 문서 기반과 직접 실행 결과를 분리한다.
6. 두 사례가 드러낸 vocabulary와 열린 질문을 기록한다. 곧바로 na 요구사항으로 변환하지 않는다.
7. 다음 묶음 Darwin + Luhmann의 원자료 접근 경로를 확보한다. 이후 Notion/Obsidian/Anchor로 확장한다.

첫 조사 세션의 현실적인 완료 단위는 ‘근거가 연결된 초기 사례 문서 두 개 + 비교 메모 + 미확인 목록’이다. 전체 범위를 한 번에 완결하려 하지 않는다.

## 열린 질문과 결정 유보

| 질문 | 현재 상태 | 결정에 필요한 것 |
|---|---|---|
| na는 누구의 어떤 문제를 우선 해결하는가? | 전체 프로젝트 맥락 미제공 | 기존 README·사용자 장면 확인. 초기 사례 조사를 막지는 않음 |
| Block/Bullet/Memo/Daily Log의 관계는? | 동일시하지 않음 | 사례별 내용·식별·UI·저장 단위 비교 |
| timestamp가 중심 주소인가 metadata인가? | 후보 | 시간 단서와 비시간적 재탐색 장면 |
| 정리를 언제 수행할 것인가? | capture/review/retrieval 모두 열림 | 비용의 이동과 결과 비교 |
| 어떤 지식 유형을 우선 지원할 것인가? | 미결정 | 실제 사용자 장면과 보존·손실 분석 |
| source/citation/provenance의 최소 수준은? | 연구에서는 모두 관찰, 구현 범위 미정 | 근거 수정·파생 추적의 필요성과 비용 |
| 명시적 claim 모델이 필요한가? | 미결정 | 텍스트·링크로 부족한 실제 사례 |
| AI 구조 추론·자동 연결이 필요한가? | 가설 | 수락·수정·거부 및 오류 회복 비용 |
| resurfacing은 누가 언제 주도하는가? | 미결정 | 재발견 이득과 방해·프라이버시 비용 |
| MVP/experiment/long-term 경계는? | 연구 후 판단 | 사례 근거와 na 맥락 |
| 역사 사례와 현대 도구를 어떻게 공정하게 비교할까? | 대응 분석 원칙만 정함 | 자료 조건·시대·작업 목적 명시 |
| Human Outcome을 어떻게 평가할까? | 단기 관찰 지표만 제안 | 학습·기억의 장기 평가 설계 |
| Xanadu·RAG 등으로 확장할까? | 선택적 확장 | 핵심 사례만으로 설명되지 않는 질문 |

## 다음 세션에 전달할 시작 요청

> 이 폴더의 pkm-study.md, research-plan.md, case-template.md를 읽고 PKM/Personal Knowledge Systems 사례연구를 이어가 주세요. 첫 조사 묶음은 Memos + Bullet Journal입니다. 사례 자체의 Problem/Primitive/Core Operations를 먼저 기술한 뒤 Knowledge → Knowledge System → Interaction → Human Outcome 렌즈로 분석해 주세요. 원자료와 공식 자료를 확인하고 중요한 주장에 정확한 출처·위치·확인 상태를 붙여 주세요. 원대화의 사례 요약은 미검증 조사 출발점입니다. 두 사례의 초기 문서와 공통 시나리오 비교, 미확인 목록을 작성하고, 아직 na의 ontology나 구현 범위를 확정하지 마세요. 다음 묶음은 Darwin + Luhmann, 이후 Notion/Obsidian/zhfahim/anchor입니다.

## 원대화 추적 정보

- 제목: 지형도 만들기 정리
- conversation ID: `6ab30d15-ae24-83ee-ad65-a7ab7d69fd8b`
- 이 패키지 작성일: 2026-09-23
- 이 문서들은 원대화 전체의 verbatim transcript가 아니라 연구를 이어가기 위한 구조화된 요약이다. 필요한 주요 개념과 용어는 본문에 보존했다.
