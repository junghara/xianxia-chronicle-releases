# 선협 역사 기록서 — Android APK

이 저장소는 **선협 역사 기록서 시뮬레이션 게임**의 Android APK 공개 배포 전용
저장소입니다. 원본 소스 코드와 개발 자료는 비공개 저장소에서 관리하며, 여기에는
정식 배포 APK·체크섬·서명 정보·변경 내역만 공개합니다.

> 현재 제공되는 빌드는 기능 개발 중인 Alpha 버전입니다. 저장 데이터 호환성,
> UI, 시스템 수치와 기능이 업데이트 과정에서 변경될 수 있습니다.

## 최신 배포 상태

- 최신 버전: **Alpha 1.0.6**
- 지원 ABI: **ARM64 (`arm64-v8a`)**
- 공개 채널: **정식 서명 Release**
- Alpha 1.0.6 Debug 릴리스: **제공하지 않음**
- 빌드 입력: `0c4987908b959bc76d19292fe25ccc993e33df28`
- 전체 검증: [공개 검증 실행 #31290916505](https://github.com/junghara/xianxia-chronicle-releases/actions/runs/31290916505)
- 상태: **빌드·서명·검증·공개 배포 완료**

## 다운로드

### Alpha 1.0.6 정식 서명 Release

- [Alpha 1.0.6 정식 릴리스 열기](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.6)
- [ARM64 Release APK 바로 다운로드](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.6/xianxia-chronicle-1.0.6-arm64-release.apk)
- [업데이트 요약본](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.6/xianxia-chronicle-1.0.6-update-summary.md)
- [상세 업데이트 내역](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.6/xianxia-chronicle-1.0.6-detailed-changelog.md)
- [SHA-256 체크섬](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.6/xianxia-chronicle-1.0.6-arm64-release.apk.sha256)
- [서명 인증서 정보](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.6/signing-certificate.txt)

## Alpha 1.0.6 주요 변경

- 엔진·상태·시스템·AI·세계·저장·조회·UI 책임 경계를 정리하고 Query/Snapshot 단방향 표시 구조를 강화
- primary·backup·temporary 후보의 구조·의미·재생 상태 해시를 검증하고 유효 후보로 primary를 자동 복구
- 진행된 월드 저장·초기화·불러오기 라운드트립과 기존 1.0.5 저장 호환 회귀를 강화
- 런타임 게임 로그 출력, 출력 전용 연간 로그 버퍼, 로그/저장 폴더 열기 기능을 제거
- 개발자 모드 활성화 입력을 0~9 숫자 전용으로 제한
- 관찰 UI를 세계·연대기·인물·랭킹·설정 5화면과 개요·수행·자질·AI·기록 5개 인물 내부 탭으로 재구성
- 최대 32명 관찰 허브, 관찰 번호·이름 검색, 등록 행동·필요 계층·저장된 사유·실제 결과 표시를 추가
- 시스템/라이트/다크 테마, 최소 12sp, 48dp 터치 영역, 큰 글꼴 단일 열, 독립 스크롤 상태를 적용
- 일반 텍스트 대비 4.5:1 이상과 색 이외의 굵은 글자·상단 표시선 선택 표현을 적용
- 불필요한 상세 판단 복사·전체 조회·문자열 처리 비용을 줄이고 Host·Sanitizer·Android·B0~B7 게이트를 통과

전체 변경 내역과 현재 제한은 릴리스에 첨부된 상세 업데이트 문서를 확인하세요.

## 호환 범위와 현재 제한

- Alpha 1.0.5 저장 메타데이터와 Alpha 1.0.4 고정 마이그레이션 자료를 계속 검증합니다.
- 삭제된 자동 로그 상태는 기존 저장에서 런타임 기능으로 복원하지 않지만 생애·윤회·수행·행동·AI 판단 기록은 유지합니다.
- 로그 폴더와 저장 폴더를 여는 바로가기 기능은 1.0.6에서 제거되었습니다.
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

릴리스에는 APK와 함께 `.sha256` 체크섬과 서명 인증서 정보를 제공합니다.

- APK SHA-256: `63c829b865eb67aa21b7d48c7e2efdd39aab1cb9d7780a0b7210efb47762d312`
- 서명 인증서 SHA-256: `0b243b8ad8773e46257cf0237fdc87f59ebf76a77e0dc65aa6a1bd499676cc44`
- 내부 버전: `versionName 1.0.6`, `versionCode 1000006`
- APK 계약: zipalign, `arm64-v8a`, 비디버그, APK Signature Scheme v2/v3 검증 통과

## 과거 개발용 Debug 기록

Alpha 1.0.4 Debug 사전 릴리스는 과거 진단 기록으로만 유지합니다. Alpha 1.0.5부터
신규 공개 배포는 정식 서명 Release만 생성하며 Debug APK는 생성·첨부하지 않습니다.

## 주의사항

- 현재 모든 공개 버전은 Alpha 개발 버전입니다.
- 실행 오류, 데이터 초기화, 기능 삭제·변경과 밸런스 변경이 발생할 수 있습니다.
- 이 저장소는 APK 배포 전용이며 게임 소스 코드는 포함하지 않습니다.
