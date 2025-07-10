---
tags:
  - "#core"
---
# C
---
C 언어는 1970년대 초 벨 연구소(Bell Labs)의 데니스 리치(Dennis Ritchie)가 개발한 절차적 프로그래밍 언어입니다. 시스템 소프트웨어(운영체제, 컴파일러 등)와 다양한 응용 프로그램 개발에 널리 사용되어 왔으며, 오늘날에도 임베디드 시스템, 하드웨어 제어, 고성능 소프트웨어 개발에 많이 활용됩니다.

주요 특징
- 절차적(Procedural) 언어: 명확한 순서와 구조로 프로그램을 작성
- 플랫폼 독립성: 표준에 맞게 작성된 코드는 다양한 운영체제에서 컴파일 가능
- 저수준 접근: 메모리와 하드웨어를 직접 제어할 수 있음
- 컴파일 언어: 소스 코드를 기계어로 변환하여 빠른 실행 속도 제공
- 다양한 파생 언어: C++·Java·Python 등 현대 언어의 기반
	
활용 분야
- 운영체제(예: UNIX, Linux 커널)
- 임베디드 시스템 및 펌웨어
- 컴파일러, 데이터베이스, 네트워크 드라이버
- 각종 소프트웨어 인프라 및 고성능 애플리케이션

