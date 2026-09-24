# PKM / Personal Knowledge Systems 사례연구

## 1. 목적과 중심 질문

이 연구는 PKM 앱의 기능 순위를 만드는 작업이 아니라, 인간이 기록·지식·행동을 다루는 방식의 **domain analysis / conceptual modeling**이다. 현대 소프트웨어, 종이 기반 방법론, 역사적 실천, 개념적 시스템, 관련 연구를 함께 보되 서로 다른 증거 조건을 보존한다. 넓게는 Personal Knowledge Systems / Human Knowledge Systems 연구이며, PKM 제품 비교는 그 일부다.

중심 질문은 다음과 같다.

> 서로 다른 시스템은 무엇을 문제로 정의하고, 무엇을 하나의 단위로 삼으며, 어떤 인간 행동을 통해 어떤 지식을 보존·변형·재발견하여 무엇을 가능하게 하는가?

세부 질문:

- 방지하려는 failure mode는 무엇인가? 기록 누락, 정리 부담, 재탐색 실패, 맥락 소실, 미완료 행동, 근거 단절 중 무엇이 중요한가?
- 사용자에게 ‘하나의 생각’인 것과 저장·식별·조작 단위는 일치하는가?
- 질서는 capture, review, retrieval 중 언제 만들어지며 누가 비용을 부담하는가?
- 어떤 종류의 지식이 표현 과정에서 보존·변형·손실되는가?
- 출처에서 해석·파생·수정으로 이어지는 epistemic lineage를 어디까지 추적할 수 있는가?
- 풍부한 지식 모델을 유지하면서 사용자의 입력·검토 부담을 어떻게 다루는가?
- 실제로 기억·이해·판단·학습·창작·소통·행동에 도움이 되는가? 그 효과의 근거는 무엇인가?

완벽한 지식 taxonomy, 거대한 통합 ontology, na의 즉각적인 구현 명세를 만드는 것은 현재 목적이 아니다.

## 2. 범위와 사례의 종류

아래는 조사 대상과 질문이다. 각 항목의 기능·역사적 실천이 확인되었다는 뜻은 아니다.

| 종류 | 대상 | 주된 조사 질문 / 경계 |
|---|---|---|
| 현대 소프트웨어 | Memos | 빠른 포착, 시간성, 이후 조직·재탐색 비용을 어떻게 다루는가? 정확한 프로젝트·버전부터 확인 |
| 현대 소프트웨어 | Notion, Obsidian | page/block/file/record의 관계, 사용자 설정과 기본 기능, 구조 유지 비용을 분리 |
| 현대 소프트웨어 | zhfahim/anchor | 해당 저장소의 정체·목적·상태·primitive를 원 README와 코드/시연으로 확인. 이름에서 기능을 추정하지 않음 |
| 방법론 | Bullet Journal | rapid logging, review, migration의 의미와 인간 부담을 당사자 설명으로 검증 |
| 방법론 | Zettelkasten | 여러 실천 계열을 구분. 현대 방법론의 용어를 루만에게 소급하지 않음 |
| 방법론 | Commonplace book | 시대·사용자별 발췌, 분류, 색인, 재사용 관행의 차이를 보존 |
| 방법론 | GTD | 수집 이후 action/project/reference 등으로 처리하는 규칙과 검토 부담 조사 |
| 역사 사례 | Darwin, Leonardo, Luhmann | 실제 노트·카드·수고·편집 이력과 당사자의 설명을 우선. 디지털 아카이브의 기능을 당시 사용자의 기능과 구분 |
| 개념·명세 | Memex, Engelbart | 제안된 지식 작업과 인간 능력 증강의 관계. 비전·명세·구현·실사용 증거를 분리 |
| 선택 확장 | Xanadu | 인용·연결·버전·계보 비교에 추가 설명력이 있을 때 조사 |
| 관련 연구 | PIM, cognitive offloading, distributed cognition, sensemaking, refinding | 사례 해석과 평가 질문을 제공하는 연구 축. 구체 논문과 적용 범위는 후속 조사 |

