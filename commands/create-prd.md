# Create PRD (Product Requirements Document)

기능/제품에 대한 PRD 문서를 생성하라.

## 사용법

```
/create-prd $ARGUMENTS   # 기능 설명 또는 요구사항
```

## 역할

경험 많은 Product Manager로서 PRD를 작성한다.

**중요:**
- 사용자 니즈와 기능에 집중 (기술 구현 세부사항 아님)
- 시간 추정 포함하지 않음
- Why → What → How 순서로 작성

## PRD 템플릿

```markdown
# PRD: [기능명]

## 1. Overview
### 1.1 Problem Statement
<!-- 해결하려는 문제 -->

### 1.2 Goal
<!-- 이 기능의 목표 -->

### 1.3 Success Metrics
<!-- 성공 측정 기준 (KPI) -->

## 2. User Stories
### 2.1 Target Users
<!-- 대상 사용자 정의 -->

### 2.2 User Stories
<!-- As a [user], I want [goal] so that [benefit] -->

### 2.3 Jobs to be Done (JTBD)
<!-- 사용자가 달성하려는 작업 -->

## 3. Requirements
### 3.1 Functional Requirements
<!-- 필수 기능 목록 -->
| ID | Requirement | Priority |
|----|-------------|----------|
| FR-1 | ... | Must |
| FR-2 | ... | Should |

### 3.2 Non-Functional Requirements
<!-- 성능, 보안, 확장성 등 -->

### 3.3 Out of Scope
<!-- 이번 범위에서 제외되는 것 -->

## 4. User Flow
<!-- 주요 사용자 흐름 (텍스트 또는 다이어그램) -->

## 5. Acceptance Criteria
<!-- 완료 조건 체크리스트 -->
- [ ] Criteria 1
- [ ] Criteria 2

## 6. Dependencies & Risks
### 6.1 Dependencies
<!-- 의존성 -->

### 6.2 Risks & Mitigations
<!-- 위험 요소와 대응 방안 -->

## 7. Open Questions
<!-- 결정되지 않은 사항 -->
```

## 작성 가이드

1. **Problem First**: 문제 정의부터 시작
2. **User-Centric**: 기술보다 사용자 관점
3. **Measurable**: 측정 가능한 목표
4. **Prioritized**: MoSCoW (Must/Should/Could/Won't)
5. **Clear Scope**: 범위 명확히 정의

## 출력

- 위 템플릿 기반으로 PRD 작성
- 필요시 사용자에게 추가 정보 질문
- 출력 경로: `docs/PRD-[feature-name].md` 권장
