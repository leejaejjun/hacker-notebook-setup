# Docker (Linux 환경)

## 설명

Docker는 컨테이너 기반의 가상화 플랫폼으로, 애플리케이션을 개발, 배포, 실행하는 데 사용되는 오픈 소스 도구입니다. Docker를 사용하면 애플리케이션과 그 종속성을 컨테이너라는 격리된 환경에 패키징하여, 어느 환경에서든 동일하게 실행할 수 있습니다.

## 설치 영역

`/usr/bin/docker` (일반적인 Docker 바이너리 위치)
`/var/lib/docker` (컨테이너, 이미지, 볼륨 등의 데이터 저장 위치)

## 사용처

- **애플리케이션 개발 및 배포:** 개발 환경과 운영 환경의 차이로 인한 문제를 해결하고, 애플리케이션을 쉽고 빠르게 배포합니다.
- **마이크로서비스 아키텍처:** 각 마이크로서비스를 독립적인 컨테이너로 배포하여, 확장성과 유지보수성을 향상시킵니다.
- **지속적 통합 및 지속적 배포 (CI/CD):** 빌드, 테스트, 배포 과정을 자동화하여, 개발 속도를 높이고 안정성을 확보합니다.
- **데이터베이스 및 기타 서비스:** MySQL, PostgreSQL, Redis 등 다양한 서비스를 컨테이너로 쉽게 실행하고 관리합니다.
- **머신러닝 및 데이터 과학:**  재현 가능한 실험 환경을 구축하고, 모델 배포를 간소화합니다.

## 설치(접속) 방법

1. **Linux 배포판에 맞는 Docker 설치:**
   - 대부분의 Linux 배포판 (Ubuntu, CentOS, Fedora 등)은 패키지 관리자를 통해 Docker를 쉽게 설치할 수 있습니다.
   - 예시 (Ubuntu):
     ```bash
     sudo apt update
     sudo apt install apt-transport-https ca-certificates curl software-properties-common
     curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
     echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
     sudo apt update
     sudo apt install docker-ce docker-ce-cli containerd.io
     ```
    -  CentOS/Fedora 등 다른 배포판은 공식 Docker 문서를 참조하여 설치합니다.

2. **Docker 서비스 시작 및 확인:**
   - Docker 서비스를 시작하고 시스템 부팅 시 자동 시작되도록 설정합니다.
     ```bash
     sudo systemctl start docker
     sudo systemctl enable docker
     ```
   - Docker 서비스 상태를 확인합니다.
     ```bash
     sudo systemctl status docker
     ```
   - Docker 버전 및 정보를 확인합니다.
      ```bash
      docker version
      docker info
      ```
3. **(선택) `sudo` 없이 Docker 명령어 실행 (권장):**
    - `docker` 그룹에 현재 사용자를 추가하여 `sudo` 없이 Docker 명령어를 실행할 수 있도록 합니다.
      ```bash
      sudo usermod -aG docker $USER
      ```
    -  *주의*:  새 그룹 설정을 적용하려면 로그아웃 후 다시 로그인하거나, 새 셸을 시작해야 합니다.  `newgrp docker` 명령어로 즉시 적용할 수도 있지만,  터미널 세션에만 적용됩니다.

## 접속 화면

Docker 자체는 CLI (Command-Line Interface) 도구이므로, 별도의 GUI 접속 화면은 없습니다.  명령어를 통해 컨테이너를 실행하고 관리합니다.

예시:  `hello-world` 컨테이너 실행

```bash
docker run hello-world
```

![hello-world 출력](hello-world.png)
(hello-world.png 는 실제로 hello-world 컨테이너를 실행했을 때 출력되는 텍스트를 캡쳐한 이미지입니다.)

Docker Desktop (GUI 도구)을 설치하면, 컨테이너, 이미지 등을 시각적으로 관리할 수 있습니다. 하지만 Docker Desktop은 리소스를 많이 사용하므로, 서버 환경에서는 주로 CLI를 사용합니다.

## 주의 사항

- **루트 권한:** Docker 데몬은 기본적으로 루트 권한으로 실행됩니다.  `sudo` 없이 Docker 명령어를 실행하려면 사용자를 `docker` 그룹에 추가해야 하지만, 이는 보안상 신중하게 고려해야 합니다. `docker` 그룹은 루트 권한과 동등합니다.
- **컨테이너 보안:** 컨테이너 이미지는 신뢰할 수 있는 출처에서 가져와야 합니다.  알 수 없는 이미지를 실행하면 시스템 보안이 위험해질 수 있습니다.  이미지 취약점 스캔 도구를 사용하는 것이 좋습니다.
- **리소스 관리:** 컨테이너는 호스트 시스템의 리소스 (CPU, 메모리 등)를 공유합니다.  컨테이너에 적절한 리소스 제한을 설정하여, 호스트 시스템의 성능 저하를 방지해야 합니다.
- **데이터 영속성:** 컨테이너는 기본적으로 임시적입니다.  컨테이너가 삭제되면 컨테이너 내부의 데이터도 함께 삭제됩니다.  데이터를 영구적으로 유지하려면 볼륨 (Volumes) 또는 바인드 마운트 (Bind Mounts)를 사용해야 합니다.
- **네트워킹:** 컨테이너는 기본적으로 격리된 네트워크 환경에서 실행됩니다.  컨테이너 간 통신 또는 외부와의 통신을 위해서는 네트워크 설정을 구성해야 합니다.

## 관련 URL

- **Docker 공식 문서:** [https://docs.docker.com/](https://docs.docker.com/)
- **Docker Hub:** [https://hub.docker.com/](https://hub.docker.com/) (컨테이너 이미지 저장소)
- **Docker 설치 가이드 (Ubuntu):** [https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)
- **Docker 설치 가이드 (CentOS):** [https://docs.docker.com/engine/install/centos/](https://docs.docker.com/engine/install/centos/)
- **Docker Desktop:** [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)