관련 연구의 작업용 질문: **PIM**은 개인 정보의 획득·조직·유지·재사용을, **cognitive offloading**은 외부 기록에 맡기는 일과 남는 인지 부담을, **distributed cognition**은 사람·도구·환경에 걸친 과정을, **sensemaking**은 자료에서 설명과 이해를 구성하는 과정을, **refinding**은 이미 접한 정보를 다시 찾는 과정을 살피는 출발점으로 둔다. 이 설명은 문헌 검토를 대체하지 않는다.

Git, Wikipedia, 서지 관리, knowledge graph, 검색엔진, LLM/RAG는 경계 비교용 후보다. 핵심 범위를 자동으로 확장하지 않는다.

## 3. 두 프레임의 통합

```text
사례 자체의 언어·자료·행동을 기술한다 (case description schema)
  Problem / Primitive / Core Operations / Temporality
  Organization timing & cost / Retrieval / Human burden / Evidence
                              ↓
Knowledge — 무엇을 다루는가?
                              ↓ represented by
Knowledge System — 어떻게 표현·관리하는가?
                              ↓ exposed through
Interaction — 인간은 어떻게 조작하고 유지하는가?
                              ↓ evaluated in terms of
Human Outcome — 인간에게 무엇을 가능하게 하는가?
                              ↓
사례 간 공통 vocabulary → scenario comparison → na implications
```

네 층은 분석 순서이며, 검증된 인과 사슬이나 구현 아키텍처가 아니다. 결과와 사용 맥락은 앞선 층의 해석을 다시 바꿀 수 있다. 풍부한 graph나 ontology 자체를 좋은 결과의 대리 지표로 삼지 않는다.

### 사례 기술 schema

| 항목 | 기록할 내용 |
|---|---|
| Problem | 당사자가 정의한 문제, 방지하려는 실패, 대상 사용자·상황. 연구자의 해석은 별도 표시 |
| Primitive | 고유 명칭, 내용 단위, 식별 단위, UI 조작 단위, 저장 단위. 이들 사이의 불일치 |
| Core Operations | 사용자가 10분 동안 하는 행동의 순서, 입력·출력·상태 변화 |
| Temporality | 시간의 역할: 주소/탐색 축인지 metadata인지. 사건·작성·수정·검토·유효 시점의 차이 |
| Organization timing/cost | capture/review/retrieval 중 언제 조직하는지, 누가 제목·분류·링크·이동·유지 비용을 부담하는지 |
| Retrieval | chronology, hierarchy, index, keyword, full-text, backlink, graph traversal, query, resurfacing, recommendation |
| Human burden | 기억해야 할 규칙, 판단·반복 작업, 검토·수정·오류 복구, 중단 후 재개 비용 |
| Evidence/source quality | 위 설명을 뒷받침하는 자료, 위치, 버전·시기, 직접 확인 범위와 불확실성 |

기존 지형도의 최소 관찰 출발점은 문제의식·primitive·대표 동작·자료 접근성이었다. 시간성·조직 비용·검색·인간 부담을 더해 위 schema로 통합한다. 자료가 없는 칸은 ‘미확인’으로 남긴다.

명사 목록보다 동사를 우선한다: `capture → append → classify → link → retrieve → revisit → migrate → elaborate → synthesize → publish`. 이는 모든 사례의 필수 순서가 아니라 차이를 발견하기 위한 어휘 후보다. **저장 구조와 검색 구조는 같을 필요가 없다.** 지도 축 역시 관찰 뒤 선택하며 사례를 미리 정한 좌표에 배치하지 않는다.

## 4. Layer I — Knowledge / knowledge-system fit

