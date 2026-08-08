# 선협 역사 기록서 — Android APK

이 저장소는 **선협 역사 기록서 시뮬레이션 게임**의 Android APK 공개 배포 전용
저장소입니다. 원본 소스 코드와 개발 자료는 비공개 저장소에서 관리하며, 여기에는
정식 배포 APK·체크섬·서명 정보·변경 내역만 공개합니다.

> 현재 제공되는 빌드는 기능 개발 중인 Alpha 버전입니다. 저장 데이터 호환성,
> UI, 시스템 수치와 기능이 업데이트 과정에서 변경될 수 있습니다.

## 최신 배포 상태

- 최신 버전: **Alpha 1.0.5**
- 지원 ABI: **ARM64 (`arm64-v8a`)**
- 공개 채널: **정식 서명 Release**
- Alpha 1.0.5 Debug 릴리스: **제공하지 않음**
- 빌드 입력: `0d59cfcce89ba0437d8fd54120966f31e6165406`
- 상태: **빌드·서명·검증·공개 배포 완료**

## 다운로드

### Alpha 1.0.5 정식 서명 Release

- [Alpha 1.0.5 정식 릴리스 열기](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.5)
- [ARM64 Release APK 바로 다운로드](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.5/xianxia-chronicle-1.0.5-arm64-release.apk)
- [업데이트 요약본](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.5/xianxia-chronicle-1.0.5-update-summary.md)
- [상세 업데이트 내역](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.5/xianxia-chronicle-1.0.5-detailed-changelog.md)
- [SHA-256 체크섬](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.5/xianxia-chronicle-1.0.5-arm64-release.apk.sha256)
- [서명 인증서 정보](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.5/signing-certificate.txt)

## Alpha 1.0.5 주요 변경

- 안정 ID, 정수 시간·점수와 실행·평가·마이그레이션 분리 RNG 계약
- 수행·자질·자원·단약·부상 상태와 행동 중단·재개·정산 기반
- AI 후보·정수 평가·결정론적 선택과 현재·최근·중요 판단 기록 기반
- 저장된 행동·판단을 재계산하지 않는 관찰 모델과 Android 상세 화면
- 버전 저장 컨테이너, 섹션별 체크섬, 원자 저장·백업 복구와 1.0.4 대표 자료 마이그레이션 계약
- 행동·판단 저장 섹션의 결정론적 압축과 B0~B7 성능·메모리·세이브 게이트
- 1·3·10·30·50·100배속의 정수 나노초 누적과 동일 결과 통합 회귀

전체 변경 내역과 현재 제한은 릴리스에 첨부된 상세 업데이트 문서를 확인하세요.

## 호환 범위와 현재 제한

- Alpha 1.0.5 엔진 컨테이너와 Alpha 1.0.4 고정 마이그레이션 자료가 검증 범위입니다.
- Android 사용자용 슬롯 선택·저장 폴더 바로가기 화면은 이번 버전에 연결되지 않았습니다.
- 새 행동·AI 기반이 모든 세계 콘텐츠의 실행 경로를 대체한 것은 아닙니다.
- 축기경 내부 수행, 상세 전투 계산과 영혼 파괴 발생 조건은 아직 구현되지 않았습니다.
- Android `arm64-v8a` 기기만 지원합니다.

## 설치 방법

1. 정식 서명 ARM64 Release APK를 다운로드합니다.
2. Android에서 해당 브라우저 또는 파일 관리자의 **알 수 없는 앱 설치** 권한을 허용합니다.
3. APK를 실행해 설치합니다.

과거 개발용 Debug APK는 정식 Release와 서명이 달라 서로 덮어쓸 수 없습니다. 다른
서명 채널이 설치되어 있다면 기존 앱을 삭제한 뒤 설치해야 하며, 앱 삭제 시 로컬
데이터도 함께 삭제될 수 있습니다.

## 무결성 확인

릴리스에는 APK와 함께 `.sha256` 체크섬과 서명 인증서 정보를 제공합니다. APK는
zipalign, versionName·versionCode, `arm64-v8a`, 비디버그 플래그와 APK Signature
Scheme v2/v3 검증을 통과한 파일입니다.

## 과거 개발용 Debug 기록

Alpha 1.0.4 Debug 사전 릴리스는 과거 진단 기록으로만 유지합니다. Alpha 1.0.5부터
신규 공개 배포는 정식 서명 Release만 생성하며 Debug APK는 생성·첨부하지 않습니다.

## 주의사항

- 현재 모든 공개 버전은 Alpha 개발 버전입니다.
- 실행 오류, 데이터 초기화, 기능 삭제·변경과 밸런스 변경이 발생할 수 있습니다.
- 이 저장소는 APK 배포 전용이며 게임 소스 코드는 포함하지 않습니다.
