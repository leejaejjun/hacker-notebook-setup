---
tags:
  - "#core"
---
# 가상 머신
---
`가상 머신`은 물리적인 컴퓨터 위에서 하이퍼바이저라는 가상화 소프트웨어를 이용해 또 다른 컴 퓨터를 소프트웨어적으로 흉내내는 것입니다. 실제 컴퓨터처럼 작동하지만, 실제 하드웨어 없이도 작동할 수 있도록 만든 논리적 컴퓨터 입니다.

## 1형 하이퍼바이저
---
`1형 하이퍼바이저`는 물리적 서버(하드웨어)에 직접 설치되어 실행되는 가상화 소프트웨어입니다. 운영체제 위해서 동작하는 2형 하이퍼바이저와 달리, 1형 하이퍼바이저는 운영체제를 거치지 않고 하드웨어 자원을 직접 제어합니다. 이 때문에 `베어메탈 하이퍼바이저` 또는 `네이티브 하이퍼바이저`라고도 불립니다.

### 주요 특징
- `하드웨어 직접 제어`: CPU, 메모리, 스토리지 등 물리적 리소스에 직접 접근하여 가상 머신에 할당합니다.
- `운영체제 불필요`: 별도의 호스트 운영체제 없이 하이퍼 바이저 자체가 OS 역할을 하며, 하드웨어 위에 바로 설치 됩니다.
- `성능 및 안정성`: 중간에 운영체제가 없으므로 성능이 뛰어나고, 보안성·안정성도 높습니다.
- `격리성`: 각 가상 머신이 높은 수준으로 격리되어, 보안과 장애 대응에 유리합니다.
- `관리 복잡성`: 설치와 관리가 비교적 복잡하며, 시스템 관리자 수준의 전문 지식이 필요합니다.
- `주요 활용처`: 데이터 센터, 클라우드 인프라, 대규모 서버 가상화 등 기업용 환경에 주로 사용됩니다.

### 대표적인 제품
- VMware ESXi
- Mirosoft Hyper-V
- KVM
- Xen

## 2형 하이퍼바이저
---
`2형 하이퍼바이저`는 호스트 운영체제 위에서 애플리케이션 형태로 설치되어 실행되는 가상화 소프트웨어입니다. `호스트형 하이퍼바이저(Hosted Hypervisor)` 또는 `내장형 하이퍼바이저`라고도 부릅니다.

### 주요 특징
- `운영체제 위 실행`: 이미 설치된 운영체제(Windows, macOS, Linux 등) 위에서 일반 프로그램처럼 동작합니다.
- `간편한 설치와 사용`: 별도의 시스템 관리자 지식 없이도 손쉽게 설치하고 사용할 수 있습니다
- `호스트 OS와 자원 공유`: 가상 머신이 사용하는 CPU, 메모리, 디스크 등 리소스를 호스트 운영체제와 공유합니다.
- `성능 오버헤드`: 하드웨어 접근이 운영체제를 거치므로 1형 하이퍼바이저에 비해 성능이 다소 떨어질 수 있습니다.
- `주요 활용처`: 개인용 PC, 개발 테스트 환경, 교육용, 여러 운영체제 동시 사용 등 비교적 소규모 환경에 적합합니다.

### 대표적인 제품
- VMware Workstaion
- Oracle VirtualBox
- Parallels Desktop
- VMware Fusion
- UTM

아래는 대표적인 하이퍼바이저들에 대한 설명입니다. 뒤에 이 있으면 mac에서 사용이 가능하다는 표시입니다.

### VMware Workstation  / VMware Fusion ()
---


### Oracle VirtualBox
---


### Parallels Desktop ()
---


### UTM ()
---


## 경량 가상화
---
`경량 가상화`는 기존의 전통적인 가상화(하이퍼바이저 기반의 VM)보다 적은 자원과 오버해드로, 여러 격리된 환경을 하나의 운영체제 또는 하드웨어 위에서 실행할 수 있게 하는 기술입니다. 커널은 공유하지만 실행 환경만을 격리하는 방식이라고 할 수 있습니다.

### WSL2
---
`WSL2 (Windows Subsystem for Linux 2 이하 WSL)`는 Windows에서 Hyper-V 기반의 리눅스 커널을 이용하여 리눅스 배포판(Ubuntu, Debian, Kali Linux 등)을 실행할 수 있게 도와주는 경량 가상화 환경입니다.

```
[Windows OS]
   │
   ├── WSL2 런타임
   │     ├── Hyper-V 기반 경량 가상 머신
   │     │     └── 리눅스 커널 (Microsoft 유지)
   │     │           └── Ubuntu / Kali / Debian 등 배포판
   │
   └── Windows와 파일/네트워크 통합
```

WSL의 구조는 위와 같습니다.
커널은 Microsoft가 직접 관리하는 리눅스 LTS 기반이고, 커널은 분리되어 있음에도 윈도우와의 통합(파일, 포트 등 공유)이 탁월합니다.

#### 설치 방법
1. WSL 활성화
	- "Windows 기능 켜기/끄기" (Windows 검색창에 입력)를 실행합니다.
	- "Linux용 Windows 하위 시스템"을 체크하고 "확인"을 클릭합니다.
	- 컴퓨터를 다시 시작합니다.