| 렌즈 | 비교할 성질 | 사례에 던질 질문 |
|---|---|---|
| 인식론적 형태 | 명제적 / 비명제적 | 진술, 이미지, 감각, 수행, 경험을 어떻게 담는가? |
| 명시화 | 암묵지 / 형식지(tacit / explicit) | 무엇을 외부화할 수 있고 무엇은 실습·상황·사람에게 남는가? |
| 내용 성격 | factual / conceptual / procedural / metacognitive | 사실, 개념 관계, 절차, 자기 이해·학습 조절을 어떻게 표현하는가? |
| 획득·정당화 | a priori / a posteriori | 경험·관찰과 추론의 근거를 구별할 수 있는가? |
| 전달 가능성 | 개인적·상황 의존 ↔ 명시적 공유 가능 | 다른 사람이 재해석할 때 필요한 맥락은 무엇인가? |
| 범위·보편성 | 특수·맥락적 / 일반적 / 보편 주장 | 적용 조건과 예외, 일반화 범위를 보존하는가? |
| 학문 영역 | 수학·자연과학·공학·인문·일상 등 | 수식·도면·코드·서술·관찰 등 표현 요구가 다른가? |
| 응용 목적 | 이론적 이해 / 실전·응용 / 판단·제작 | 저장물이 설명·실행·연습·결정에 어떻게 사용되는가? |

이 축들은 서로 배타적인 단일 분류표가 아니다. 한 자료가 여러 성질을 가질 수 있다. procedural과 tacit, 비명제적을 동의어로 취급하지 않으며, explicit을 형식 논리로 표현되었다는 의미로 제한하지 않는다. a priori/a posteriori 역시 단순한 파일 유형 태그가 아니다.

**완벽한 taxonomy가 아니라 knowledge-system fit이 목적이다.**

`지식 성질 → 표현 방식 → 가능한 연산 → 보존 / 변형 / 손실 → 사용자에게 생기는 결과`

예시적 사고 실험: 절차 설명을 텍스트로 저장하는 것과 그 절차를 능숙하게 수행하는 것은 다르다. 실행 가능한 코드는 절차의 일부를 보존하지만 작성자의 판단과 사용 맥락까지 자동으로 보존하지는 않는다. 따라서 ‘저장 가능’과 ‘이해·수행 가능’을 구분한다.

## 5. Layer II — Knowledge System capabilities

구성요소 유무만 체크하지 않고 표현력, 접근·조작 방법, 유지 책임과 한계를 기술한다.

| 묶음 | 관찰 대상 |
|---|---|
| 의미·인식론 | ontology/semantics, entity/concept/relation, proposition/claim, context, meaning, 진리·정당화 기준 |
| 근거·추론 | evidence/source/justification/confidence/uncertainty, inference, contradiction/agreement, supports/contradicts/derived-from |
| 정보 단위 | identity/identifier, schema/metadata, document/block/record/triple/graph |
| 조직 | hierarchy/taxonomy/tag/link, 개념적 배치와 저장 위치의 관계 |
| 시간·계보 | version/history/provenance, authorship, 변경·유효 시점 |
| 접근 | index/query/search/retrieval, 여러 entry point와 refinding |
| 유지 | validation/update/revision/supersession/deprecation/retraction |
| 거버넌스 | collaboration, access control, ownership/authorship, license, privacy, 편집 규약 |

문서에 claim이 쓰여 있는 것과 시스템이 claim을 식별 가능한 객체로 관리하는 것은 다르다. 그렇다고 모든 지식 시스템에 명제를 최소 단위로 강요하지 않는다. 자신감 수치·인용 수·동료심사 여부는 진실성 자체가 아니며, confidence의 주체와 근거를 기록한다.

지원 방식은 `native / extension / user convention / external tool / not supported / unknown / not applicable`로 구분할 수 있다. 미확인을 미지원으로 바꾸지 않는다. 코드·문서에 존재하는 기능과 실제 동작 관찰도 구별한다.

### Epistemic lineage: Source / Citation / Provenance

