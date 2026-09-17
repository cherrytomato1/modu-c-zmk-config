# MODU-C Studio 전환 — 기존 키맵 보존

이 브랜치는 사용자 main의 7677fa5(32번 Actions)를 기준으로, 제작자 studio-test의 5c5a60a에서 Studio 지원을 이식한 커스텀 구성입니다. 제작자 배포 V4 바이너리 자체가 아닙니다. 실제 키보드 설치/Studio 연결 시험은 아직 하지 않았습니다.

## 보존한 설정

- 레이어0 Mac, 레이어1 Windows, 레이어2 Fn, 레이어3 관리용
- Caps: 짧게 누르면 Caps Lock, 200ms 이상 누르는 동안 Fn
- 엄지 Command(60) + 오른쪽 엄지 Backspace(63): Command+Space 콤보(50ms)
- 기존 Ctrl+5+6 일반재부팅 콤보
- 레이어3 Shift/Z/X/C의 Bluetooth 삭제/프로필0/1/2
- 레이어3 숫자5/6의 좌우 부트로더
- 양쪽 트랙볼, 엄지 방향 보정, ZMK/MODU 소스 고정 버전

Studio 통신/물리 배치 설정과 레이어3 R/T 두 키에 더해, 기본 레이어0/1의 오른쪽 엄지 Backspace에 Command Backspace 동작을 추가했습니다. 단독으로는 Backspace, 왼쪽 Command를 먼저 누른 상태에서는 Command+Space입니다. Command는 유지되며 50ms 동시 입력 제한 없이 동작합니다. 기존 동시 입력 콤보도 유지합니다. 원래 Command+Backspace 동작은 해당 위치에서 대체됩니다.

## 설치 전 준비

현재 정상 펌웨어와 GitHub 소스를 따로 보관합니다. 제공 묶음의 backup-7677fa5에는 이전 좌우 UF2와 소스 ZIP이 있습니다. 미저장 Keymap Editor 편집이 있으면 별도로 보관하십시오. 이 빌드는 위 기준 커밋의 설정만 포함합니다.

현재 Mac에서 부트로더 드라이브를 읽을 수 없었던 문제는 해결됐다고 확인되지 않았습니다. 디스크를 초기화/포맷하지 마십시오. Windows 등에서 정상적으로 부트로더 드라이브를 열 수 있을 때 아래 설치를 진행합니다. 별도 컴파일 도구는 필요하지 않습니다.

## 최초 Studio 펌웨어 설치 — 양쪽 각각

1. ZIP을 모두 압축 풉니다. install-studio 폴더의 파일을 사용합니다.
2. 왼쪽을 PC에 데이터 USB로 연결합니다. 엄지 Fn을 누른 채 왼쪽 Ctrl, 숫자5를 눌러 왼쪽 부트로더에 진입합니다.
3. 방금 나타난 MODU_BOOT 드라이브에 install-studio/modu_left.uf2 하나만 복사합니다. 자동 재부팅까지 기다립니다.
4. 오른쪽을 PC에 데이터 USB로 연결합니다. 양쪽 전원/좌우 연결을 유지한 상태에서 Fn→왼쪽 Ctrl→숫자6으로 오른쪽 부트로더에 진입합니다.
5. 오른쪽 드라이브에 install-studio/modu_right.uf2 하나만 복사합니다. 자동 재부팅까지 기다립니다.
6. 키 조합이 안 되면 해당 절반의 물리 RESET을 빠르게 두 번 누르는 제작자 절차를 사용합니다: https://erkeys.com/user-guide/reset-firmware/
7. 양쪽 전원을 다시 켜고, 왼쪽을 PC USB에 연결합니다.

두 파일을 같은 부트로더 드라이브에 넣지 않습니다. 오른쪽 파일은 오른쪽 기기에 설치해야 합니다. 이번 전환은 Studio를 위한 물리 배치도 달라지므로 양쪽을 설치합니다.

## Studio 첫 연결

Chrome 또는 Edge에서 https://zmk.studio/ 에 접속합니다. Mac에서도 해당 브라우저로 시도할 수 있습니다. 이전 UF2 드라이브 접근 문제와 Studio의 USB 직렬 통신은 서로 다른 경로이므로, Mac에서 연결이 성공하는지는 설치 후 별도 확인해야 합니다.

