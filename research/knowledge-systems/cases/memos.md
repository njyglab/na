# Memos

- Case ID: memos / 종류: 소프트웨어
- 조사일·조사자: 2026-09-24 / Codex, 문헌·소스 계약 분석
- 상태: 초기 기술·문서 근거 검토. 실행·성과 검증 전.
- 대상: usememos/memos의 열람 당시 main README와 API proto, 현재 공식 Usage 안내.
- 버전 한계: main은 가변이다. 커밋 조회는 웹 오류와 로컬 네트워크 제한으로 실패했다. 특정 릴리스에 기능을 귀속하지 않으며 후속 실행 전에 커밋·릴리스를 고정한다.
- 제외: 플러그인, 실제 개인 자료, DB 내부 저장 구조, 설치·동기화 검증.

## 1. 사례 자체의 기술

| 항목 | 기술 | 근거·상태 |
|---|---|---|
| Problem | 짧은 생각과 일상 기록을 자체 운영 환경에 빠르게 남긴다는 제품 지향 | C01, 당사자 설명 |
| Primitive | memo가 API 식별·수정 단위이며 content는 Markdown이다. 화면의 항목과 DB 행의 대응은 미확인 | C02 |
| Core Operations | 작성·저장 → 필요 시 태그·핀 → 시간 흐름·검색으로 재방문 | C01, C04. 문서상 재구성 |
| Temporality | 식별 이름과 생성·수정 시각이 분리된다 | C02. 시간대·날짜 경계 UI는 미확인 |
| Organization | 입력에서 제목·폴더 선택을 요구하지 않는다는 안내. 후속 조직 수단 제공 | C01, C04 |
| Retrieval | 시간순 목록·검색·태그·저장된 필터(Views) | C01, C04. 검색 성공률은 미측정 |
| Human burden | 재방문용 단서와 검토 습관을 사용자가 얼마나 관리하는지 실행 조사 필요 | 연구 질문 |

10분 행동 서술은 실제 관찰하지 않았다. 비교용 가상 장면은 [S1/S5 비교](../comparisons/capture-and-review.md)에 따로 둔다.

## 2. 근거 장부

모든 자료 열람일: 2026-09-24. 아래 위치는 문서 절 또는 proto 심볼이다. 원문은 읽었으나 제품을 실행하지 않았다.

| Source ID | 자료·주체 | 유형·판본 | 정확한 위치 |
|---|---|---|---|
| S01 | [Memos README](https://github.com/usememos/memos) · usememos | 공식, 가변 main | Memos / Why Memos? |
| S02 | [memo_service.proto](https://raw.githubusercontent.com/usememos/memos/main/proto/api/v1/memo_service.proto) · usememos | 소스의 API 계약, 가변 main | Memo, ListMemosRequest, MemoRelation, CreateMemoComment |
| S03 | [Usage](https://usememos.com/docs/usage) · Memos | 공식 문서, 버전 미표기 | Write and capture / Organize and find / Choose the question |

| Claim ID | 검증 가능한 주장 | 상태·근거 | 한계 |
|---|---|---|---|
| C01 | README는 제목·폴더·템플릿 선택 없는 Markdown 기록과 timeline·search·tags·pins를 안내한다 | 문서 확인, S01 Why Memos? | 실사용 마찰은 미측정 |
| C02 | Memo 계약은 name, content, create_time, update_time을 구분하며 목록 기본 정렬을 create_time desc로 명시한다 | 소스 계약 확인, S02 Memo / ListMemosRequest | 서버·UI 실행 보장으로 해석하지 않음 |
| C03 | 관계 enum은 REFERENCE와 COMMENT를 구분하고, 댓글 생성 RPC는 별도 memo 생성을 설명한다 | 소스 계약 확인, S02 MemoRelation / CreateMemoComment | 수정 이유·지지·반박의 의미까지 규정하지 않음 |
| C04 | Usage는 검색·archive/restore와 재사용할 필터 Views를 안내한다 | 문서 확인, S03 Organize and find | 상세 필터·복원 흐름 미실행 |

## 3. Knowledge — fit

해석: 짧은 서술을 저장할 수 있다는 사실과 관찰의 맥락을 충분히 보존한다는 주장은 다르다. 실제 예문을 이용해 사건·해석·행동 요청이 한 memo 안에 섞일 때 재사용이 어려워지는지 확인해야 한다. 절차 수행 능력이나 장기 학습 효과는 조사하지 않았다.

## 4. Knowledge System

C02는 내용·식별·시간을 분리한 native 계약의 근거다. C03은 관계 표현의 근거이지만, 관계가 곧 논증이나 파생 계보라는 뜻은 아니다. 다음 실제 자료 추적이 필요하다: 원문 링크 → 사용자 해석 → 후속 memo → 수정. 현재는 이 경로를 관찰하지 않았으므로 지원 범위를 확정하지 않는다.

Lifecycle 초기 확인 범위는 capture, retrieve, revise의 API/문서 표면이다. validation·supersession·retraction, 변경 이력과 삭제 복구, export의 관계 보존은 미확인이다. unknown을 미지원으로 기록하지 않는다.

## 5. Interaction

가설: 입력 시 필수 결정이 적더라도 누적 기록의 검토·재탐색 비용은 남을 수 있다. 같은 자료에서 무태그 기록과 후속 태그·Views 사용을 비교할 필요가 있다. 공식 지원과 사용자 관행을 분리하고 설정·숙련도를 기록한다.

## 6. Human Outcome

빠른 포착은 제품의 의도(C01)로 확인했다. 실제 누락 감소·재탐색 성공·이해·행동 재개의 효과는 미검증이다. 저장량이나 링크 수를 성과로 대체하지 않는다.

## 7. 연결과 다음 확인

- [정리 비용](../questions/organization-cost.md), [계보](../questions/epistemic-lineage.md), [성과](../questions/human-outcomes.md).
- 다음: 릴리스·커밋 고정 → 날짜 탐색·수정·검색 UI와 계약 대조 → 동일 가상 자료의 S1/S5 관찰.
- 내용 안 체크리스트 항목의 독립 식별 여부, 과거 날짜 작성, 시간대 변경, 댓글과 수정 이력의 차이를 확인한다.
- na 전이 가설은 [별도 종합](../synthesis/na-implications.md). 아직 스키마 선택 근거로 충분하지 않다.
