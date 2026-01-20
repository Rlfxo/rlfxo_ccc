# Create Pull Request

브랜치 생성부터 PR 제출까지 전체 워크플로우를 수행하라.

## 사용법

```
/create-pr
/create-pr $ARGUMENTS   # PR 제목/설명 힌트
```

## 실행 순서

### 1. 현재 상태 확인
```bash
git status
git branch --show-current
git log origin/main..HEAD --oneline  # 커밋 확인
```

### 2. 브랜치 생성 (필요시)
- 현재 main/master에 있다면 새 브랜치 생성
- 브랜치명: `<type>/<short-description>`
  - 예: `feat/user-auth`, `fix/memory-leak`, `refactor/api-client`

### 3. 변경사항 커밋
- 스테이징되지 않은 변경사항이 있으면 `/commit` 규칙에 따라 커밋
- 논리적 단위로 분할 커밋 권장

### 4. 원격 푸시
```bash
git push -u origin <branch-name>
```

### 5. PR 생성
```bash
gh pr create --title "<title>" --body "<body>"
```

## PR 본문 템플릿

```markdown
## Summary
<!-- 변경사항 요약 (1-3 bullet points) -->

## Changes
<!-- 주요 변경 파일/기능 목록 -->

## Test Plan
<!-- 테스트 방법 또는 체크리스트 -->

## Related Issues
<!-- 관련 이슈 번호 (closes #123) -->
```

## 커밋 분할 가이드라인

- 기능/컴포넌트/관심사별 분리
- 관련 파일은 같은 커밋으로
- 리팩토링과 기능 추가 분리
- 각 커밋이 독립적으로 이해 가능해야 함

## 주의사항

- PR 생성 전 `git diff origin/main` 확인
- 큰 변경은 여러 커밋으로 분할
- 제목은 명확하고 간결하게
- Draft PR: `gh pr create --draft`
