# GEF (GDB Enhanced Features)

## 설명

GDB의 기능을 확장하여 디버깅을 더 효율적으로 수행할 수 있도록 도와주는 도구.

## 사용처

- 리버스 엔지니어링
- 디버깅 자동화

## 설치 방법

1. **GEF 설치:**
   ```bash
   wget -O ~/.gdbinit-gef.py https://gef.blah.cat/py
   echo "source ~/.gdbinit-gef.py" >> ~/.gdbinit
   ```
2. **설치 확인:**
   ```bash
   gdb
   ```
   GDB 실행 후, GEF 로고가 표시되면 정상 설치됨.

## 주요 기능

- **`gef config`** : GEF 설정 변경
- **`heap-analysis-helper`** : 힙 구조 분석
- **`context`** : 실행 중인 프로그램 상태 요약 제공
- **`gef-help`** : 사용 가능한 명령어 목록 확인

## 관련 URL

[GEF 공식 문서](https://github.com/hugsy/gef)

