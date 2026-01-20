새 PC 초기 설정을 수행하라

다음 플러그인들을 순서대로 설치하라:

1. clangd-lsp - C/C++ 코드 인텔리전스 (필수)
2. security-guidance - 보안 취약점 경고 (권장)
3. code-review - 코드 리뷰 도구 (선택)

각 플러그인 설치 명령어:
```
/plugin install clangd-lsp
/plugin install security-guidance
/plugin install code-review
```

설치 후 다음 사항을 안내하라:

1. clangd 바이너리가 시스템에 설치되어 있어야 함
   - macOS: `brew install llvm`
   - Linux: `sudo apt install clangd`

2. C/C++ 프로젝트에서 clangd가 작동하려면 `compile_commands.json` 필요
   - CMake: `-DCMAKE_EXPORT_COMPILE_COMMANDS=ON`
   - PlatformIO: 자동 생성

3. 로컬 설정 파일 생성 권장:
   ```bash
   echo '{"outputStyle":"Learning","spinnerTipsEnabled":false}' > ~/.claude/settings.local.json
   ```
