# Commit

Staged Changes를 분석하여 적절한 commit message를 추천하라.

## 실행 순서

1. `git status`로 staged/unstaged 파일 확인
2. `git diff --cached`로 staged 변경사항 분석
3. 변경사항이 여러 논리적 단위면 **커밋 분할 제안**
4. 각 커밋에 대해 message 추천

## Conventional Commits 규칙

```
<type>: <description>

[optional body]
```

### Type 목록
| Type | 설명 |
|------|------|
| feat | 새로운 기능 |
| fix | 버그 수정 |
| docs | 문서 변경 |
| style | 포맷팅, 세미콜론 등 (코드 변경 없음) |
| refactor | 리팩토링 (기능 변경 없음) |
| perf | 성능 개선 |
| test | 테스트 추가/수정 |
| chore | 빌드, 설정 등 유지보수 |
| ci | CI/CD 설정 |
| revert | 이전 커밋 되돌리기 |

## 커밋 분할 기준

다음 경우 별도 커밋으로 분할 제안:
- 서로 다른 기능/컴포넌트 변경
- 타입이 다른 변경 (feat + fix + docs)
- 소스 코드 vs 문서/설정 파일
- 리팩토링과 기능 추가가 섞인 경우

## 작성 규칙

1. 제목은 50자 이내, 명령형으로 작성 (Add, Fix, Update)
2. 본문은 72자에서 줄바꿈
3. Why와 What 중심으로 작성
4. 이모지 사용 금지

## 출력 형식

```
## 추천 커밋 (N개)

### 커밋 1
파일: file1.ts, file2.ts
```
feat: add user authentication

Implement JWT-based auth with refresh token support
```

### 커밋 2
파일: README.md
```
docs: update API documentation
```

---
위 내용을 확인 후 직접 커밋하세요.
```

## 중요

- 추천만 하고 직접 커밋하지 않음
- 사용자가 선택하여 직접 명령어 입력
