# 선협 역사 기록서 — Android APK

이 저장소는 **선협 역사 기록서 시뮬레이션 게임**의 Android APK 공개 배포 전용 저장소입니다. 원본 소스와 개발 자료는 비공개 저장소에서 관리하며, 여기에는 정식 배포 APK·체크섬·서명 정보·변경 내역만 공개합니다.

> 현재 제공되는 빌드는 기능 개발 중인 Alpha 버전입니다. Alpha 1.0.9는 기존 저장 wire와 공개 게임 결과를 의도적으로 바꾸지 않고, 결정론·인과·저장·성능 계약과 릴리스 검증 기준을 강화합니다.

## 최신 배포 상태

- 최신 버전: **Alpha 1.0.9**
- 지원 ABI: **ARM64 (`arm64-v8a`)**
- 공개 채널: **정식 서명 Release**
- Debug 릴리스: **제공하지 않음**
- 빌드 입력: `fdd2022a0aa1031d730138df660ffa67deac9298`
- 전체 검증: [고정 소스 검증 run 31797844164](https://github.com/junghara/xianxia-chronicle-releases/actions/runs/31797844164)
- 공식 배포: [릴리스 run 31799039623](https://github.com/junghara/xianxia-chronicle-releases/actions/runs/31799039623)
- 성능 기준: 동일 runner에서 기준 소스 `c917c15b4c51d050d8ae507f4c7dd35d97b944cd`와 최종 소스를 비교해 gate 통과
- 상태: **Host·Sanitizer·Android·Release emulator·성능·서명·공개 배포 완료**

## 다운로드

### Alpha 1.0.9 정식 서명 Release

- [Alpha 1.0.9 정식 릴리스 열기](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.9)
- [ARM64 Release APK 바로 다운로드](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.9/xianxia-chronicle-1.0.9-arm64-release.apk)
- [업데이트 요약본](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.9/xianxia-chronicle-1.0.9-update-summary.md)
- [상세 업데이트 내역](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.9/xianxia-chronicle-1.0.9-detailed-changelog.md)
- [SHA-256 체크섬](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.9/xianxia-chronicle-1.0.9-arm64-release.apk.sha256)
- [서명 인증서 정보](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.9/signing-certificate.txt)

## Alpha 1.0.9 주요 변경

- simulation·persistence·query·runtime·Android 코드를 기능·계층·생명주기별 검색 작업집합으로 재편
- source/test/benchmark 등록, owner·의존 DAG, native command·DTO 계약을 단일 정본과 자동 gate로 고정
- RNG domain, 인과 ID, 권위 상태, 저장 section 의존성, 복구와 성능 지표의 전역 계약 추가
- 기존 자질 생성 동작을 stable ID·version·상태가 있는 `LegacyCompatibility` 프로필로 명시
- Candidate/Production 자질 프로필이 기존 균등 sampler를 암묵적으로 재사용하지 못하도록 차단
- 기존 수행·아이템·지역·이동·탐색·AI·기록·저장·Android 기반을 실제 코드·테스트 기준으로 재감사
- Host 81개 회귀, B0–B7 성능, ASan/UBSan, Android 양 ABI 빌드와 Release 에뮬레이터 검증을 통과
- 중간 개발에는 Actions를 사용하지 않고, 최종 고정 SHA에서만 전체 검증과 서명 빌드를 수행

미승인 production 분포·확률·가중치·외형 필드·영맥 값·구체 콘텐츠는 임의 구현하지 않았습니다.

## 저장 정책

Alpha 1.0.9는 기존 저장 wire와 공개 게임 결과를 의도적으로 변경하지 않고 다음 계약을 회귀 검증합니다.

- 현재 권위 Agent domain·아이템 런타임·RNG·다음 경계 저장/복원
- Characters v2 현재 월드 슬롯 round-trip과 state hash
- 체크섬·길이·잘림·잘못된 섹션·journal 불일치·손상 상태 거부
- 실패한 restore의 무변경 원자성
- 임시 쓰기·원자 교체·backup/temporary 복구

이전 버전 저장 파일을 위한 새로운 복원·마이그레이션 계약은 Alpha 1.0.9에 추가하지 않았습니다.

## 설치 방법

1. 정식 서명 ARM64 Release APK를 다운로드합니다.
2. Android에서 해당 브라우저 또는 파일 관리자의 **알 수 없는 앱 설치** 권한을 허용합니다.
3. APK를 실행해 설치합니다.

과거 Debug APK나 다른 서명 채널이 설치되어 있으면 정식 Release를 덮어쓸 수 없습니다. 기존 앱을 삭제한 뒤 설치해야 할 수 있으며, 앱 삭제 시 로컬 데이터도 함께 삭제될 수 있습니다.

## 무결성 확인

릴리스에 첨부된 `.sha256` 파일과 서명 인증서 정보를 기준으로 다운로드 파일을 확인하세요.

- APK SHA-256: `1b0b57cecff6e03fec1827d59e1274a3129054ae5f615a66cddffef9ba3d7f4a`
- 서명 인증서 SHA-256: `0b243b8ad8773e46257cf0237fdc87f59ebf76a77e0dc65aa6a1bd499676cc44`
- 내부 버전: `versionName 1.0.9`, `versionCode 1000009`
- APK 계약: zipalign, `arm64-v8a`, 비디버그, APK Signature Scheme v2/v3 검증 통과

```bash
sha256sum -c xianxia-chronicle-1.0.9-arm64-release.apk.sha256
apksigner verify --verbose --print-certs xianxia-chronicle-1.0.9-arm64-release.apk
```

## 현재 제한

- 현재 모든 공개 버전은 Alpha 개발 버전입니다.
- Android `arm64-v8a` 기기만 공개 지원합니다.
- production 자질 분포·확률·가중치와 미모 세부 공식·효과는 아직 확정되지 않았습니다.
- 구체 아이템 품계·전체 장착 슬롯·완성 제작 콘텐츠·확률·비용·AI 정책은 아직 포함하지 않았습니다.
- 일반 아이템 통계는 현재 실제 연결 데이터가 없어 숨김 처리됩니다.
- 기존 지역·이동·탐색·AI 기반은 감사했지만, 미승인 지도·공간·이동·탐색·AI 확장 값과 콘텐츠는 추가하지 않았습니다.
- 실행 오류, 데이터 초기화, 기능 삭제·변경과 밸런스 변경이 발생할 수 있습니다.
- 이 저장소는 APK 배포 전용이며 게임 소스 코드는 포함하지 않습니다.

## 과거 릴리스

- [Alpha 1.0.8](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.8)
- [Alpha 1.0.7](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.7)
- [Alpha 1.0.6](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.6)
- Alpha 1.0.4 Debug 사전 릴리스는 과거 진단 기록으로만 유지합니다.
