# Clean Code

현재 브랜치와 비교 브랜치 사이의 변경사항을 분석하여 불필요한 코드를 정리합니다.

## 비교 대상 브랜치
$ARGUMENTS (기본값: main)

## 실행 순서

1. **변경 파일 목록 확인**
   ```bash
   git diff <compare-branch>..HEAD --stat
   ```

2. **불필요한 파일 검색**
   - 백업 파일 (`*_backup*`, `*.bak`, `*.orig`)
   - 임시 파일 (`*.tmp`, `*~`)
   - 테스트용 파일이 남아있는지 확인

3. **죽은 코드 검색**
   ```bash
   # 주석 처리된 코드
   git diff <compare-branch>..HEAD | grep -E "^\+\s*//.*[a-zA-Z]+\("

   # 빈 조건문/루프
   git diff <compare-branch>..HEAD | grep -E "^\+.*if.*\{\s*\}|^\+.*while.*\{\s*\}"

   # #if 0 블록
   git diff <compare-branch>..HEAD | grep -E "^\+.*#if 0"
   ```

4. **불필요한 주석 검색**
   ```bash
   # TODO/FIXME (검토 필요)
   git diff <compare-branch>..HEAD | grep -E "^\+.*(TODO|FIXME|XXX|HACK)"

   # 오래된 주석 (날짜 포함)
   git diff <compare-branch>..HEAD | grep -E "^\+.*//.*(2023|2024|2025)"
   ```

5. **사용하지 않는 변수/함수 검색**
   ```bash
   # 선언 후 사용하지 않는 static 변수
   # 컴파일 경고 확인
   make clean && make 2>&1 | grep -E "unused|never used"
   ```

6. **디버그 코드 검색**
   ```bash
   # printf/debug 문
   git diff <compare-branch>..HEAD | grep -E "^\+.*(printf|debug_printf|console\.log)"

   # 하드코딩된 테스트 값
   git diff <compare-branch>..HEAD | grep -E "^\+.*(0x(DEAD|BEEF|1234)|test_|dummy_)"
   ```

## 정리 대상 분류

### 즉시 삭제
- 백업 파일 (`*_backup*`, `*.bak`)
- 주석 처리된 코드 블록 (5줄 이상)
- `#if 0` 블록
- 빈 조건문/루프

### 검토 후 결정
- TODO/FIXME 주석 (유효한지 확인)
- 디버그 로그 (릴리즈에 필요한지 확인)
- 테스트용 상수/함수

### 유지
- 의미 있는 TODO (이슈 번호 포함)
- 필수 디버그 로그 (error, warn 레벨)
- API 문서 주석

## 출력 형식

```
## 정리 대상 파일

### 삭제 대상 파일
- path/to/backup_file.c (백업 파일)

### 삭제 대상 코드
파일: path/to/file.c
라인: 123-130
```c
// 주석 처리된 코드 블록
// old_function();
// another_old_call();
```

### 검토 필요
파일: path/to/file.c:45
```c
// TODO: 나중에 구현
```
이유: TODO 주석 - 유효한지 확인 필요

---
위 내용을 확인하고 정리 작업을 진행하세요.
```

## 주의사항

- 삭제 전 반드시 `git stash` 또는 커밋으로 백업
- 빌드 테스트 후 정리 확인
- 팀원과 공유된 코드는 협의 후 삭제
