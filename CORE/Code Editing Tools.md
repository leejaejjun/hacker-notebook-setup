---
tags:
  - "#core"
---
# Intergrated Development Enviromnent
---
`IDE (Intergrated Development Enviroment, 통합 개발 환경)`는 소프트웨어 개발자가 코드 작성부터 디버깅, 실행,배포까지 하나의 환경에서 효율적으로 작업할 수 있도록 도와주는 개발 도구들의 집합입니다.

대표적인 IDE로 `Visual Studio`, `PyCharm`, `IntelliJ IDEA`, `Xcode` 등이 있습니다.


## VI(VIM)
---
`VI`은 유닉스에서 시작된 경량 텍스트 편집기이며, `VIM`은 그것을 확장한 개발용 데이터 입니다. 모드 기반 인터페이스를 사용하며, 빠른 텍스트 조작과 자동화 기능, 플러그인 등을 통해 프로그래머에게 최적화된 환경을 제공합니다.

### 동작 방식
| **모드**                | **설명**                  | **전환 방법**    |
| --------------------- | ----------------------- | ------------ |
| 명령 모드 (Normal Mode)   | 파일 탐색, 복사/삭제, 저장 등 수행   | 기본 모드        |
| 입력 모드 (Insert Mode)   | 실제 텍스트를 입력하는 모드         | i, a, o 등 입력 |
| 비주얼 모드 (Visual Mode)  | 텍스트 블록 선택               | v, V 입력      |
| 명령어 모드 (Command Mode) | 저장, 종료, 검색 등 수행 (:로 시작) | 명령 모드에서 :    |
- 명령 모드 진입은 `esc`를 누르면 됩니다.

### 기본 사용법
| 동작             | 명령어            |
| -------------- | -------------- |
| 편집 시작 (Insert) | i, a, o        |
| 저장             | :w             |
| 종료             | :q             |
| 저장 후 종료        | :wq or ZZ      |
| 강제 종료 (저장 안 함) | :q!            |
| 한 줄 삭제         | dd             |
| 복사             | yy             |
| 붙여넣기           | p              |
| 실행 취소          | u              |
| 되돌리기 취소        | Ctrl + r       |
| 찾기             | /검색어           |
| 찾은 곳 이동        | n (다음), N (이전) |
### 설치 방법
- Linux
	```bash
	sudo apt install vim
	```

## nano
---
nano는 유닉스/리눅스 시스템에서 널리 사용되는 가볍고 사용하기 쉬운 텍스트 기반 편집기 입니다. 다른 편집기들과 달리 모드 없이 직관적인 조작이 가능하여 리눅스 초보자에게 특히 적합합니다.

### 기본 명령어
| 동작   | 단축키 (Ctrl + …)               |
| ---- | ---------------------------- |
| 저장   | Ctrl + O (Write Out) → Enter |
| 종료   | Ctrl + X (Exit)              |
| 잘라내기 | Ctrl + K                     |
| 붙여넣기 | Ctrl + U                     |
| 복사   | Alt + 6                      |
| 검색   | Ctrl + W                     |
| 줄 이동 | Ctrl + _ → 줄 번호 입력 후 Enter   |
- Ctrl은 보통 ⌃, ^, CTRL 등으로 표기됩니다. 예: ^X = Ctrl + X

### 설치 방법
- Linux
	```bash
	sudo apt install nano
	```

## Visual Studio
---
`Visual Studio`는 Microsoft에서 개발한 IDE로 C, C++, C#, VB.NET 등 다양한 언어로 대규모 소프트웨어 및 애플리케이션 개발을 위한 도구입니다. 특히 Windows 애플리케이션, 웹 서비스, 게임 개발, 모바일 앱 개발 등에 최적화되어 있습니다.

### 주요 기능
- 프로젝트/솔루션 관리
	- .sln 기반 대규모 프로젝트 구조 관리
- 단위 테스트 도구
	- MSTest, xUnit 등 테스트 프레임 워크 통합
- 버전 관리 통합
	- Git, GitHub, Azure DevOps 내장 연동
- GUI 디자이너
	- WinForms, WPF 등 GUI 시각적 설계 도구 제공
- 코드 분석 및 리펙터링
	- 코드 품질 검사, 실시간 오류 탐지, 리팩토링 추천

### 설치 방법
1. [Visual Studio 공식 웹사이트](https://visualstudio.microsoft.com/ko/) 접속
2. Community, Professional, Enterprise 중 하나 선택해 설치 프로그램 다운로드
3. 실행 후 설치 마법사에서 **워크로드(작업 부하)** 선택
    - 예:
        - “.NET 데스크톱 개발”
        - “ASP.NET 및 웹 개발”
        - “C++을 사용한 데스크톱 개발” 등
4. 설치 후 재부팅 및 실행

## VSCode
---
`VSCode`는 Microsoft가 개발한 오픈소스 기반의 경량 코드 편집기입니다. 웹 개발부터 시스템 프로그래밍, 데이터 사이언스까지 다양한 언어와 환경에서 사용할 수 있도록 설계된 범용 개발 도구이며, Windows, macOS, Linux 등 주요 플랫폼에서 사용 가능합니다.

VSCode는 확장성이 매우 좋다는 장점이 있습니다.

### 주요 기능
- 확장 프로그램 지원
    - VS Code Marketplace에서 다양한 확장 프로그램 설치 가능.
    - 예: Python, Prettier, ESLint, Docker 등.
- 테마 및 UI 커스터마이징
    - 사용자 설정을 통해 에디터 테마와 글꼴을 변경할 수 있음.
- 통합 터미널
    - 에디터 내에서 터미널을 실행하여 개발 및 빌드 작업 가능.
- Git 통합
    - Git 명령어를 UI에서 바로 실행 가능하며 코드 변경 내역 확인 가능.

### 설치 방법
- Windows
	1. [VSCode 공식 웹사이트](https://code.visualstudio.com/) 접속
	2. 운영체제에 맞는 설치 파일 다운로드
	3. 설치 후 실행
- macOS
	1. 아래의 명령어를 터미널에 입력하여 설치 가능합니다.
		```bash
		brew install --cask visual-studio-code
		```


