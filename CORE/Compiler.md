---
tags:
  - "#core"
---
# Compiler & Interpreter
---
`컴파일러`는 사람이 이해하기 쉬운 고급 프로그래밍 언어(예: C, Java 등)로 작성된 소스 코드를 컴퓨터가 이해할 수 있는 기계어(0과 1) 또는 저수준 언어(예: 어셈블리어)로 변환하는 소프트웨어입니다. 이 변환 과정을 컴파일이라고 합니다.

컴파일러는 다음과 같은 역할을 수행합니다:
- 소스 코드의 문법 오류를 검사
- 최적화를 수행해 효율적인 실행 파일(바이너리)을 생성
- 생성된 실행 파일은 운영체제에서 직접 실행 가능

반면, `인터프리터`는 소스 코드를 한 줄씩 읽고 즉시 해석하여 실행하는 프로그램 또는 실행 환경입니다.  
컴파일러는 실행 파일을 미리 생성하지만, 인터프리터는 소스 코드를 실행 시점에 실시간으로 번역 및 실행합니다.

| 구분    | 컴파일러                  | 인터프리터              |
| ----- | --------------------- | ------------------ |
| 번역 시점 | 실행 전 전체 번역 후 실행 파일 생성 | 실행 시 한 줄씩 해석하며 실행  |
| 실행 파일 | 생성함                   | 생성하지 않음            |
| 실행 속도 | 빠름 (이미 번역된 파일 실행)     | 느림 (매번 해석)         |
| 대표 언어 | C, C++, Java 등        | Python, JS, Ruby 등 |
프로그래밍 언어는 크게 컴파일 방식 언어와 인터프리터 방식 언어로 나눌 수 있습니다.
- **컴파일러 언어** 예시: C, C++
- **인터프리터 언어** 예시: Python, JavaScript

컴파일러는 언어마다 다양한 종류가 있으며, C/C++ 언어의 대표적인 컴파일러로는 `gcc`와 `clang`이 있습니다.  
아래는 Ubuntu 22.04 환경에서 `C`, `Python`, `Java`를 이용한 간단한 예제입니다.

## Simple Example
### C

1. 간단한 C 소스 코드를 준비합니다.
```c
//hello.c
#include <stdio.h>

int main()
{
	printf("Hello World!\n");

	return 0;
}
```

2. gcc를 이용하여 컴파일을 진행합니다.
```bash
gcc -o hello hello.c
```

3. 컴파일 후 실행 및 `file` 명령어로 파일 정보를 확인합니다.
```bash
# hello 실행
ubuntu@ubuntu:~$ ./hello
Hello World!

# file 명령어로 파일 정보 확인
ubuntu@ubuntu:~$ file hello
hello: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=b74da2c9c77d221eeaa98f87f4a7a529782db280, for GNU/Linux 3.2.0, not stripped
```

### Python
1. 간단한 Python 소스코드를 준비합니다.
```python
#hello.py
print("Hello Python!")
```

2. `hello.py` 파일을 실행합니다.
```bash
ubuntu@ubuntu:~$ python3 hello.py
Hello Python!
```
> ⚠️ Python은 실행 전 컴파일 과정이 없으며, 문법 오류가 있다면 실행 시점에 바로 오류가 발생합니다.

### Java
- 컴파일
1. 간단한 Java 소스코드를 준비합니다.
```java
public class hello {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

2. javac를 이용하여 컴파일을 진행합니다.
```bash
javac hello.java
```
	→ 이때 hello.class 파일이 생성됩니다.(JVM용 바이트 코드)

3. 컴파일 된 hello를 실행시킵니다.
```bash
ubuntu@ubuntu:~$ java hello
Hello, Java!
```

- 인터프리터
1. 간단한 Java 소스코드를 준비합니다. (Java 컴파일 과정 1번과 동일한 소스코드)
2. java를 이용하여 hello.java를 실행합니다.
```bash
ubuntu@ubuntu:~$ java hello.java
Hello, Java!
```

# Compiler Framework
---
## MinGW
<!--추후 업데이트-->

## LLVM
<!--추후 업데이트천-->

# Cross Compiler
---
`크로스 컴파일러(Cross Compiler)`는 컴파일러가 실행되는 플랫폼(호스트)과 실행 파일이 동작할 플랫폼(타겟)이 서로 다를 때 사용되는 컴파일러입니다.

예를 들어, 개발자가 사용하는 컴퓨터가 x86_64 리눅스 환경일 때, ARM 기반 임베디드 시스템이나 Windows에서 실행될 프로그램을 만들고자 한다면 크로스 컴파일러가 필요합니다.

크로스 컴파일러는 다음과 같은 상황에서 유용합니다:
- 타겟 시스템에 직접 컴파일 환경이 없는 경우
- 다른 아키텍처용 바이너리를 미리 빌드해야 하는 경우
- 리눅스에서 Windows 실행 파일을 생성하는 경우 등

아래는 Ubuntu 22.04 환경에서 `mingw-w64`를 사용해 Windows용 `.exe` 실행 파일을 크로스 컴파일하는 예시입니다.

## Simple Example
1. 우선 `mingw-w64`를 설치해 윈도우 실행파일(.exe)를 컴파일할 준비를 합니다.
```bash
sudo apt install mingw-w64
```

2. 간단한 C 소스코드를 준비합니다.
```c
#include <stdio.h>

