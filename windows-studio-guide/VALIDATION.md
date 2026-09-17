# 검증 결과 — J/K/L/세미콜론 방향키와 왼쪽 기호열

- Studio: [Actions #39](https://github.com/cherrytomato1/modu-c-zmk-config/actions/runs/35220618580), commit bd6524cd6ee7a13207ac78498c1da812db46f927, success.
- 일반: [Actions #38](https://github.com/cherrytomato1/modu-c-zmk-config/actions/runs/35220614649), commit 2230517c9f96523d1e6b6648f5fb053f2e70bce2, success.
- 기존 #34/#35 대비 레이어2 바인딩17개만 변경. 다른3개 레이어, Command 홀드 동작, 콤보 정의 완전동일 확인.
- 두 소스의 정적 검사 및 HEX/UF2 패키징 보호 검사 통과. Studio 구성 회귀 테스트12개 통과.
- 두 빌드의 실제 왼쪽 Devicetree에서 위치31/32/33/34가 Left/Down/Up/Right인 것을 확인.
- 실제 왼쪽 Devicetree에서 위치13..17이 MINUS/EQUAL/LEFT_BRACKET/RIGHT_BRACKET/SQT인 것을 확인.
- Home(S), Mac 전환(F), Windows 전환(G), 관리 레이어 접근(Ctrl)도 실제 왼쪽 Devicetree에서 확인.
- 기존 Command Backspace 및 combo_command_space가 실제 왼쪽 빌드에 남아 있음.
- Studio 오른쪽 UF2는 기존 #35와 동일. 일반 오른쪽 UF2는 기존 #34와 동일.
- 네 UF2의 구조/family/block/address 검증 통과.

| 파일 | SHA-256 |
| --- | --- |
| Studio left | e629786db52fecec68af6d8c0dd3159d9067b3bfb8abae8cb8e50c902f20f0c4 |
| Studio right | 2e0ff14833be1f462a80891f8f6b764702b0040879c1096b8cab701d52302b63 |
| 일반 left | 2aeb9ed72062904f4e24b04f3bf0790135a56ba39d664883e6141265a5deb973 |
| 일반 right | f14416b13da19acd301d96af596f1779904e80e31cc049e2d543ecf084b8a5de |

Studio: left1089블록, right783블록. 일반: left985블록, right780블록.

실제 기기 설치/입력/Studio 저장 시험은 아직 진행하지 않았습니다. Windows에서 안내서의 완료 체크를 수행합니다.
