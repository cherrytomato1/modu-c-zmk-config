# 검증 결과 — Command 홀드 추가

- Studio: [Actions #35](https://github.com/cherrytomato1/modu-c-zmk-config/actions/runs/35213627868), commit 8175d9d32edae4dbbe7ce8d2a2ccc691071d9fd7, success.
- 일반: [Actions #34](https://github.com/cherrytomato1/modu-c-zmk-config/actions/runs/35213624641), commit 655179f832267e335b49efa65c1d96191a65b31a, success.
- 각 직전 소스 대비 기본0/1레이어 위치63만 cmd_bspc로 교체. 기존 콤보/나머지266개 레이어 바인딩 동일 확인.
- 양쪽 소스의 정적 검사, HEX/UF2 패키징 보호 검사 통과. Studio 구성 회귀 테스트12개 통과.
- 두 빌드의 실제 왼쪽 Devicetree에서 Command Backspace, BSPC(0x7002a)/SPACE(0x7002c), mods=keep-mods=0x8(LGUI), 두 기본레이어 배정 확인.
- 두 빌드의 실제 왼쪽 Devicetree에 기존 60+63 Command+Space 콤보(50ms)가 남아 있음.
- Studio 왼쪽 ZMK_STUDIO/LOCKING/UART 활성 유지 확인.
- Studio 오른쪽 UF2는 이전 #33과 byte 동일. 일반 오른쪽 UF2는 기존 #32와 byte 동일.
- 네 UF2의 구조/family/block/address 검증 통과.

| 파일 | SHA-256 |
| --- | --- |
| Studio left | c91759078ccbec5dbc6f58e7405f3cd48f2e6ceb457924fe02c069ac5b007cba |
| Studio right | 2e0ff14833be1f462a80891f8f6b764702b0040879c1096b8cab701d52302b63 |
| 일반 left | 63deeeb5ad5e16cf92c61e4ab3fba9c0165974c18f731ea1315135ba71264848 |
| 일반 right | f14416b13da19acd301d96af596f1779904e80e31cc049e2d543ecf084b8a5de |

Studio: left1089블록, right783블록. 일반: left985블록, right780블록.

실제 장치 설치, Command 홀드/동시 콤보 입력, Studio 연결/저장/재부팅은 아직 시험 전입니다. Windows에서 안내서의 완료 체크를 수행해야 합니다.