| 개념 | 질문 | 필요한 관찰 |
|---|---|---|
| Source | 어디에서 왔는가? | 원자료·관찰·논문·발언자, 원문과 판본, 출처 유형 |
| Citation | 무엇을 명시적으로 가리키는가? | 어느 주장/발췌가 어느 자료의 어느 위치를 참조하는지 |
| Provenance | 어떤 과정을 거쳐 현재 상태가 되었는가? | 발췌·해석·요약·합성·수정·파생의 주체·시점·입출력 연결 |

```text
Paper A → Excerpt → My interpretation → Claim B → Essay C
원출처      인용 위치     해석 주체/과정      수정/파생    사용 맥락
```

AI 개입 시 `source → retrieved passage → LLM interpretation → user modification → derived claim`을 구분한다. 이는 구현 요구가 아니라 관찰 질문이다. 원문, 인용, 인간 해석, AI 제안이 섞일 때 어떤 구분과 수정 가능성이 있는지 조사한다.

`source_url` 하나는 시작점이지만 파생 계보 전체와 같지 않다. 버전 이력도 자동으로 epistemic provenance를 제공하지 않는다. 인용 관계만으로 지지·반박 관계를 확정하지 않는다. 출처·인용·계보는 정당화와 추적 가능성을 잇지만, 그 존재 자체가 주장의 참을 보장하지 않는다. W3C PROV는 필요시 검토할 명세 후보이며 채택 결정은 아니다.

연구자가 사례를 설명하는 근거의 질과, 사례 시스템이 사용자 지식의 근거를 관리하는 능력은 별개로 기록한다.

### Lifecycle

`capture → normalize → organize → connect → validate → retrieve → use/derive → revise → supersede/deprecate`

| 단계 | 관찰 질문 |
|---|---|
| capture | 최초 입력과 맥락을 얼마나 쉽게 남기는가? |
| normalize | 형식·단위·표현을 바꾸며 원문과 차이를 보존하는가? |
| organize | 분류·배치가 언제 누구에 의해 일어나는가? |
| connect | 관계의 대상·의미·방향을 어떻게 만든다? |
| validate | 출처·적용 조건·모순을 누가 검토하는가? |
| retrieve | 어떤 단서로 다시 만나며 실패하면 무엇을 하는가? |
| use/derive | 글쓰기·판단·행동에 재사용하고 파생 결과를 연결하는가? |
| revise | 내용·관점·근거 변화가 어떻게 기록되는가? |
| supersede/deprecate | 대체·더 이상 권장하지 않음·철회·삭제를 구분하는가? |

이는 강제 입력 파이프라인이 아니다. 생략·반복·역행할 수 있으며 모든 단계가 필요한 것도 아니다. 각 전환의 행위자, 비용, 흔적, 오류 회복을 본다.

## 6. Layer III — Interaction / UI·UX

- **Capture friction ↔ semantic richness**: 입력 단계의 필수 결정·시간과 나중에 얻는 의미 구조를 따로 관찰한다. 반드시 고정된 상충관계라고 가정하지 않는다.
- **Explicit ↔ inferred structure**: 직접 입력, 규칙, 추론의 역할을 구분하고 제안의 수락·수정·거부 비용을 본다.
- **User-driven ↔ system-driven resurfacing**: search/browse/review와 추천·알림의 주도권, 적시성, 방해 비용을 본다.
- **Knowledge-model richness ≠ interaction complexity**: 내부 모델이 풍부하다고 모든 metadata를 사용자에게 매번 입력시키는 것은 아니다. 이 분리를 핵심 설계 원칙 후보로 유지한다.

자유 입력 후 구조 후보를 제안하거나 필요한 순간에만 구조를 드러내는 것은 조사·실험 후보다. na가 AI 추출·자동 연결·자동 resurfacing을 구현하기로 결정한 것은 아니다. 원대화의 ‘cache hit를 인간에게 알려주는 시스템’은 관련 과거 기록을 적절한 순간에 다시 만나는 경험에 대한 비유로 보존한다.

