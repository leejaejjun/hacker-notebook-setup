# 🔧 해킹 도구 설치 가이드

초보 해커들이 실습에 필요한 도구들을 손쉽게 설치하고 활용할 수 있도록 이 가이드를 제공합니다. 도구별 설명, 설치법, 주요 기능을 중심으로 정리했습니다.

---

## 📁 디렉토리 구조

- `CORE/`: 개발 환경 설정에 필요한 기본 도구들 (코드 에디터, 언어, 패키지 매니저 등)
- `Software hacking/`: 리버스 엔지니어링, 포렌식, 분석 도구 등 전문 해킹 도구 모음

---

## 📘 도구 분류별 전체 요약 (주요 기능 제외)

| 분류 | 도구명 | 지원 OS (M: macOS / W: Windows / L: Linux) | 권장 설치 |
|------|--------|---------------------------------------------|------------|
| CORE | [Code Editing Tools](CORE/Code Editing Tools.md) |  |  |
| CORE | [Compiler](CORE/Compiler.md) |  |  |
| CORE | [Language](CORE/Language.md) |  |  |
| CORE | [Package Management Tools](CORE/Package Management Tools.md) |  |  |
| CORE | [Virtual Enviroment](CORE/Virtual Enviroment.md) |  |  |
| Software hacking | [010Editor](Software hacking/010Editor.md) | M W |  |
| Software hacking | [ADB (Android Debug Bridge)](Software hacking/ADB (Android Debug Bridge).md) |  |  |
| Software hacking | [Android Studio AVD](Software hacking/Android Studio AVD.md) | M W L |  |
| Software hacking | [Autopsy](Software hacking/Autopsy.md) | M W L |  |
| Software hacking | [BrowsingHistoryView](Software hacking/BrowsingHistoryView.md) | W |  |
| Software hacking | [Burp Suite](Software hacking/Burp Suite.md) | M W L |  |
| Software hacking | [Cheat Engine](Software hacking/Cheat Engine.md) | M W |  |
| Software hacking | [Curl](Software hacking/Curl.md) | M W L |  |
| Software hacking | [CyberChef](Software hacking/CyberChef.md) |  |  |
| Software hacking | [DB Browser for SQLite](Software hacking/DB Browser for SQLite.md) | M W L |  |
| Software hacking | [DIE (Detect It Easy)](Software hacking/DIE (Detect It Easy).md) | M W L |  |
| Software hacking | [EnCase (유료)](Software hacking/EnCase (유료).md) | M W L |  |
| Software hacking | [ExifTool](Software hacking/ExifTool.md) | M W L |  |
| Software hacking | [FRIDA](Software hacking/FRIDA.md) | M W L |  |
| Software hacking | [FTK Imager](Software hacking/FTK Imager.md) | W |  |
| Software hacking | [Fiddler](Software hacking/Fiddler.md) | M W L |  |
| Software hacking | [GHIDRA](Software hacking/GHIDRA.md) | M W L |  |
| Software hacking | [Hex Fiend](Software hacking/Hex Fiend.md) | M |  |
| Software hacking | [HxD (Freeware Hex Editor and Disk Editor)](Software hacking/HxD (Freeware Hex Editor and Disk Editor).md) | W |  |
| Software hacking | [IDA Free](Software hacking/IDA Free.md) | M W L |  |
| Software hacking | [JADX](Software hacking/JADX.md) | M W L |  |
| Software hacking | [LNK Parser (보류 -> 종류가 다양함)](Software hacking/LNK Parser (보류 -> 종류가 다양함).md) | W |  |
| Software hacking | [NOX](Software hacking/NOX.md) | W |  |
| Software hacking | [NTFS Log Tracker](Software hacking/NTFS Log Tracker.md) | W |  |
| Software hacking | [Nmap](Software hacking/Nmap.md) | M W L |  |
| Software hacking | [NumPy](Software hacking/NumPy.md) | M W L |  |
| Software hacking | [OWASP ZAP (Zed Attack Proxy)](Software hacking/OWASP ZAP (Zed Attack Proxy).md) | M W L |  |
| Software hacking | [QEMU](Software hacking/QEMU.md) | M W L |  |
| Software hacking | [REGA](Software hacking/REGA.md) | W |  |
| Software hacking | [ROP Gadget](Software hacking/ROP Gadget.md) | M W L |  |
| Software hacking | [Remix IDE](Software hacking/Remix IDE.md) |  |  |
| Software hacking | [RustScan](Software hacking/RustScan.md) | M W L |  |
| Software hacking | [SHODAN](Software hacking/SHODAN.md) |  |  |
| Software hacking | [Sage Math](Software hacking/Sage Math.md) | M W L |  |
| Software hacking | [Volatility](Software hacking/Volatility.md) | M W L |  |
| Software hacking | [Webhook Tester](Software hacking/Webhook Tester.md) |  |  |
| Software hacking | [Windbg (Windows Debugger)](Software hacking/Windbg (Windows Debugger).md) | W |  |
| Software hacking | [Wireshark](Software hacking/Wireshark.md) | M W |  |
| Software hacking | [Z3 Solver](Software hacking/Z3 Solver.md) | M W L |  |
| Software hacking | [anvil](Software hacking/anvil.md) |  |  |
| Software hacking | [censys](Software hacking/censys.md) |  |  |
| Software hacking | [dnSpy](Software hacking/dnSpy.md) | W |  |
| Software hacking | [ether.js](Software hacking/ether.js.md) |  |  |
| Software hacking | [foundry](Software hacking/foundry.md) | M W L |  |
| Software hacking | [gdb](Software hacking/gdb.md) | L |  |
| Software hacking | [gef](Software hacking/gef.md) | L |  |
| Software hacking | [hardhat](Software hacking/hardhat.md) |  |  |
| Software hacking | [nc (netcat)](Software hacking/nc (netcat).md) | M W L |  |
| Software hacking | [ngrok](Software hacking/ngrok.md) |  |  |
| Software hacking | [postman](Software hacking/postman.md) | M W L |  |
| Software hacking | [pwndbg](Software hacking/pwndbg.md) | L |  |
| Software hacking | [pwntools](Software hacking/pwntools.md) | M W L |  |
| Software hacking | [rp++](Software hacking/rp++.md) | M W L |  |
| Software hacking | [sqlmap](Software hacking/sqlmap.md) | M W L |  |
| Software hacking | [web3.js](Software hacking/web3.js.md) |  |  |
| Software hacking | [x64dbg](Software hacking/x64dbg.md) | W |  |
