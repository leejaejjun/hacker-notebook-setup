# Visual Studio Code (Linux)

## 설명

Visual Studio Code (VS Code)는 마이크로소프트에서 개발한 소스 코드 편집기입니다.  Linux, macOS, Windows에서 실행 가능하며, 디버깅, 내장 Git, 구문 강조, 지능형 코드 완성, 스니펫, 코드 리팩토링 기능을 제공합니다.  다양한 프로그래밍 언어 및 프레임워크를 지원하며, 확장 프로그램을 통해 기능을 확장할 수 있는 강력하고 가벼운 편집기입니다.

## 설치 영역

`~/.config/Code` (설정 파일)
`/usr/share/code` (실행 파일 - 배포판에 따라 다를 수 있음)
`~/.vscode/extensions` (확장 프로그램)

## 사용처

- **다양한 프로그래밍 언어 개발:**  Python, JavaScript, C++, Java, Go, C#, PHP 등 거의 모든 언어의 개발 환경을 구성할 수 있습니다.
- **웹 개발:** HTML, CSS, JavaScript를 사용한 프론트엔드 개발 및 Node.js, Python (Django, Flask) 등을 이용한 백엔드 개발.
- **데이터 과학:** Python을 이용한 데이터 분석, 머신 러닝, 딥 러닝 프로젝트. (Jupyter Notebook 통합 지원)
- **클라우드 개발:**  Azure, AWS, Google Cloud 등 클라우드 플랫폼과의 연동 및 개발.
- **원격 개발:** SSH, Containers, WSL (Windows Subsystem for Linux)을 통한 원격 개발 환경 구축.
- **텍스트 편집:**  간단한 텍스트 파일이나 마크다운 문서 작성 및 편집.

## 설치(접속) 방법

1. **패키지 관리자를 이용한 설치 (권장):**
   * **Debian/Ubuntu 계열:**
     ```bash
     sudo apt update
     sudo apt install software-properties-common apt-transport-https curl
     curl -sSL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /usr/share/keyrings/vscode.gpg > /dev/null
     echo "deb [arch=amd64 signed-by=/usr/share/keyrings/vscode.gpg] https://packages.microsoft.com/repos/vscode stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
     sudo apt update
     sudo apt install code
     ```
   * **Red Hat/Fedora/CentOS 계열:**
     ```bash
     sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
     sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
     sudo dnf check-update  # Fedora
     # or
     sudo yum check-update  # CentOS/RHEL
     sudo dnf install code   # Fedora
     # or
     sudo yum install code   # CentOS/RHEL
     ```
   * **Snap 패키지 (모든 배포판):**
     ```bash
     sudo snap install --classic code
     ```

2. **.deb 또는 .rpm 패키지 다운로드 후 설치:**  [Visual Studio Code 다운로드 페이지](https://code.visualstudio.com/download)에서 해당 리눅스 배포판에 맞는 `.deb` (Debian/Ubuntu 계열) 또는 `.rpm` (Red Hat/Fedora/CentOS 계열) 패키지를 다운로드하여 설치합니다.  (일반적으로 GUI 환경에서 더블 클릭하여 설치하거나, 터미널에서 `dpkg -i <package_name>.deb` 또는 `rpm -i <package_name>.rpm` 명령어를 사용합니다.)

3. **실행:**  설치 후, 애플리케이션 메뉴에서 "Visual Studio Code"를 찾아 실행하거나, 터미널에서 `code` 명령어를 입력하여 실행합니다.

## 접속 화면
![VS Code 초기화면](vscode_linux.png)
*(실제 접속 화면은 테마 및 설정에 따라 다를 수 있습니다. 위 이미지는 VS Code의 기본 다크 테마를 보여주는 예시입니다.  파일 탐색기, 편집 영역, 터미널, 상태 표시줄 등이 포함된 전형적인 모습을 나타냅니다.)*

## 주의 사항

- **확장 프로그램 설치 시 주의:**  신뢰할 수 없는 출처의 확장 프로그램은 보안 문제를 일으킬 수 있습니다.  공식 마켓플레이스에서 평판이 좋은 확장 프로그램을 설치하는 것이 좋습니다.
- **업데이트 확인:**  VS Code는 주기적으로 업데이트됩니다.  새로운 기능과 보안 패치를 받기 위해 정기적으로 업데이트를 확인하고 설치하는 것이 중요합니다. (`Help` -> `Check for Updates` 또는 패키지 관리자를 통해)
- **리소스 사용량:**  많은 확장 프로그램을 설치하거나 큰 프로젝트를 열 경우, 메모리 사용량이 증가할 수 있습니다.  시스템 성능에 영향을 미칠 수 있으므로, 불필요한 확장 프로그램은 비활성화하거나 제거하는 것이 좋습니다.
- **Git 설정:** 내장 Git 기능을 사용하려면 Git이 시스템에 설치되어 있고, 사용자 이름과 이메일이 설정되어 있어야 합니다. (`git config --global user.name "Your Name"`  및 `git config --global user.email "your.email@example.com"`).
- **키보드 단축키:** VS Code는 다양한 키보드 단축키를 제공합니다.  효율적인 사용을 위해 자주 사용하는 기능의 단축키를 익혀두는 것이 좋습니다. (`File` -> `Preferences` -> `Keyboard Shortcuts` 에서 확인 및 변경 가능)

## 관련 URL

- [Visual Studio Code 공식 웹사이트](https://code.visualstudio.com/)
- [Visual Studio Code 문서](https://code.visualstudio.com/docs)
- [Visual Studio Code Marketplace (확장)](https://marketplace.visualstudio.com/vscode)
- [Visual Studio Code on Linux](https://code.visualstudio.com/docs/setup/linux)
