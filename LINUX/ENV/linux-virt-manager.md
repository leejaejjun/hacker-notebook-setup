## linux-virt-manager

# Virtual Machine Manager (virt-manager)

## 설명

Virtual Machine Manager (virt-manager)는 데스크톱 사용자 인터페이스를 통해 가상 머신을 관리하기 위한 응용 프로그램입니다.  libvirt 관리 API를 사용하여 KVM, Xen, QEMU 등과 같은 다양한 하이퍼바이저를 통해 실행되는 가상 머신을 생성, 구성, 시작, 중지 및 모니터링할 수 있습니다.  내장된 VNC 및 SPICE 클라이언트 뷰어를 통해 가상 머신의 그래픽 콘솔에 대한 접근을 제공합니다.

## 설치 영역

`대부분의 Linux 배포판 패키지 관리자 (apt, yum, dnf, pacman 등)`

## 사용처

- **서버 가상화:** 여러 운영 체제를 단일 물리적 서버에서 실행하여 리소스 활용도를 높이고 비용을 절감합니다.
- **개발 및 테스트 환경:** 다양한 운영 체제 및 소프트웨어 구성을 테스트하기 위한 격리된 환경을 제공합니다.
- **데스크톱 가상화:** 여러 데스크톱 환경을 단일 시스템에서 실행하여 작업 공간을 분리하거나 레거시 애플리케이션을 실행합니다.
- **교육 및 훈련:** 가상 머신을 사용하여 안전하고 제어된 환경에서 시스템 관리, 네트워킹 및 보안을 학습합니다.

## 설치(접속) 방법

1. **패키지 관리자를 사용하여 설치:**
   * Debian/Ubuntu 기반: `sudo apt update && sudo apt install virt-manager`
   * Fedora/CentOS/RHEL 기반: `sudo dnf install virt-manager`  (또는 `sudo yum install virt-manager`)
   * Arch Linux 기반: `sudo pacman -S virt-manager`
   * openSUSE: `sudo zypper install virt-manager`

2. **libvirtd 서비스 시작 및 활성화 (필요한 경우):**
   * `sudo systemctl start libvirtd`
   * `sudo systemctl enable libvirtd`

3. **애플리케이션 실행:**
   * 터미널에서 `virt-manager`를 입력하거나,  애플리케이션 메뉴에서 "Virtual Machine Manager"를 찾아 실행합니다.  (일반적으로 "시스템 도구" 또는 "관리" 카테고리에 있습니다.)

4. **(선택 사항) 사용자 그룹 추가:**
    *  `sudo usermod -aG libvirt $(whoami)` (현재 사용자를 libvirt 그룹에 추가)
    *  `sudo usermod -aG kvm $(whoami)` (현재 사용자를 kvm 그룹에 추가 - 필요한 경우)
    *  새 그룹 멤버십을 적용하려면 로그아웃했다가 다시 로그인하거나 새 쉘을 시작해야 합니다.

## 접속 화면

![virt-manager main window](virt-manager-main.png)
*virt-manager-main.png*  (이 파일은 virt-manager의 메인 창을 보여주는 스크린샷이어야 합니다.  연결된 하이퍼바이저와 가상 머신 목록을 표시합니다.)

![virt-manager virtual machine window](virt-manager-vm.png)
*virt-manager-vm.png* (이 파일은 실행 중인 가상 머신의 콘솔 창과 세부 정보 창을 보여주는 스크린샷이어야 합니다. CPU 사용량, 메모리 사용량, 디스크 I/O, 네트워크 트래픽 등의 정보를 표시합니다.)
(실제 이미지를 첨부하여야 합니다)

## 주의 사항

- **루트 권한:** virt-manager는 일반적으로 일반 사용자 권한으로 실행할 수 있지만, 일부 기능(예: 네트워크 브리지 생성)에는 루트 권한이 필요할 수 있습니다.  `sudo virt-manager`로 실행하는 것은 권장되지 않습니다. 대신 `polkit`을 통해 권한을 관리하는 것이 좋습니다.
- **하이퍼바이저 지원:** virt-manager는 다양한 하이퍼바이저를 지원하지만, 모든 기능이 모든 하이퍼바이저에서 동일하게 작동하는 것은 아닙니다.  사용 중인 하이퍼바이저의 설명서를 참조하세요.
- **원격 연결:** virt-manager를 사용하여 원격 호스트의 가상 머신을 관리할 수 있습니다.  원격 호스트에 SSH를 통해 연결하고 libvirtd 데몬이 실행 중인지 확인해야 합니다.
- **저장소 풀:** 가상 머신 이미지 파일을 저장할 위치 (저장소 풀)를 구성해야 합니다.  기본적으로 `/var/lib/libvirt/images`를 사용하지만, 다른 위치로 변경할 수 있습니다.
- **QEMU 사용자 세션:** `qemu:///session` URI를 사용하면 사용자 권한으로 가상 머신을 실행할 수 있습니다. 이는 보안을 강화하는 데 도움이 될 수 있지만, 일부 기능 (예: 호스트 장치에 직접 접근)은 제한될 수 있습니다.

## 관련 URL

- **libvirt 공식 웹사이트:** [https://libvirt.org/](https://libvirt.org/)
- **Virtual Machine Manager 프로젝트 페이지:** [https://virt-manager.org/](https://virt-manager.org/)
- **Red Hat Virtualization 문서 (virt-manager 관련 내용 포함):** [https://access.redhat.com/documentation/en-us/red_hat_virtualization/](https://access.redhat.com/documentation/en-us/red_hat_virtualization/)
- **Arch Wiki (virt-manager):** [https://wiki.archlinux.org/title/Virt-manager](https://wiki.archlinux.org/title/Virt-manager)
- **Ubuntu Community Help Wiki (KVM/VirtManager):** [https://help.ubuntu.com/community/KVM/VirtManager](https://help.ubuntu.com/community/KVM/VirtManager)