## 설치 방법
### Windows
Visual Studio 설치
1. [VIsual Studio](https://visualstudio.microsoft.com/ko/)다운로드
2. 설치를 진행하는 과정에서 "C++을 사용한 데스크톱 개발" 워크 로드 선택

### mac
1. 터미널에 아래의 코드를 입력하여 설치를 진행합니다.
```bash
xcode-select --install
```

2. 설치 확인
	- 터미널에 `clang --version`  입력하여 설치 확인

### linux
Ubuntu/Debian 계열
1. 아래의 명령어를 터미널에 입력하여 설치 합니다.
```bash
sudo apt install gcc
```

2. 설치 확인
	- 터미널에 `gcc --version` 입력하여 설치 확인


# Python
---
파이썬은 높은 수준의 범용 프로그래밍 언어로, 코드의 가독성을 강조하며 들여쓰기를 통해 코드 구조를 명확히 표현합니다. 1991년 귀도 반 로섬(Guido van Rossum)이 처음 발표했으며, 현재는 전 세계적으로 가장 인기 있는 언어 중 하나입니다.

주요 특징
- `간결하고 읽기 쉬운 문법`: 영어와 유사한 문법으로 초보자도 쉽게 배울 수 있습니다.
- `인터프리터 언어`: 별도의 컴파일 과정 없이 바로 실행할 수 있습니다.
- `객체 지향 및 함수형 프로그래밍 지원`: 다양한 프로그래밍 패러다임을 지원합니다.
- `방대한 표준 라이브러리: 웹 개발`, 데이터 분석, 인공지능, 자동화 등 다양한 분야에 활용할 수 있습니다.
- `크로스 플랫폼`: 윈도우, 맥, 리눅스 등 다양한 운영체제에서 동일하게 동작합니다
	
활용 분야
- 웹 개발(서버, 백엔드)
- 데이터 분석 및 인공지능
- 자동화 및 스크립트
- 소프트웨어 개발 및 프로토타이핑
- 과학/공학 계산 등

## 설치 방법
### Windows
1. [파이썬 공식 홈페이지](https://www.python.org/) 접속 후 최신 버전의 파이썬 설치 파일을 다운로드 합니다.
	- `Download Python {version}`이라 적힌 버튼을 누르시면 됩니다.
2. 다운로드 한 `python-{version}-{architecture}.exe` 파일을 실행합니다.
3. 설치 옵션 선택
	- "Add Python to PATH" 체크박스를 반드시 선택하세요
	- "Install Now"
4. 설치 완료 확인
	- 명령 프롬프트(CMD 또는 Powershell)에서 `python --version` 입력하여 설치 확인

### mac
homebrew 이용한 설치
1. 아래 명령어를 터미널에 입력하여 설치하시면 됩니다.
```bash
brew install python
```
2. 설치 확인
	- 터미널에 `python3 --version` 혹은 `python3`입력하여 설치 확인

공식 설치 파일 이용한 설치
1. [파이썬 공식 홈페이지](https://www.python.org/) 접속 후 최신 버전의 파이썬 설치 파일을 다운로드 합니다.
	- `Download Python {version}`이라 적힌 버튼을 누르시면 됩니다.
2. 다운로드 한 `python-{version}-{architecture}.pkg` 파일을 실행하여 설치 마법사 안내에 따라 설치합니다.
3. 설치 확인
	- 터미널에 `python3 --version` 혹은 `python3`입력하여 설치 확인

### Linux
Ubuntu/Debian 계열
1. 터미널에 아래 명령어를 입력하여 설치하시면 됩니다. 
```bash
# python, pip(파이썬 패키지 관리자) 설치
sudo apt install python3 python3-pip
```
2. 설치 확인
	- 터미널에 `python3 --version` 혹은 `python3`입력하여 설치 확인
# JAVA
---
`Java`는 고수준의 범용 객체지향 프로그래밍 언어로, 1995년 Sun Microsystems(현재 Oracle)에서 처음 발표되었습니다. Java의 가장 큰 특징은 Write Once, Run Anywhere(WORA), 즉 한 번 작성한 코드를 어떤 운영체제에서도 실행할 수 있다는 점입니다. 이는 Java 프로그램이 플랫폼에 독립적인 바이트코드로 컴파일되어, Java Virtual Machine(JVM)이 설치된 모든 환경에서 동작하기 때문입니다.

주요 특징
- `객체지향`: 모든 것이 객체로 구성되어 있어 코드의 재사용성과 유지보수성이 뛰어남
- `플랫폼 독립성`: JVM만 있으면 어떤 OS에서도 동일하게 실행 가능
- `보안성`: 포인터를 지원하지 않고, 다양한 보안 메커니즘 내장
- `멀티스레딩`: 여러 작업을 동시에 처리할 수 있음
- `풍부한 라이브러리`: 네트워크, 데이터베이스, GUI 등 다양한 표준 라이브러리 제공
- `대규모 개발에 적합`: 엔터프라이즈, 웹, 모바일(특히 Android) 등 다양한 분야에서 활용

활용 분야
- 웹 애플리케이션(서버/백엔드)
- 모바일 앱(Android)
- 데스크톱 애플리케이션
- 빅데이터, 클라우드, IoT, 게임 등

## 설치 방법
### Windows
1.	[Oracle 공식 다운로드 사이트](https://www.oracle.com/java/technologies/downloads/#jdk24-windows)에 접속해서 환경에 맞는 설치 파일 다운로드
2.	다운로드한 설치 파일(예: `jdk-{Ver}_windows-x64_bin.exe`)을 더블 클릭하여 설치 마법사 진행
3.	환경 변수 설정
	- JAVA_HOME 변수 이름으로 JDK가 설치된 경로(예: C:\Program Files\Java\jdk-XX)를 등록합니다.
	- 시스템 환경 변수 Path에 `%JAVA_HOME%\bin`를 추가합니다
4.	설치 확인
	- 명령 프롬프트에서 `java --version` 또는 `javac --version` 입력하여 정상 설치 확인

### mac
hombrew를 이용한 설치
1. 아래 명령어 중 하나를 이용하여 설치를 진행합니다.
```bash
brew install --cask temurin

brew install --cask zulu
```

2. 설치 확인
	- 터미널에 `java --version`을 입력하여 설치 확인

3. 환경 변수 설정 (필요시)
```bash
export JAVA_HOME=$(/usr/libexec/java_home)
export PATH=$JAVA_HOME/bin:$PATH
```
- 위 내용을 `~/.zshrc` 또는 `~/.bash_profile`에 추가 후 `source ~/.zshrc` 실행

Oracle JDK 설치
1.	공식 사이트 접속: Oracle Java 다운로드 페이지에서 macOS용 `.dmg` 파일 다운로드
2.	설치 파일 실행: 다운로드한 `.dmg` 파일을 더블 클릭해 설치 마법사 진행
3.	설치 확인: 터미널에서 `java -version` 또는 `javac -version` 입력

### Linux
Ubuntu/Debian 계열
1. 아래 명령어를 터미널에 입력하여 설치를 진행합니다.
```bash
sudo apt install openjdk-{version}-jdk
```

2. 설치 확인
	 - 터미널에 `java --version`을 입력하여 설치 확인

3. 환경 변수 설정(필요시)
```bash
sudo vim /etc/profile
```

```bash
# profile에 추가
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
export PATH=$PATH:$JAVA_HOME/bin
```

```bash
source /etc/profile
```


# 관련 URL
---
[파이썬 공식 웹사이트](https://www.python.org/)
[Oracle 공식 다운로드 사이트](https://www.oracle.com/java/technologies/downloads/#jdk24-windows)

