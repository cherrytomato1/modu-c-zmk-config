# 검증 결과

커밋 b589c1b9e3f3d82ea4b4470deada6c56c99b6929 / Actions33 run35209802696 성공.

- 기존32번 키맵 대비 레이어3 R/T 두 바인딩만 변경, 콤보/나머지266개레이어바인딩 보존.
- Studio 구성회귀테스트12개,정적검사,HEX/UF2패키징보호검사통과.
- 실제left: ZMK_STUDIO,STUDIO_LOCKING,USB_CDC_ACM,STUDIO_TRANSPORT_UART활성. 미사용600초/연결해제시잠금.
- 실제right: Studio RPC미활성,물리배치/엄지보정유지.
- 실제Devicetree에Command-Space콤보와Caps layer-tap포함확인.
- left FLASH278660B/792KiB, RAM73454B/256KiB.
- 새left UF2 1089블록,0x26000..0x6a100, SHA256 1cba657e3494f30abb763d931db3c69d1ef6164ed78a95e9bb521ff2c2e71ef1.
- 새right UF2 783블록,0x26000..0x56f00, SHA256 2e0ff14833be1f462a80891f8f6b764702b0040879c1096b8cab701d52302b63.
- backup32의좌우UF2도구조검증통과.

실제장치플래시,Studio장치검색/잠금해제,입력/트랙볼,Studio저장/재부팅은아직미실행이다.
