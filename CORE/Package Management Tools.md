---
tags:
  - "#core"
---
# Package Management Tools
---
`패키지 관리 도구(Package Management Tools)`는 소프트웨어 개발에서 라이브러리나 패키지를 설치, 업데이트, 삭제, 버전 관리하는데 사용되는 도구입니다.

개발자는 직접 코드를 다운로드하거나 빌드하지 않고도, 필요한 외부 모듈을 쉽게 설치하고 프로젝트에 통합할 수 있습니다.

## Homebrew
---
`Homebrew`는 macOS 및 Linux에서 사용되는 대표적인 오픈소스 패키지 관리자입니다. 터미널 명령어를 통해 간단하고 효율적으로 다양한 소프트웨어와 개발 도구를 설치, 업데이트, 제거, 관리할 수 있습니다.

### 설치 방법 (macOS 기준)
1. Homebrew 설치 
	- 터미널에서 다음 명령어를 실행하세요:
	```bash
	/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
	```
    
2. 설치 확인 
	- 설치가 완료되었는지 아래 명령어로 확인하세요:
	```shell
	brew --version
	```


### 주요 명령어
| **명령어**                 | **설명**        |
| ----------------------- | ------------- |
| `brew install [패키지명]`   | 패키지 설치        |
| `brew list`             | 설치된 패키지 목록 확인 |
| `brew update`           | 저장소 메타데이터 최신화 |
| `brew upgrade`          | 설치된 패키지 업그레이드 |
| `brew uninstall [패키지명]` | 패키지 제거        |
| `brew search [키워드]`     | 패키지 검색        |
| `brew info [패키지명]`      | 패키지 상세 정보 확인  |

### 관련 URL
---
[Homebrew 공식 웹사이트](https://brew.sh/)
[Homebrew GitHub 저장소](https://github.com/Homebrew/brew)

## apt
---
`apt(Advanced Package Tool)`는 Debian 및 Ubuntu 계열 Linux 배포판에서 사용하는 기본 패키지 관리자입니다. 

시스템 도구, 서비스, 라이브러리 등 OS 구성 요소를 손쉽게 관리할 수 있도록 해줍니다.

### 주요 명령어
| 명령어                       | 설명               |
| ------------------------- | ---------------- |
| `sudo apt update`         | 저장소 메타데이터 갱신     |
| `sudo apt upgrade`        | 시스템 전체 패키지 업그레이드 |
| `sudo apt install [패키지명]` | 패키지 설치           |
| `sudo apt remove [패키지명]`  | 패키지 제거           |
| `sudo apt purge [패키지명]`   | 패키지 + 설정 파일 제거   |
| `sudo apt autoremove`     | 불필요한 의존성 자동 삭제   |
| `apt list --installed`    | 설치된 패키지 목록 확인    |
| `apt list --upgradable`   | 업그레이드 가능한 패키지 확인 |
| `apt search [키워드]`        | 패키지 검색           |
| `apt show [패키지명]`         | 패키지 정보 상세 보기     |
| `sudo apt clean`          | 다운로드 캐시 정리       |

# pip
---
`pip (pip installs packages)`는 Python의 공식 패키지 관리자입니다. 

Python 표준 라이브러리에 포함되지 않은 외부 패키지(라이브러리, 모듈 등)를 쉽게 설치 업그레이드, 제거, 관리 할 수 있습니다. 

### 주요 명령어
| **명령어**                           | **설명**           |
| --------------------------------- | ---------------- |
| `pip install [패키지명]`              | 패키지 설치           |
| `pip install [패키지명]==버전`          | 특정 버전 설치         |
| `pip uninstall [패키지명]`            | 패키지 제거           |
| `pip list`                        | 설치된 패키지 목록 확인    |
| `pip show [패키지명]`                 | 패키지 상세 정보 확인     |
| `pip freeze > requirements.txt`   | 현재 환경 패키지 목록 저장  |
| `pip install -r requirements.txt` | 저장된 목록 기반 패키지 설치 |
### 팁 
- 가상환경 (venv)과 함께 사용하는 것이 좋습니다.
- [PyPI](https://pypi.org/)를 기본 저장소로 사용합니다.
- 보안 점검 도구: pip-audit