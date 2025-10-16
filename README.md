# 📖 `vref-docs` Repository

* V-Ref 전반 문서·ADR(Architecture Decision Record)·가이드 통합 관리 저장소
* 모든 기술 의사결정과 문서를 중앙화하여 일관성 있는 지식 베이스 제공

---

## 🎯 목적

* ADR(Architecture Decision Record) 중앙 집중 관리
* 조직 전체 기술 의사결정 이력 추적 및 공유
* 이슈 템플릿을 통한 표준화된 ADR 생성 프로세스
* 자동화 워크플로를 통한 ADR 인덱스 관리

---

## 🛠 사용법

### 1. ADR 작성

* 위치: `docs/adr/`
* 조직 레벨: `docs/adr/org/`
* 이슈 템플릿: `.github/ISSUE_TEMPLATE/00-adr-proposal.yml` 사용
* 자동 생성: ADR 이슈 생성 시 워크플로가 자동으로 문서 파일 생성

### 2. 이슈 템플릿

* 위치: `.github/ISSUE_TEMPLATE/*.yml`
* 10종 기본 제공: ADR Proposal, Task, Docs, Feature, Refactor, Test, Chore, Bug, Fix, Idea
* ADR 전용 템플릿으로 구조화된 의사결정 문서 작성 지원

### 3. PR 템플릿

* 위치: `.github/PULL_REQUEST_TEMPLATE.md`
* 공통 체크리스트 포함

### 4. 워크플로

* 위치: `.github/workflows/`
* 예시:
    * `adr-auto-create.yml` : ADR 문서 자동 생성
    * `adr-auto-create-index-.yml` : ADR 인덱스 자동 업데이트

---

## 📂 레포 구조

```
vref-docs/
├── .github/
│   ├── ISSUE_TEMPLATE/           # 이슈 템플릿 (ADR 포함)
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── workflows/                # ADR 자동화 워크플로
├── docs/
│   └── adr/                      # Architecture Decision Records
│       ├── index.md              # ADR 인덱스
│       └── org/                  # 조직 레벨 ADR
└── README.md
```

---

## ⏩ 향후 계획

* 프로젝트별 ADR 디렉토리 구조 확장
* 기술 가이드 및 베스트 프랙티스 문서 추가
* Notion 연동을 통한 문서 동기화
* ADR 검색 및 탐색 도구 개발

---

## 💡 철학

* **SSOT 중심**: 모든 기술 의사결정은 단일 원천에서 관리
* **자동화 우선**: 수동 문서 관리 최소화
* **투명성 보장**: 의사결정 과정과 근거를 명확히 기록
* **점진적 확장**: 핵심 ADR부터 시작 → 단계적 문서화 확대
