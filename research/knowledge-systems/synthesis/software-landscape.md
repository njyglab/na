# 지식·업무 소프트웨어의 초기 지형도

작성: 2026-09-27. 공식 자료로 대상과 관찰 표면을 확인한 탐색 지도다. 분류와 연구 가치는 연구자의 해석이며 시장점유율·영향력 순위나 도입 추천이 아니다. 기능 전체·요금제·실행·라이선스 범위는 검증하지 않았다.

## 비교 축

문서·노드·레코드·업무 객체 중 어디서 출발하는지, 의미 구조를 언제 부여하는지, 질의와 상태 전이를 얼마나 중시하는지, 개인/팀의 유지 책임, 데이터·동작을 교체할 수 있는지를 함께 본다. 한 제품은 여러 영역에 걸친다. 기업용·온톨로지를 개인 메모의 단순한 상위 단계로 배열하지 않는다.

## 사용자 지정 사례

아래 ‘공식 자료’ 링크가 각 행의 근거이며 열람일은 모두 2026-09-27. 코드 저장소는 링크의 가변 브랜치 README만 확인했고 구현 분석은 하지 않았다. ‘연구 가치’는 비교 가설이다.

| 사례 | 공식 자료에서 확인한 초점 | 지형상의 위치·연구 가치 | 다음 검증 |
|---|---|---|---|
| [Notion](../cases/notion.md) | page·block·schema·relation·view | 문서와 구조화 데이터의 결합 기준 | 연산·이식성·삭제 의미 |
| [Tana Outliner](https://outliner.tana.inc/learn/features/supertags) | Supertag를 node에 적용하고 fields·search nodes로 조직 | 기록에서 타입 있는 대상으로 발전하는 경계 | native node와 타입·참조·export의 관계 |
| [Linear](https://linear.app/docs/issue-relations) | issue의 blocked/blocking/related/duplicate 관계 | 업무 의미가 정해진 모델의 비교점 | 일반 relation으로 환원할 때 잃는 규칙 |
| [ClickUp](https://developer.clickup.com/docs/tasks) | task와 custom fields, linked tasks | 확장 가능한 업무 객체의 비교점 | 업무 계층·Docs·views 사이의 경계 |
| [AFFiNE](https://raw.githubusercontent.com/toeverything/AFFiNE/canary/README.md) | docs·canvas·tables, local-first·collaboration 지향 | 문서와 공간적 표현을 결합하는 비교점 | 같은 내용의 표현 전환과 참조 의미 |
| [AppFlowy](https://raw.githubusercontent.com/AppFlowy-IO/AppFlowy/main/README.md) | 자체 호스팅 안내, 데이터 통제·구성 가능한 도구 지향 | 문서·데이터 workspace를 직접 운영하는 비교점 | 클라이언트·서버·데이터 모델·편집판 경계 |
| [SiYuan](https://raw.githubusercontent.com/siyuan-note/siyuan/master/README.md) | 세밀한 block-level reference와 Markdown WYSIWYG | 개인 지식의 주소·참조 단위 비교점 | 블록 이동·재사용·저장/내보내기 |
| [Docmost](https://raw.githubusercontent.com/docmost/docmost/main/README.md) | 협업 wiki, spaces·권한·comments·history | 팀 문서와 관리 책임을 분리해 보는 비교점 | 권한 상속·이력·검색·자체 운영 |

Tana Inc는 회사 이름으로 제시되었으므로 이 지도는 공식 Supertags 자료의 제품 표기인 Tana Outliner를 조사 대상으로 식별했다. 회사의 모든 제품·서비스를 포괄하지 않는다.

AFFiNE·AppFlowy·SiYuan·Docmost는 ‘Notion의 오픈소스 버전’보다 **서로 다른 강조점을 가진 대안 프로젝트**로 관리한다. 동등한 기능·형식·API·운영 조건을 가정하지 않는다. 특히 Docmost README는 core와 enterprise 영역의 라이선스를 구분한다. 실제 코드 재사용·설치 전에는 대상 릴리스와 파일의 조건을 별도로 확인한다.

## 설명력을 추가하는 후보 — 아직 심화 조사 채택 전

| 후보 | 공식 근거·확인한 표면 | 추가하는 비교 질문 |
|---|---|---|
| [Airtable](https://support.airtable.com/articles/1747995963-introduction-to-airtable-basics) | table·record·field·view 설명 | 본문 편집기를 제거해도 남는 데이터 운영 핵심은? |
| [Coda](https://help.coda.io/hc/en-us/articles/39555858394637-Basics-of-Coda-formulas) | canvas·table·button·automation에서 사용하는 수식 | 문서가 계산·행동을 제공하는 앱이 되는 경계는? |
| [Confluence](https://www.atlassian.com/software/confluence/knowledge-base) | 조직의 knowledge base, 권한·문서 이력 안내 | 개인 재탐색에서 조직의 책임·신뢰 유지로 무엇이 추가되는가? |
| [Stardog](https://docs.stardog.com/inference-engine/) | 명시적 reasoning schema와 추론 엔진 | 관계 저장을 넘어 기계가 도출하는 의미는 무엇인가? |
| [Palantir Ontology](https://www.palantir.com/docs/foundry/ontology/overview) | objects·properties·links와 actions·functions·security | 지식 표현을 업무 실행에 연결하면 필요한 계약은? |

후보 선정 이유는 구조적 차이를 설명하는 능력이다. 인지도·영향력을 평가하려면 기준일, 사용자/조직 채택 자료, 생태계·통합·운영 지속성의 근거를 별도로 수집한다. GitHub stars·벤더 고객 수·검색 노출을 하나의 동일 지표로 합치지 않는다.

## ‘온톨로지 엔진’ 연구에서 분리할 책임

| 책임 | 기준 자료 | 다른 책임과의 경계 |
|---|---|---|
| 의미·공리 | [OWL 2 Overview](https://www.w3.org/TR/owl2-overview/), Abstract·Introduction | 클래스·속성·개체의 형식 의미. 필드 이름 붙이기만으로 동등하지 않음 |
| 제약 검증 | [SHACL](https://www.w3.org/TR/shacl/), Abstract | RDF graph가 조건을 만족하는지 검증. 추론과 같은 연산이 아님 |
| 추론 실행 | Stardog Inference Engine, 위 링크 | 스키마·규칙으로 도출하는 결과. LLM의 개연적 제안과 구별 |
| 업무 실행 | Palantir Ontology, 위 링크의 Ontology building | 객체와 관계뿐 아니라 action·function·보안 의미를 다룸 |

‘온톨로지 엔진’은 하나의 고정된 제품 종류로 가정하지 않는다. 다음 조사에서 모델 편집, 저장·질의, 검증, 추론, 운영 행동 중 원하는 역할을 좁힌다. 노트 링크 그래프, 의미 모델, 권한 정책, workflow 상태 머신은 연결될 수 있지만 같은 구조는 아니다.

## 우선순위 제안

1. Notion의 공개 단위·연산·내보내기 경계를 기준으로 작성.
2. Tana·Airtable·Coda로 자유 기록/타입/계산의 경계를 대조.
3. Linear·ClickUp으로 미리 정한 업무 의미와 사용자 정의 모델의 차이를 대조.
4. AFFiNE·AppFlowy·SiYuan·Docmost는 필요한 책임의 구현·운영·교체 가능성을 중심으로 선택 조사.
5. Confluence·Stardog·Palantir는 기업 KMS·의미·운영 계층의 차이를 설명하는 후속 표본.

상세 진행과 평가 기준은 [Notion 중심 연구 방향](../notion-research-direction.md)을 따른다. 소스·문서 확인을 실제 동작이나 인간 성과의 검증으로 승격하지 않는다.