int main()
{
	printf("Hello World!\n");

	return 0;
}
```

3. `mingw-w64`를 이용하여 윈도우용 실행 파일로 컴파일합니다.
```bash
x86_64-w64-mingw32-gcc -o hello hello.c
```

4. 컴파일 후 실행 및 `file` 명령어로 생성된 파일 정보를 확인합니다.
```bash
# hello 실행
ubuntu@ubuntu:~$ ./hello
-bash: ./hello.exe: cannot execute binary file: Exec format error

# file 명령어로 파일 정보 확인
ubuntu@ubuntu:~$ file hello
hello.exe: PE32+ executable (console) x86-64, for MS Windows
```

`hello.exe` 파일은 **PE32+ 형식의 Windows 실행 파일**이므로 리눅스에서는 직접 실행할 수 없습니다.

하지만 이 파일을 Windows 환경으로 옮겨 실행하면 **정상적으로 작동하는 것을 확인할 수 있습니다.

# Debugging & Debugger
---
`디버깅`은 소프트웨어 개발 과정에서 버그(Bug)를 찾아내고, 그 원인을 분석하며, 이를 해결하는 일련의 과정입니다. 프로그램이 예상대로 동작하지 않을 때, 문제의 원인을 규명하고 수정하는 작업이 디버깅에 해당합니다.

`디버거`는 이러한 디버깅 작업을 지원하는 전문 도구로, 개발자가 프로그램의 실행 흐름을 직접 제어하고, 특정 지점에서 실행을 중단하거나 변수의 값을 실시간으로 확인할 수 있도록 도와줍니다.

또한 보안의 관점에서는 디버거를 통해 바이너리(프로그램)의 내부 동작을 추적하고, 메모리 구조와 로직, 취약한 지점을 정밀하게 분석하여, 취약점 분석과 익스플로잇 개발까지 수행할 수 있는 기술과 도구입니다.

주요 기능으로는 다음과 같습니다.
- 중단점(Breakpoint) 설정: 코드의 특정 위치에서 실행을 일시 중지
- 단계별 실행(Step Execution): 한 줄씩 코드를 실행하며 동작을 관찰
- 변수 및 메모리 검사: 변수 값, 메모리 상태를 실시간 확인
- 콜 스택(Call Stack) 확인: 함수 호출 순서와 실행 경로 추적
- 고급 기능: 메모리 누수 감지, 다중 스레드 디버깅 등

대표적인 디버거들로 `gdb`, `WinDbg`, `x64dbg`, `LLDB` 등이 있습니다.

## GDB (GNU Debugger)
---
`GDB`는 GNU 프로젝트에서 개발한 대표적인 오픈소스 디버거로, 주로 Linux/Unix 환경에서 C, C++, Fortran 등 다양한 언어의 프로그램을 디버깅하는데 사용됩니다.

특징
- 명령줄 기반 동작
- IDE 연동 가능
- 원격 디버깅과 같은 고급 기능 지원

## WinDbg (Windows Debugger)
---
`WinDbg`는 마이크로소프트에서 제공하는 윈도우 전용 디버거로, 사용자 모드 애플리케이션, 커널모드 드라이버, 운영체제 자체의 디버깅까지 지원합니다.

특징
- GUI 및 CLI 모두 지원
- 윈도우 시스템 내부 분석
- 블루스크린(BSOD)분석

## x64dbg / x32dbg
---
`x64dbg`는 윈도우 환경에서 32비트 및 64비트 실행 파일을 분석/디버깅 할 수 있는 오픈소스 디버거입니다.

특징
- 오픈소스
- 커뮤니티 지원 활발

## LLDB (LLVM Debugger)
---
`LLDB`는 LLVM 프로젝트의 공식 디버거로 C, C++, Objective-C, Swift 등 다양한 언어를 지원하며 macOS, Linux, Windows 등 여러 플랫폼에서 동작합니다.

특징
- Xcode의 기본 디버거
- 성능 및 확장성 우수
- LLVM/Clang 생태계와 긴밀히 통합
