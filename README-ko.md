<div align="right">

[English](README.md) · [中文](README-zh.md) · [日本語](README-ja.md) · 한국어 · [Русский](README-ru.md)

</div>

# general-readme-skill

> AI 코딩 어시스턴트를 사용하여 모든 프로젝트의 전문적인 README 파일 생성

![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-blue?style=flat)

## 기능

| 기능 | 설명 |
|---|---|
| 다중 톤 지원 | 3가지 작성 프로파일: 에너제틱, 미니멀, 프로페셔널 |
| 배지 시스템 | 3가지 비주얼 스타일로 shields.io 배지 자동 생성 |
| 다국어 지원 | 영어, 중국어, 일본어, 한국어, 러시아어 등 README 파일 생성 |
| 제로 의존성 | 외부 CLI, 런타임, 네트워크 서비스 불필요 |
| 멀티 플랫폼 | Claude Code, GitHub Copilot, Cursor에서 작동 |
| 개인정보 보호 | 민감한 키, 비밀번호, 개인 정보 자동 마스킹 |

## 빠른 시작

### Claude Code

```bash
mkdir -p .claude/skills/general-readme
cp SKILL.md .claude/skills/general-readme/
cp -r references/ .claude/skills/general-readme/
```

### GitHub Copilot

```bash
mkdir -p .github
cp SKILL.md .github/copilot-instructions.md
cp -r references/ .github/copilot-instructions/references/
```

### Cursor

```bash
mkdir -p .cursor/rules
cp SKILL.md .cursor/rules/general-readme.mdc
cp -r references/ .cursor/rules/references/
```

## 사용법

AI 코딩 어시스턴트에서 `/readme`를 입력하거나 "generate readme"라고 말하세요. 스킬이 다음을 안내합니다:

1. **구성** — 톤 프로파일, 배지 스타일, 언어 선택
2. **프로젝트 스캔** — 프로젝트 유형, 기술 스택, 구조 자동 감지
3. **생성** — 역 피라미드 구조로 README 작성
4. **출력** — 메인 파일 및 번역본 생성

### 지원 명령어

| 명령어 | 설명 |
|---|---|
| `/readme` | README 생성 트리거 |
| `generate readme` | 자연어 트리거 |
| `write readme` | 자연어 트리거 |
| `帮我写 README` | 중국어 트리거 |
| `更新README` | 기존 README 업데이트 |

## 프로젝트 구조

```
general-readme-skill/
├── SKILL.md                # 메인 스킬 정의 파일
├── examples/               # README 예제 파일
│   ├── app-readme.md       # 풀스택 애플리케이션 예제
│   ├── cli-readme.md       # CLI 도구 예제
│   └── library-readme.md   # 라이브러리/패키지 예제
├── install/                # 설치 가이드
│   ├── claude-code.md      # Claude Code 설정
│   ├── copilot.md          # GitHub Copilot 설정
│   └── cursor.md           # Cursor 설정
└── references/             # 참조 파일
    ├── badges.md           # 기술 배지 매핑
    ├── badge-styles.md     # 배지 레이아웃 규칙
    ├── diagram-templates.md # Mermaid/SVG 템플릿
    ├── language-guide.md   # 다국어 규칙
    ├── section-guidelines.md # 섹션 작성 규칙
    └── tone-profiles.md    # 작성 톤 정의
```

## 기술 스택

### 문서

| 기술 | 용도 |
|---|---|
| Markdown | 주요 콘텐츠 형식 |
| shields.io | 배지 생성 |
| Mermaid | 아키텍처 다이어그램 |

### 지원 플랫폼

| 플랫폼 | 통합 방법 |
|---|---|
| Claude Code | `.claude/skills/` 디렉토리 |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Cursor | `.cursor/rules/` 디렉토리 |

## 기여하기

1. 리포지토리를 포크
2. 기능 브랜치 생성 (`git checkout -b feature/amazing`)
3. 변경 사항 커밋 (`git commit -m 'feat: add amazing feature'`)
4. 브랜치에 푸시 (`git push origin feature/amazing`)
5. Pull Request 열기

## 라이선스

LICENSE 파일이 감지되지 않았습니다. 프로젝트 라이선스를 명확히 하려면 LICENSE를 추가하세요.
