# 검증 결과 — Fn 맨 윗줄 F1~F12

- Studio: [Actions #41](https://github.com/cherrytomato1/modu-c-zmk-config/actions/runs/35221176021), commit 89681a619b07190f7dc59185c5de9d3b6ce6f36f, success.
- 일반: [Actions #40](https://github.com/cherrytomato1/modu-c-zmk-config/actions/runs/35221173023), commit 420394469f12cd572c2cabc5b9834bc5054315b3, success.
- 각 직전 버전(#38/#39) 대비 레이어2의 위치0..11만 F1..F12로 변경. 다른 키맵 내용 동일 확인.
- 정적 검사, HEX/UF2 패키징 검사 및 Studio 회귀 테스트12개 통과.
- 두 실제 왼쪽 빌드의 Devicetree에서 위치0..11이 F1~F12(HID 0x7003a~0x70045)임을 확인. 나머지55개 Fn 바인딩은 이전 실제 빌드와 동일.
- JKL; 방향키, QWERT 기호, Fn+F/G 전환, 기본 Esc, Command 홀드/콤보와 관리 레이어 유지.
- Studio 오른쪽 UF2는 이전 #39와 동일. 일반 오른쪽 UF2는 이전 #38과 동일.
- 네 UF2의 구조/family/block/address 검증 통과.

| 파일 | SHA-256 |
| --- | --- |
| Studio left | a682499afe829b3df86f6215a1206dc9db3f61e0b55e61fba00e22af80fb9bcb |
| Studio right | 2e0ff14833be1f462a80891f8f6b764702b0040879c1096b8cab701d52302b63 |
| 일반 left | 911fbeb9e3dcd0ab36a29d0efdc10970764b43fac2ed9a060364f15414cceed0 |
| 일반 right | f14416b13da19acd301d96af596f1779904e80e31cc049e2d543ecf084b8a5de |

실제 기기 설치/입력/Studio 저장 시험은 아직 진행하지 않았습니다. Windows에서 안내서의 완료 체크를 수행합니다.