1. 양쪽 전원을 켜고 왼쪽을 USB로 연결합니다.
2. Fn→왼쪽 Ctrl을 누른 채 T: USB 출력 선택.
3. Studio에서 USB/Serial 연결을 선택하고 MODU 장치를 선택합니다. 오른쪽은 Studio 연결 대상이 아닙니다.
4. Fn→왼쪽 Ctrl을 누른 채 R: Studio 잠금 해제.
5. 레이어0~3과 현재 키 배치가 보이는지 확인합니다.
6. 일반 문자 키 하나를 시험 변경하고 Save를 누릅니다. 입력과 재부팅 후 유지 여부를 확인한 다음 원하는 값으로 되돌려 저장합니다.

Fn은 기존 엄지 Fn 키를 사용하면 됩니다. Caps 홀드를 사용할 때는 200ms 이상 누른 뒤 진행합니다. 관리 레이어3에 접근하는 Fn/Ctrl 경로와 R 잠금 해제 키를 모두 지우지 마십시오. 화면의 작은 자리표시자6개(51~56)는 실제 키가 아닙니다.

## 저장 관리와 복구

Studio에 저장한 키맵은 기기 설정 영역에 보관되며 GitHub에 자동 반영되지 않습니다. 이후 .keymap을 수정해 다시 플래시해도 Studio에서 저장한 키맵이 우선할 수 있습니다.

새 펌웨어의 기본 키맵을 적용할 때는 필요한 Studio 설정을 먼저 기록한 다음 Studio의 Restore Stock Settings를 사용합니다. 이 작업은 Studio에서 수정한 키맵을 초기화합니다. 일반 설치에 Bluetooth 페어링 전체 초기화는 필요하지 않습니다.

Studio에서 콤보를 만들거나 수정하는 기능은 아직 지원하지 않습니다. 이 펌웨어에 포함된 기존 콤보는 유지하고, 콤보 정의를 바꿀 때는 소스/빌드로 관리합니다. 기존 .keymap 파일을 Studio에 업로드하여 자동 복원하는 기능이 있다고 가정하지 않습니다.

이전 펌웨어로 돌아가려면 backup-7677fa5/firmware의 좌우 UF2를 각 절반에 설치합니다. Studio 저장 설정이 재플래시만으로 지워지는 것은 아니므로 나중에 Studio 펌웨어를 다시 설치하면 이전 Studio 설정이 나타날 수 있습니다. 이 경우 접근 가능한 상태에서 설정을 기록하고 Restore Stock Settings로 새 기본값을 복원합니다. 잠금 해제 경로까지 잃어버린 경우 임의 초기화를 반복하지 말고 물리 부트로더/제작자 복구 안내로 진행합니다.

## 설치 후 확인할 항목

- Mac/Windows/Fn 전환과 Caps 탭/홀드
- 엄지 Command+Backspace 콤보, Fn+Ctrl+5/6 부트로더
- Fn+Ctrl+R 잠금 해제 / T USB 출력
- 양쪽 모든 키, 트랙볼 이동과 버튼, 엄지 방향
- Studio 저장→재부팅 유지 / 절전 복귀 / 좌우 재연결

## 개발 검증 및 출처

python3 scripts/validate.py
python3 scripts/test_validate.py
python3 scripts/selftest.py

CI/UF2 검증 성공과 실제 장치 동작 검증은 구분합니다. 초기 실기기 검증 전까지 기본 main은 기존 펌웨어 경로로 유지합니다.

- 제작자 공지: https://www.wadiz.io/web/campaign/detailPost/386073/news/611398
- 이식 근거: https://github.com/22sh22/modu-c-zmk-config/tree/5c5a60ace453b11ecf7fab9e1fb70f4483942caa
- 공식 Studio 설명: https://zmk.dev/docs/features/studio

Studio에 예전 키맵을 이미 저장했다면 새 펌웨어 설치 후 기본 레이어0/1의 오른쪽 엄지 Backspace에 Behavior **Command Backspace**를 선택하고 Save하십시오. 다른 Studio 편집을 유지하면서 이 동작만 적용할 수 있습니다.
