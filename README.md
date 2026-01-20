# Claude Code Configuration

개인 Claude Code 설정 저장소

## 구조

```
~/.claude/
├── commands/           # 커스텀 슬래시 명령어
├── settings.json       # 공통 설정
└── .gitignore          # 자동 생성 파일 제외
```

## 새 PC 설정

```bash
# 1. Clone
git clone git@github.com:Rlfxo/rlfxo_ccc.git ~/.claude

# 2. Claude Code 실행 후 startup 명령어
/startup
```

## 추천 플러그인

### C/C++ 임베디드 개발용

| 플러그인 | 설명 | 필요성 |
|----------|------|--------|
| **clangd-lsp** | C/C++ 코드 인텔리전스 (Go to Definition, Find References, Hover) | 필수 |
| **security-guidance** | 보안 취약점 자동 경고 (buffer overflow, injection 등) | 권장 |
| **code-review** | PR 자동 코드 리뷰 | 선택 |

### 수동 설치

```bash
/plugin install clangd-lsp
/plugin install security-guidance
/plugin install code-review
```

### clangd 사전 설치 필요

```bash
# macOS
brew install llvm
export PATH="/opt/homebrew/opt/llvm/bin:$PATH"

# Ubuntu/Debian
sudo apt install clangd
```

> clangd가 제대로 작동하려면 프로젝트에 `compile_commands.json` 필요
> - CMake: `-DCMAKE_EXPORT_COMPILE_COMMANDS=ON`
> - PlatformIO: 자동 생성

## 커스텀 명령어 목록

| 명령어 | 설명 |
|--------|------|
| `/startup` | 새 PC 초기 설정 (플러그인 설치) |
| `/commit` | Git 커밋 메시지 추천 |
| `/analyze-repo` | 프로젝트 구조/아키텍처 분석 |
| `/review-code` | 코드 리뷰 수행 |
| `/doc-gen` | 문서 생성 |
| `/find-similar` | 유사 코드/패턴 찾기 |
| `/quick-fix` | 빠른 버그 수정 분석 |
| `/archive` | 세션 지식 아카이브 |
| `/ask-kb` | 지식 베이스 쿼리 |
| `/recall` | 프로젝트 지식 리콜 |

## 로컬 설정

`settings.local.json`은 Git에서 제외됨 (개인 설정용)

```json
{
  "outputStyle": "Learning",
  "spinnerTipsEnabled": false
}
```