편의성뿐 아니라 통제 가능성·설명 가능성·수정 가능성도 본다. 비용을 사용자에서 자동화로 옮기면 검토·오류 복구·프라이버시 비용이 새로 생기는지 확인한다. 의도적인 review/migration의 노력은 단순한 제거 대상이 아닐 수 있다.

## 7. Layer IV — Human Outcome

| 결과 | 확인할 질문 / 가능한 관찰 |
|---|---|
| remember | 필요한 때 기억하거나 다시 찾는가? 즉시 재탐색과 장기 기억은 분리 |
| understand | 관계·이유·조건을 자기 말로 설명할 수 있는가? |
| decide | 근거·대안·불확실성을 고려해 판단하는가? |
| learn | 이후 새로운 상황에서 적용·수행할 수 있는가? |
| create | 기록의 재결합으로 새로운 글·설계·산출물을 만드는가? |
| communicate | 다른 사람이 출처와 맥락을 이해할 수 있는가? |
| act | 필요한 행동을 선택·재개·완료하는가? |

저장량·링크 수·검색 클릭 수를 곧바로 성과로 해석하지 않는다. 설계자가 의도한 효과, 사용자가 보고한 효과, 실제 관찰한 결과, 연구자의 가설을 나눈다. 짧은 시연으로 장기 학습 효과를 확정하지 않는다.

## 8. 연구 방법과 근거 규율

1. 사례 고유 언어로 문제·primitive·행동을 기술한다.
2. 각 진술의 출처와 상태를 붙인다.
3. 네 층으로 해석하되 맞지 않는 항목과 정보 부재를 남긴다.
4. 반복되는 차이에서 공통 vocabulary와 지도 축을 추출한다.
5. 같은 사용자 장면으로 비교하고, 마지막에 na에 대한 가설을 만든다.

Evidence hierarchy의 탐색 우선순위는 **원자료 → 당사자 설명/명세 → 공식 문서 → 학술적 분석 → 후대 해석/커뮤니티 관행**이다. 이는 자동적인 진실성 점수표가 아니다. 당사자 문서는 의도를 보여주어도 효과를 입증하지 않을 수 있고, 역사적 맥락은 학술 분석이 필요할 수 있다. 주장에 맞는 증거를 선택하고 교차 확인한다.

- **확인된 사실**: 원자료·문서·관찰에서 정확히 확인한 범위. 출처와 위치·버전 필수.
- **해석**: 확인된 사실로부터 연구자가 도출한 의미. 근거와 대안 해석 명시.
- **미확인**: 원문 미열람, 실행 미검증, 충돌하는 자료, 과거 대화의 미복원 인용 등.

제품·방법론·역사 인물·개념 명세를 같은 수준의 실사용 증거로 취급하지 않는다. 루만의 당시 카드 사용과 현대 아카이브 UI, 현대 Zettelkasten의 규칙을 구분한다. 기능이 문서에 없다는 이유만으로 부재를 단정하지 않는다.

원대화의 Memos=시간축 memo, BuJo=entry/bullet와 migration, Luhmann=addressed Zettel와 reference/recombination, Obsidian=file/heading/block, Notion=page/block/database item, GTD=action/project/reference는 **조사 출발점으로 보존한 미확인 요약**이다. 원문 검증 전 최종 지형도의 사실 행으로 사용하지 않는다.

## 9. na로 연결하는 시점

지형도 → 대표 사례 deep dive → scenario comparison → na implications 순서를 유지한다.

na implications는 `MVP 후보 / 실험 가설 / 장기 탐색`으로 나눈다. 각각 근거 사례, 해결할 사용자 문제, 기대 결과, 비용·위험, 반증 조건을 기록한다. timestamp, Block/Bullet/Memo/Daily Log, source/claim 모델, AI 구조화는 모두 검토 대상이며 확정 스키마가 아니다. 구체 진행은 [research-plan.md](research-plan.md)를 따른다.
