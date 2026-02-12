# MCP-Study

MCP(Model Context Protocol)를 학습하고 실험하기 위한 프로젝트입니다.  
[FastMCP](https://github.com/jlowin/fastmcp) 기반으로 MCP 서버, 도구(Tool), 프롬프트, 리소스를 직접 구현해보며 익히는 것을 목표로 합니다.

> **Status**: 🏗️ 프로젝트 스캐폴딩 완료, 본격적인 MCP 서버 개발 진행 중

## Tech Stack

| Category | Tool |
|----------|------|
| Language | Python 3.11+ |
| MCP Framework | [FastMCP](https://github.com/jlowin/fastmcp) >= 2.14.5 |
| Package Manager | [uv](https://docs.astral.sh/uv/) |
| IDE | [Cursor](https://cursor.sh/) (with custom rules & commands) |

## Project Structure

```
mcp-study/
├── main.py                  # 엔트리포인트
├── pyproject.toml           # 프로젝트 메타데이터 & 의존성
├── uv.lock                  # 의존성 락 파일
│
├── lessons/                 # MCP 학습 커리큘럼
│   ├── 01-basics/           # MCP 기초 (서버, 도구, 리소스)
│   ├── 02-prompts/          # 프롬프트 템플릿 & 엔지니어링
│   └── 03-rag/              # RAG (Retrieval-Augmented Generation)
│
├── toyprojects/             # 단일 파일 미니 프로젝트
│   ├── 01-todo/             # TODO 앱 (HTML)
│   ├── 02-tetris/           # 테트리스 게임 (HTML)
│   └── 03-snake/            # 스네이크 게임 (HTML)
│
└── .cursor/
    ├── rules/               # Cursor AI 코딩 규칙
    │   ├── 00-python.mdc    # Python 코딩 표준 (항상 적용)
    │   ├── 01-mcp.mdc       # FastMCP 서버 개발 규칙
    │   ├── 02-streamlit.mdc # Streamlit 개발 규칙
    │   └── 03-common.mdc    # 리팩토링/테스트/디버깅 규칙
    └── commands/             # Git 워크플로우 커맨드
        ├── commit.md
        ├── create-pr.md
        ├── create-issue.md
        └── create-hotfix-pr.md
```

## Getting Started

### Prerequisites

- Python 3.11+
- [uv](https://docs.astral.sh/uv/) 패키지 매니저

### Setup

```bash
# 저장소 클론
git clone https://github.com/<your-username>/mcp-study.git
cd mcp-study

# 의존성 설치
uv sync

# 실행 확인
uv run python main.py
```

### 패키지 추가

```bash
# pip 대신 uv를 사용합니다
uv add <package-name>
```

## Lessons

MCP의 핵심 개념을 단계별로 학습합니다.

| # | Topic | Description |
|---|-------|-------------|
| 01 | **Basics** | MCP 서버 생성, `@mcp.tool()` 도구 등록, `@mcp.resource()` 리소스 노출 |
| 02 | **Prompts** | `@mcp.prompt()` 프롬프트 템플릿 정의, 재사용 가능한 프롬프트 설계 |
| 03 | **RAG** | Retrieval-Augmented Generation 파이프라인 구축 |

## Toy Projects

프롬프트 하나로 만든 단일 파일 웹 앱/게임 모음입니다.  
각 디렉토리에 원본 프롬프트(`*-prompt.md`)와 결과물(`.html`)이 함께 있습니다.

| # | Project | Description |
|---|---------|-------------|
| 01 | **TODO App** | 로그인, 추가/완료/삭제 기능이 있는 TODO 앱 |
| 02 | **Tetris** | 7종 테트로미노, 점수, 레벨 시스템이 있는 테트리스 |
| 03 | **Snake** | 점수, 속도 증가, 하이스코어(localStorage) 지원 스네이크 게임 |

## Development Guidelines

이 프로젝트는 `.cursor/rules/`에 정의된 코딩 규칙을 따릅니다:

- **Type Hints** — 모든 함수 인자와 반환값에 명시적 타입 힌트
- **Docstrings** — Google Style docstring 필수
- **Error Handling** — `try-except`로 예외 처리, 명확한 에러 로그
- **MCP Tools** — `@mcp.tool()` docstring은 LLM이 도구를 이해하는 설명서 역할
- **Git** — 한국어 명령형 커밋 메시지, `feature|fix|hotfix/{issue-number}` 브랜치 전략

## License

This project is for personal study purposes.
