# O-ADR-2025-0001: ADR: ADR 운영 원칙(문서 구조/넘버링/라벨/자동화)

- **Status**: Accepted
- **Date**: 2025-09-08
- **Discussion**: #1
- **Scope**: Repo
- **Related**: -

---

### 요약 (Summary)

V-Ref ADR은 vref-docs에서 단일 원칙하 관리하며 이슈 생성 및 승인 라벨을 적용해 자동화 한다

### 저장 위치 (Storage Path)

org (docs/adr/org/)

### 적용 범위 (Scope)

Org

### 관련 레포/이슈/PR

_No response_

### Context (배경/문제 정의)

- 여러 결정 사항에 대한 근거와 기록을 위한 문서 필요
- ADR을 여러 레포에서 관리하면 관리 복잡도 오버헤드
- 매번 직접 작성하면서 일관성 유지에 한계가 걱정되었음

### Decision (결정 사항)

* **SSOT**: 모든 ADR은 `V-Ref/vref-docs`에서 관리
* **디렉토리 구조**:

  ```
  docs/adr/
    org/
    repos/{vref-be,vref-fe,vref-config,vref-infra,etc}/
    index.md  # 자동 생성/갱신
  ```
* **이름 규칙(파일/ID)**:
  `<Scope>-ADR-<Repo?>-<YYYY>-<NNNN>-<slug>.md`

  * Scope: `O`(Org) / `R`(Repo)
  * Repo?: Org는 생략, Repo는 `vref-be` 등
  * 예) `O-ADR-2025-0001-api-versioning.md`, `R-ADR-vref-be-2025-0003-cache-invalidation.md`

* **넘버링(MVP)**: `NNNN = GitHub Issue 번호` (충돌 없음, 간단).
  * 필요 시 향후 docs/adr/{repo} 별 카운트 진행

* **상태 체계**: `Proposed / Accepted / Suspended / Superseded / Deprecated`.
* **라벨**(docs 전용): `adr:proposed/accepted/suspended/superseded/deprecated`, `scope:*`
* **템플릿**: 이슈 폼에 **저장 위치 (Storage Path)** 필드로 실제 저장 경로를 지정

* **자동화**:
  * `adr:accepted` 라벨 → 해당 경로에 ADR `.md` 자동 생성(PR)
  * `docs/adr/**/*.md` 변경 → `index.md` 상태별 섹션으로 자동 재빌드

### Consequences (결과/파급효과)

* Positive

  * 작성 흐름 간단(이슈→라벨→PR 자동 생성), 히스토리 보존
  * 레포 확장/세분화에 유연(저장 위치 옵션으로 분기)

* Negative

  * GitHub Actions 의존(권한/러너 이슈 시 영향)
  * 이슈 번호 기반 넘버링은 Org/Repo별 연속성이 약함
  * 라벨 관리가 흐트러지면 자동화가 오동작할 수 있음


### Alternatives Considered (대안)

- 각 레포에 ADR 저장(분산 관리) → 검색/일관성 저하, 링크 단절 위험
- 수동 인덱스 운영 → 누락/정렬 오류 가능
- 전역 단일 일련번호(통합 카운터) → 충돌 관리/동기화 비용↑
- adr-tools/별도 사이트 운영 → 도구 의존도↑, 초기 셋업 비용↑

### 검증/지침 연계 (Validation)

- DoR: 배경·목표·저장 위치 명시, 명시된 상태/라벨 사용
- DoD: Status/Discussion/Scope/Related 필드 채움, 인덱스에 노출 확인
- 이슈/파일 예시 1건을 실제 생성하여 docs/adr/index.md 반영 확인

### Deciders / Reviewers

_No response_

---

> Tracking issue: #1
