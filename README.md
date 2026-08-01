# 선협 역사 기록서 — Android APK

이 저장소는 **선협 역사 기록서 시뮬레이션 게임**의 Android APK 공개 배포 전용 저장소입니다.

게임의 원본 소스 코드와 개발 자료는 비공개 저장소에서 관리하며, 이 저장소에는 배포용 APK·체크섬·변경 내역만 공개합니다.

> 현재 제공되는 모든 빌드는 기능 개발 중인 **Alpha 버전**입니다. 저장 데이터 호환성, UI, 시스템 수치와 기능이 업데이트 과정에서 변경될 수 있습니다.

## 최신 배포 상태

- 최신 버전: **Alpha 1.0.1**
- 개발 단계: **Alpha**
- 지원 ABI: **ARM64 (`arm64-v8a`)**
- 공개 채널: **정식 서명 Release / 개발용 Debug**
- 상태: **빌드·검증·공개 배포 완료**

## 다운로드

### Alpha 1.0.1 정식 서명 Release

- [Alpha 1.0.1 정식 릴리스 열기](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.1)
- [Alpha 1.0.1 ARM64 Release APK 바로 다운로드](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.1/xianxia-chronicle-1.0.1-arm64-release.apk)

### Alpha 1.0.1 Debug

- [Alpha 1.0.1 Debug 사전 릴리스 열기](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.1-debug)
- [Alpha 1.0.1 ARM64 Debug APK 바로 다운로드](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.1-debug/xianxia-chronicle-1.0.1-arm64-debug.apk)

일반 설치에는 **정식 서명 Release APK**를 사용하세요. Debug APK는 기능 확인과 오류 진단용입니다.

## 업데이트 내역 공개 방식

모든 신규 배포는 가능한 변경 내역을 다음 두 단계로 나누어 공개합니다.

1. **요약본**
   - GitHub Release 본문에서 바로 확인할 수 있습니다.
   - 핵심 기능 추가, 주요 수정, 사용자에게 직접 영향을 주는 변경을 간결하게 정리합니다.
   - 동일한 요약본 Markdown 파일도 릴리스 자산에 첨부합니다.

2. **상세본**
   - `xianxia-chronicle-버전-detailed-changelog.md` 파일로 릴리스 자산에 첨부합니다.
   - 기능, UI, 시뮬레이션, 성능, 안정성, 빌드, 테스트, 호환성, 알려진 문제를 가능한 범위에서 모두 기록합니다.
   - 소스 코드와 비밀값은 공개하지 않으며, 실제 동작과 변경된 규칙을 설명합니다.

버전별 요약본과 상세본이 비공개 원본 저장소에 준비되지 않으면 Debug와 정식 Release 배포가 모두 중단됩니다.

## Debug와 Release의 차이

두 빌드는 게임 기능, UI, 버전 표시, 배속, 시뮬레이션, JNI 명령 경로가 동일합니다.

- **Debug:** 디버깅 가능, 개발용 Debug 서명
- **Release:** 디버깅 불가, 고정 배포 키 서명

기능을 Debug 전용 또는 Release 전용으로 분리하지 않습니다.

## 설치 방법

1. APK 파일을 다운로드합니다.
2. Android에서 해당 브라우저 또는 파일 관리자의 **알 수 없는 앱 설치** 권한을 허용합니다.
3. 다운로드한 APK를 실행해 설치합니다.

Debug와 Release는 서명 인증서가 다르므로 서로 덮어쓸 수 없습니다. 다른 채널이 설치되어 있다면 기존 앱을 삭제한 뒤 설치해야 합니다.

## 무결성 확인

각 Release에는 APK와 함께 `.sha256` 체크섬 파일을 제공합니다. 정식 서명 Release에는 서명 인증서 정보도 함께 제공합니다.

## 주의사항

- 현재 모든 공개 버전은 **Alpha 개발 버전**입니다.
- 실행 오류, 데이터 초기화, 기능 삭제·변경, 밸런스 변경이 발생할 수 있습니다.
- ARM64 Android 기기만 지원합니다.
- 이 저장소는 APK 배포 전용이며 게임 소스 코드는 포함하지 않습니다.
