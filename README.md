# 옥피부 (OkSkin)

<img src="https://github.com/okdaejang-art/okskin-releases/releases/download/v0.2.3/OkSkin-icon.png" width="180" alt="옥피부 얼굴 아이콘">

**Final Cut Pro에서 피부 보정과 얼굴형 조절을 함께 사용하는 Mac용 효과입니다.** 사진·동영상을 따로 열어 볼 수 있는 독립 미리보기 앱도 포함합니다.

## 다운로드 — 0.2.3 공개 시험판

- **[설치 ZIP 바로 받기](https://github.com/okdaejang-art/okskin-releases/releases/download/v0.2.3/OkSkin-0.2.3-macOS-universal.zip)**
- [릴리스·설치 안내·검증 파일 보기](https://github.com/okdaejang-art/okskin-releases/releases/tag/v0.2.3)
- Intel(x86_64)·Apple Silicon(arm64)을 함께 포함한 유니버설 배포본
- 무료로 내려받아 시험할 수 있습니다. 이 저장소는 설치 파일과 사용 안내를 제공하는 배포용 저장소입니다.

GitHub의 **Assets → OkSkin-0.2.3-macOS-universal.zip**을 받으세요. 자동으로 표시되는 **Source code** ZIP은 앱 설치 파일이 아닙니다.

## 할 수 있는 것

- 피부 매끄러움, 밝기, 붉은기 조절
- 얼굴 폭, 턱선, 눈 크기 조절
- 전체 보정 강도와 피부 보정 영역 표시
- Final Cut Pro 효과의 표준 키프레임 조절
- 독립 앱에서 사진·SDR 영상 프레임 미리보기, PNG·오디오 포함 ProRes MOV 저장
- 얼굴 분석과 보정은 Mac에서 처리합니다. 영상이나 얼굴 데이터를 서버로 업로드하지 않습니다.

## 설치와 파이널컷 사용

1. ZIP을 **폴더째** 풀어 주세요. 앱과 `옥피부 효과` 폴더, 설치 명령 파일을 같은 폴더에 둡니다.
2. 작업을 저장하고 **Final Cut Pro·Motion·옥피부 앱을 종료**합니다.
3. 배포 폴더의 **옥피부 설치.command**를 실행합니다. 터미널에 설치 완료 문구가 나오면 됩니다.
4. Final Cut Pro를 다시 열고 **효과 브라우저(⌘5) → 옥피부**를 선택합니다.
5. 옥피부 효과를 영상 클립으로 드래그한 뒤 **비디오 인스펙터**에서 값을 조절합니다.

설치 명령은 현재 사용자의 응용 프로그램 폴더에 앱을, Motion Templates의 Effects 폴더에 효과를 설치합니다. 기존 옥피부 앱·효과는 교체 전에 백업합니다. Xcode·FxPlug SDK를 별도로 설치할 필요는 없습니다.

독립 앱은 Finder의 **이동 → 홈 → 응용 프로그램 → 옥피부.app**에서 열 수 있습니다. 파이널컷에서 효과를 쓸 때 독립 앱을 계속 켜 둘 필요는 없습니다. 앱 안에 효과 엔진이 들어 있어 앱을 삭제하면 파컷 효과도 정상 작동하지 않습니다.

피부 보정은 기본값부터, 얼굴형은 낮은 값부터 비교하세요. **피부 보정 영역 보기**는 확인용이므로 출력 전에 꺼 주세요. 전체 강도 0 또는 파컷 효과의 체크박스로 전후를 비교할 수 있습니다.

## 지원 범위와 검증

- **macOS 13 이상을 대상으로 빌드**했습니다. Final Cut Pro는 별도이며, 사용하는 파컷 버전의 OS 요구 사항도 충족해야 합니다.
- 실제 확인 환경: **Intel Mac / macOS 15.7.4 / Final Cut Pro 12.3 / AMD Radeon RX 6900 XT**.
- 파컷 효과 표시·8개 조절 항목·얼굴 감지·ProRes 출력, 독립 앱 미리보기·영상 출력 확인.
- 12개 GPU 검사 통과. 앱·엔진·FxPlug·두 런타임 프레임워크 모두 x86_64/arm64 및 서명 검사 완료.
- **Apple Silicon 실기기 실행·성능 검증은 아직입니다.** 유니버설 파일 포함 여부와 실제 실행 검증은 구분해서 안내합니다.
- 0.2.3은 살구·로즈색 얼굴 아이콘을 적용한 버전이며 보정 엔진은 0.2.1과 같습니다.

## 시험판에서 알아둘 점

**SDR Rec.709 영상용**입니다. HDR/Log의 색 처리 품질은 검증하지 않았습니다. 독립 앱은 PQ/HLG 영상을 거부하지만 파컷 플러그인이 HDR 프로젝트를 자동으로 막지는 않습니다.

움직임을 시간축으로 안정화하는 추적 기능은 아직 없어서 빠른 움직임·가림·옆얼굴에서 보정이 흔들리거나 약해질 수 있습니다. 얼굴형을 크게 바꾸면 머리카락·배경도 함께 휠 수 있습니다. 최대 8명에게 같은 설정을 적용하며 사람별 선택은 지원하지 않습니다.

전용 AI 피부 분할이나 잡티·깊은 주름을 하나씩 지우는 기능은 없습니다. 독립 앱의 영상 미리보기는 실시간 재생이 아닌 프레임 탐색 방식입니다. 4K 장시간 재생·출력, 모든 Mac·파컷 버전은 검증하지 않았습니다. 먼저 짧은 SDR 클립으로 확인해 주세요.

현재 **개발용 ad-hoc 서명이며 Apple Developer ID 서명·공증 전**입니다. 처음 실행할 때 macOS가 차단할 수 있습니다. 출처를 확인하고 신뢰하는 경우 [Apple의 앱 실행 안내](https://support.apple.com/ko-kr/102445)를 참고하세요.

## 설치 위치와 제거

- 앱: `~/Applications/옥피부.app`
- 효과: `~/Movies/Motion Templates.localized/Effects.localized/옥피부/옥피부/옥피부.moef`
- 이전 설치 백업: `~/Library/Application Support/옥피부/Backups/`

파컷·Motion·옥피부를 종료한 뒤 위의 옥피부 앱과 Effects 아래 옥피부 폴더를 휴지통으로 옮기면 됩니다. 원본 영상이나 파컷 보관함은 제거 대상이 아닙니다.

문제가 있으면 [Issues](https://github.com/okdaejang-art/okskin-releases/issues)에 Mac 칩 종류, macOS·파컷 버전, 어떤 조절에서 발생했는지 알려 주세요.