2. Linux 배포판 설치
	- Microsoft Store를 엽니다.
    - 원하는 Linux 배포판 (예: Ubuntu, Debian)을 검색하고 설치합니다.
    - 설치 후, 배포판을 실행하면 사용자 계정 및 비밀번호를 설정하는 과정이 진행됩니다.
3. WSL 실행
	- 설치한 Linux 배포판을 시작 메뉴에서 찾아 실행하거나,
    - 명령 프롬프트(cmd) 또는 PowerShell에서 `wsl` 명령어를 입력하여 기본 배포판을 실행합니다.
    - 명령 프롬프트(cmd) 또는 PowerShell에서 `wsl -l` 명령어를 입력하여 배포판 종류를 확인합니다.
    - 특정 배포판을 실행하려면 `wsl -d <배포판 이름>` (예: `wsl -d Ubuntu`)을 사용합니다.

### 활용 사례
- `개발`
- `보안 실습`
- `데이터 분석`
- `서버 테스트`
- `Docker`

### Docker
---
`Docker`는 컨테이너 기술을 사용할 수 있도록 해주는 도구/애플리케이션입니다. 이를 통해 개발자는 리눅스 컨테이너를 빌드, 실행, 관리 할 수 있습니다.

`컨테이너`는 애플리케이션과 그 실행에 필요한 모든 환경(코드, 라이브러리, 설정 등)을 하나로 묶어, 다른 컴퓨터에서도 동일한 환경에서 실행할 수 있도록 해주는 경량 가상화 기술입니다.
컨테이너는 호스트 운영체제의 커널을 공유하면서도, 서로 독립적으로 실행되기 때문에, 애플리케이션 간 실행 환경을 효과적으로 분리할 수 있습니다.

```
[하드웨어]
   ↓
[호스트 OS (Linux)]
   ↓
[컨테이너 엔진 (Docker)]
   ↓
[컨테이너 A] → Nginx + 설정 + 코드
[컨테이너 B] → Python + Flask + DB
```

컨테이너의 구조는 위와 같습니다.

#### 설치 방법
##### Windows
1. [Docker Desktop 공식 웹사이트](https://www.docker.com/products/docker-desktop/)에서 환경에 맞는 설치 파일 다운로드
2. `Docker Desktop Installer.exe` 파일 실행하고 설치 마법사 안내에 따라 설치 진행
3. 설치 완료 후 시스템 재부팅
4. 첫 실행 시 WSL2 backend 사용 여부 확인 → 사용 권장

- 설치 시 주의 사항
	- Hyper-V 및 WSL2 활성화 필요
	- BIOS에서 가상화(Virtualization) 기능이 켜져 있어야 함

##### macOS
- Homebrew로 설치하는 방법
	```bash
	brew install --cask docker
	open -a Docker # 도커 앱 실행
	```

- Docker 공식 설치 패키지 사용
	1. [Docker Desktop 공식 웹사이트](https://www.docker.com/products/docker-desktop/)에서 환경에 맞는 설치 파일 다운로드
	2. `Docker.dmg` 파일을 실행하여 Docker를 Application 폴더로 드래그 하여 설치

##### Linux
1. 저장소 설정 및 설치
	```bash
	sudo apt update
	sudo apt install \
	    ca-certificates \
	    curl \
	    gnupg \
	    lsb-release
	
	# Docker 공식 GPG 키 추가
	sudo mkdir -p /etc/apt/keyrings
	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
	sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
	
	# Docker 저장소 추가
	echo \
	"deb [arch=$(dpkg --print-architecture) \
	signed-by=/etc/apt/keyrings/docker.gpg] \
	https://download.docker.com/linux/ubuntu \
	$(lsb_release -cs) stable" | \
	sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
	
	# Docker 설치
	sudo apt update
	sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
	```

2. Docker 권한 설정 (옵션)
	```bash
	# 현재 사용자를 docker 그룹에 추가
	sudo usermod -aG docker $USER
	# 적용을 위해 재로그인 필요
	```


## 에뮬레이션
---
`에뮬레이션(Emulation)`은 하나의 시스템(하드웨어 또는 소프트웨어)이 다른 시스템처럼 동작하도록 흉내 내는 기술입니다.  

예를 들어, ARM 기반의 macOS에서 x86_64 아키텍처를 소프트웨어적으로 에뮬레이션한 뒤, 그 위에 리눅스 운영체제를 가상 머신 형태로 실행할 수 있습니다.  

이러한 방식은 CPU 구조가 다른 환경에서 소프트웨어를 호환시키기 위한 대표적인 예시입니다.

에뮬레이션의 기본 구조는 다음과 같습니다.
```
[ARM 기반 하드웨어]  
   ↓
[macOS (호스트 운영체제)]  
   ↓
[에뮬레이터 (예: QEMU, UTM)]  
   ↓
[x86_64 아키텍처로 작동하는 가상 머신 환경]  
   ↓
[게스트 OS: x86 기반 Linux]
```

### QEMU


### UTM ()



# 가상 환경

`가상환경`은 하나의 운영체제 내에서 특정 개발 언어난 실행 환경의 라이브러리, 설정, 패키지를 독립적으로 관리하기 위한 공간입니다. 운영체제 전체를 가상화하지 않고, 주로 개발 환경(언어, 라이브러리, 실행 설정 등)을 격리하는 경량화된 가상화 기술입니다.