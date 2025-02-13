# foundry

## 설명
Foundry는 이더리움 스마트 컨트랙트를 개발하고 테스트할 수 있는 강력한 개발 도구 모음입니다. Solidity 기반 스마트 컨트랙트를 컴파일, 배포, 테스트 및 디버깅하는 데 사용되며, 빠른 속도와 강력한 기능을 제공합니다.

## 설치 영역
`~/.foundry`

## 사용처
사용처|	설명
---|---
스마트 컨트랙트 개발|	Solidity 기반 개발, Hardhat보다 빠름
테스트 자동화	|Solidity로 직접 테스트 코드 작성 가능
배포|	forge script로 메인넷, 테스트넷 배포
온체인 데이터 조회	|cast로 블록체인 정보 조회 및 트랜잭션 실행
메인넷 포킹	|anvil로 로컬 환경에서 실전 테스트 가능
보안 테스트	|퍼즈 테스트, 프라퍼티 기반 테스트 지원
개발 효율화	|빠른 빌드, 배포 및 상호작용 지원


## 설치(접속) 방법
1. **CURL를 통한 설치 (권장):**
   ```bash
   curl -L https://foundry.paradigm.xyz | bash
   ```
   



## 접속 화면
mac-foundry는 주로 커맨드 라인 인터페이스 (CLI) 도구이므로, 별도의 GUI 접속 화면은 없습니다.  대신, 터미널에서 명령어를 실행하여 사용합니다.  명령어 실행 결과는 터미널에 출력됩니다.

![터미널에서 mac-foundry help 명령어 실행 결과](mac-foundry-help.png) *<-- 이 이미지는 예시입니다. 실제 mac-foundry help 실행 결과 스크린샷으로 대체해야 합니다.*

## 주의 사항
- **Apple Developer 계정 필요:** 코드 서명 및 노타리제이션을 위해서는 유효한 Apple Developer 계정과 인증서가 필요합니다.
- **Xcode 설치:** Xcode와 Command Line Tools가 설치되어 있어야 합니다.
- **프로젝트 설정:**  mac-foundry를 사용하기 전에 Xcode 프로젝트의 설정을 올바르게 구성해야 합니다 (Bundle Identifier, Version, Build Number 등).
- **Sparkle 설정 (선택 사항):** Sparkle 업데이트를 사용하려면, `Info.plist`에 Sparkle 관련 키를 추가하고, 앱캐스트 피드(appcast feed)를 호스팅해야 합니다.
- **mac-foundry.yaml 설정:** 프로젝트 루트에 mac-foundry.yaml 파일을 생성하여 빌드 및 배포 설정을 지정하는 것이 좋습니다.  (선택 사항이지만 권장됨)

## 관련 URL
- **mac-foundry GitHub 저장소:** [https://github.com/mac-foundry/mac-foundry](https://github.com/mac-foundry/mac-foundry)
- **Sparkle 프레임워크:** [https://sparkle-project.org/](https://sparkle-project.org/)
- **Apple Developer Documentation:** [https://developer.apple.com/documentation/](https://developer.apple.com/documentation/)
- **Notarizing macOS Software Before Distribution:** [https://developer.apple.com/documentation/security/notarizing_macos_software_before_distribution](https://developer.apple.com/documentation/security/notarizing_macos_software_before_distribution)

**참고:** 위 내용은 mac-foundry의 일반적인 사용법과 설치 방법을 설명합니다.  최신 정보 및 자세한 내용은 mac-foundry GitHub 저장소의 README 파일과 문서를 참조하세요.  `mac-foundry-help.png` 이미지는 첨부되어있지 않으므로, 실제로 `mac-foundry help` 명령어를 실행하여 스크린샷을 찍은 후 첨부해주세요.
