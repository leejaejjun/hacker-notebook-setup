## linux-Python

## 설명

linux-Python은 Linux 환경에서 사용되는 Python 프로그래밍 언어 및 관련 도구들을 통칭하는 용어입니다. 특정 도구나 애플리케이션을 지칭하는 것이 아니라, Linux 운영체제에서 Python 개발 환경을 구축하고 사용하는 전반적인 내용을 의미합니다.

## 설치 영역

- `/usr/bin/python` (시스템 기본 Python 인터프리터)
- `/usr/lib/pythonX.Y` (표준 라이브러리, X.Y는 버전 번호)
- `/usr/local/lib/pythonX.Y/dist-packages` (pip 등으로 설치한 패키지)
- 사용자 홈 디렉토리 (개별 프로젝트 및 가상 환경)

## 사용처

- **웹 개발:** Django, Flask 등을 이용한 웹 애플리케이션 개발
- **데이터 분석 및 과학:** NumPy, Pandas, SciPy, Matplotlib 등을 활용한 데이터 처리, 분석, 시각화
- **머신 러닝 및 딥 러닝:** TensorFlow, PyTorch, Scikit-learn 등을 이용한 모델 개발 및 학습
- **시스템 자동화:** 스크립트를 통한 시스템 관리 작업 자동화
- **네트워크 프로그래밍:** 소켓 프로그래밍, 네트워크 관련 도구 개발
- **GUI 애플리케이션 개발:** Tkinter, PyQt 등을 이용한 데스크톱 애플리케이션 개발

## 설치(접속) 방법

1. **패키지 매니저를 이용한 설치:**
   - Debian/Ubuntu 계열: `sudo apt update && sudo apt install python3 python3-pip`
   - Fedora/CentOS/RHEL 계열: `sudo dnf install python3 python3-pip`
   - Arch Linux 계열: `sudo pacman -S python python-pip`

2. **소스 코드를 이용한 설치 (선택 사항):**
   - [Python 공식 웹사이트](https://www.python.org/downloads/)에서 소스 코드를 다운로드합니다.
   - 압축을 풀고, `./configure`, `make`, `sudo make install` 명령어를 차례로 실행합니다.

3. **가상 환경 생성 (권장):**
   - `python3 -m venv <가상환경이름>`  (가상 환경 생성)
   - `source <가상환경이름>/bin/activate` (가상 환경 활성화)
    - 가상환경을 사용하면 프로젝트별로 독립적인 Python 환경을 구성할 수 있어 패키지 충돌을 방지할 수 있습니다.

4. **터미널에서 Python 실행:**
   - `python3` (인터프리터 실행)
   - `python3 <스크립트파일이름>.py` (스크립트 실행)

## 접속 화면
![터미널에서 python3 실행](python_terminal.png)
*python_terminal.png 파일은 터미널에 `python3`를 입력하여 인터프리터가 실행된 화면을 캡처한 이미지라고 가정합니다.*

## 주의 사항

- **시스템 Python 사용 시 주의:** 시스템 Python (보통 `/usr/bin/python3`)에 직접 패키지를 설치하는 것은 권장하지 않습니다. 시스템 라이브러리와 충돌이 발생할 수 있으므로, 가상 환경을 사용하는 것이 좋습니다.
- **버전 관리:** 여러 버전의 Python이 설치되어 있는 경우, `python3.8`, `python3.9`와 같이 버전을 명시하여 사용할 수 있습니다.  `update-alternatives` (Debian/Ubuntu) 또는 `alternatives` (Fedora/CentOS/RHEL) 명령어를 사용하여 기본 Python 버전을 변경할 수 있습니다.
- **pip 사용 시 주의:**  `pip install` 시 `--user` 옵션을 사용하면 사용자 홈 디렉토리에 패키지를 설치할 수 있습니다.  시스템 전체에 영향을 주지 않고 패키지를 설치하는 방법입니다.
- **Shebang (`#!`)**:  Python 스크립트 파일의 첫 줄에 `#!/usr/bin/env python3`와 같이 Shebang을 추가하면, 스크립트를 `./<스크립트파일이름>.py`와 같이 직접 실행할 수 있습니다.

## 관련 URL

- [Python 공식 웹사이트](https://www.python.org/)
- [Python 튜토리얼 (한국어)](https://docs.python.org/ko/3/tutorial/)
- [점프 투 파이썬 (온라인 책)](https://wikidocs.net/book/1)
- [pip 공식 문서](https://pip.pypa.io/en/stable/)
- [venv 공식 문서](https://docs.python.org/3/library/venv.html)
