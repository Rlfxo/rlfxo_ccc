# Check & Clean

코드 품질 검사 및 불필요한 요소 정리를 수행하라.

## 사용법

```
/check              # 전체 검사 + 정리 제안
/check $ARGUMENTS   # 특정 경로나 옵션
```

## 검사 항목

### 1. 코드 품질 (Quality)

| 항목 | 설명 |
|------|------|
| 잠재적 버그 | null 참조, 범위 초과, 타입 오류 |
| 에러 처리 | try-catch 누락, 에러 무시 |
| 복잡도 | 과도한 중첩, 긴 함수/파일 |
| 중복 코드 | 반복되는 로직 |
| 네이밍 | 불명확한 변수/함수명 |

### 2. 보안 (Security)

| 항목 | 설명 |
|------|------|
| 하드코딩된 시크릿 | API 키, 비밀번호, 토큰 |
| 입력 검증 | SQL injection, XSS, command injection |
| 인증/권한 | 누락된 인증 체크 |
| 민감 데이터 | 로그에 노출된 개인정보 |

### 3. 정리 대상 (Cleanup)

| 항목 | 패턴 |
|------|------|
| **Dead Code** | 사용되지 않는 함수, 변수, import |
| **주석 처리된 코드** | `// oldFunction()`, `/* disabled */` |
| **불필요한 로그** | `console.log`, `print()`, `printf` (디버깅용) |
| **TODO/FIXME** | 오래된 TODO 주석 |
| **빈 파일/폴더** | 내용 없는 파일 |
| **중복 파일** | `.bak`, `.old`, `.copy` |
| **임시 파일** | `.tmp`, `.swp`, `~` |

## 출력 형식

```markdown
# 검사 결과

## Summary
- 품질 이슈: N개
- 보안 이슈: N개
- 정리 대상: N개

## 🔴 Critical (즉시 수정 필요)
| 파일:라인 | 유형 | 설명 |
|-----------|------|------|
| src/api.ts:45 | Security | 하드코딩된 API 키 |

## 🟡 Warning (수정 권장)
| 파일:라인 | 유형 | 설명 |
|-----------|------|------|
| src/utils.ts:120 | DeadCode | 사용되지 않는 함수 `oldHelper` |

## 🟢 Info (검토 권장)
| 파일:라인 | 유형 | 설명 |
|-----------|------|------|
| src/main.ts:30 | Cleanup | 디버깅 console.log |

## 정리 명령어 (선택적 실행)
아래 항목들을 정리하시겠습니까?

### Dead Code 제거
- [ ] `src/utils.ts` - `oldHelper()` 함수 삭제
- [ ] `src/types.ts` - 미사용 타입 `OldType` 삭제

### 불필요한 로그 제거
- [ ] `src/main.ts:30` - `console.log('debug')` 삭제
- [ ] `src/api.ts:78` - `console.log(response)` 삭제

### 주석 처리된 코드 제거
- [ ] `src/handler.ts:45-52` - 주석 블록 삭제
```

## 언어별 검사

### JavaScript/TypeScript
- ESLint 규칙 기반
- 미사용 import/export
- any 타입 남용

### C/C++ (임베디드)
- 미사용 변수/함수
- 메모리 누수 패턴
- volatile 누락 (ISR)
- 버퍼 오버플로우

### Python
- 미사용 import
- bare except
- mutable default argument

## 옵션

| 옵션 | 설명 |
|------|------|
| `--fix` | 자동 수정 가능한 항목 수정 |
| `--security-only` | 보안 이슈만 검사 |
| `--cleanup-only` | 정리 대상만 검사 |
| `--path <dir>` | 특정 경로만 검사 |

## 주의

- 자동 삭제 전 반드시 확인
- 주석 처리된 코드가 의도적일 수 있음
- 로그가 프로덕션에서 필요할 수 있음
