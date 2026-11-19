---
description: .gitignore 생성, origin 연결, prefix 규칙에 맞춘 커밋 후 push까지 한 번에 수행
argument-hint: [커밋 메시지]
---

# Commit & Push

아래 순서대로 커밋 작업을 진행해 줘.
이미 완료된 단계는 확인 후 건너뛴다.

## 입력

- 커밋 메시지: `$ARGUMENTS`

## 작업 순서

### 1. `.gitignore` 생성

> `.gitignore` 파일이 이미 있으면 이 단계는 건너뛴다.

다음 항목을 포함해 `.gitignore`를 생성한다.

- **에디터/IDE**: VS Code(`.vscode/`), JetBrains(`.idea/`) 등
- **macOS**: `.DS_Store`, `.AppleDouble`, `.LSOverride`, `._*` 등
- **Windows**: `Thumbs.db`, `ehthumbs.db`, `Desktop.ini`, `$RECYCLE.BIN/` 등
- **환경변수 파일**: `.env`, `.env.*` (단, `.env.example`은 제외 대상에서 뺀다)
- **기타 일반 항목**: 로그(`*.log`), 의존성 폴더(`node_modules/`), 빌드 산출물(`dist/`, `build/`) 등

### 2. remote 연결

> `origin` remote가 이미 등록되어 있으면 이 단계는 건너뛴다.

- remote 이름: `origin`
- 주소: `git@github.com:LEE0202020/a_commands.git`

```bash
git remote add origin git@github.com:LEE0202020/a_commands.git
```

### 3. 커밋

변경 내용을 확인한 뒤, 아래 prefix 규칙 중 적절한 것을 골라 커밋 메시지를 작성한다.

- 형식: `<prefix>: <커밋 메시지>`
- 예시: `feat: 로그인 기능 추가`

### 4. push

`origin`에 push한다.

```bash
git push -u origin <현재 브랜치>
```

## 커밋 prefix 규칙

| prefix     | 용도                                  |
| ---------- | ------------------------------------- |
| `feat`     | 새로운 기능 추가                      |
| `fix`      | 버그 수정                             |
| `docs`     | 문서 수정 (README 등)                 |
| `style`    | 코드 포맷 변경 (세미콜론, 공백 등)    |
| `refactor` | 리팩토링 (기능 변화 없음)             |
| `test`     | 테스트 코드 추가/수정                 |
| `chore`    | 빌드, 설정, 패키지, 기타 작업         |
| `perf`     | 성능 개선                             |
| `ci`       | CI 설정 수정                          |
| `build`    | 빌드 시스템 수정                      |
| `revert`   | 커밋 되돌리기                         |