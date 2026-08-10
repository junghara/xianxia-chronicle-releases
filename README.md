# 선협 역사 기록서 — Android APK

이 저장소는 **선협 역사 기록서 시뮬레이션 게임**의 Android APK 공개 배포 전용 저장소입니다. 원본 소스와 개발 자료는 비공개 저장소에서 관리하며, 여기에는 정식 배포 APK·체크섬·서명 정보·변경 내역만 공개합니다.

> 현재 제공되는 빌드는 기능 개발 중인 Alpha 버전입니다. Alpha 1.0.8은 기존 저장·복구 계약을 회귀 검증하지만 이전 버전 저장 파일을 위한 새 복원·마이그레이션은 추가하지 않습니다.

## 최신 배포 상태

- 최신 버전: **Alpha 1.0.8**
- 지원 ABI: **ARM64 (`arm64-v8a`)**
- 공개 채널: **정식 서명 Release**
- Debug 릴리스: **제공하지 않음**
- 빌드 입력: `e5553bbd82a6bab95699c37ce9199d7ba1fe8181`
- 전체 검증: [고정 소스 검증 run 31374221635](https://github.com/junghara/xianxia-chronicle-releases/actions/runs/31374221635)
- 공식 배포: [릴리스 run 31378180032](https://github.com/junghara/xianxia-chronicle-releases/actions/runs/31378180032)
- 상태: **Host·Sanitizer·Android·서명·검증·공개 배포 완료**

## 다운로드

### Alpha 1.0.8 정식 서명 Release

- [Alpha 1.0.8 정식 릴리스 열기](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.8)
- [ARM64 Release APK 바로 다운로드](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.8/xianxia-chronicle-1.0.8-arm64-release.apk)
- [업데이트 요약본](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.8/xianxia-chronicle-1.0.8-update-summary.md)
- [상세 업데이트 내역](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.8/xianxia-chronicle-1.0.8-detailed-changelog.md)
- [SHA-256 체크섬](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.8/xianxia-chronicle-1.0.8-arm64-release.apk.sha256)
- [서명 인증서 정보](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.8/signing-certificate.txt)

## Alpha 1.0.8 주요 변경

- 월드 1회 순회로 세계 KPI·15개 계획 통계·인물 필터용 레코드를 생성하는 불변 관찰 스냅샷을 추가
- 변경된 월드만 15Hz 이하로 재발행하고 동일 필터·정렬·페이지 결과를 재사용하는 캐시를 적용
- 생존·연령·경지·단계·진행·돌파·자질·영근·행동·공법·돌파법·상태·자원·윤회 통계를 추가
- 실제 데이터가 없는 일반 아이템 통계와 세부 구역은 임의 값을 만들지 않고 숨김
- 랭킹과 인물 허브에 다중 AND 필터, 12행 페이지 조회, 이름·번호 검색을 추가
- 인물 상세를 개요·수행·자질·보유·AI·기록 6개 목적형 탭으로 정리
- 세계·연대기·인물·랭킹·설정 화면에 48dp 입력 영역과 화면 밖 행 렌더 생략을 적용
- 화면·스크롤·필터·선택 인물·상세 탭·접힘 상태를 시뮬레이션 저장과 분리해 유지
- Host 79개 회귀, B0–B7 성능, ASan/UBSan, Android 양 ABI 빌드와 Release 에뮬레이터 검증을 통과

새 게임 규칙·확률·분포·가중치·저장 마이그레이션과 Alpha 1.0.9의 지도·공간·이동·탐색·AI 확장 범위는 이번 버전에 추가하지 않았습니다.

## 저장 정책

Alpha 1.0.8은 Alpha 1.0.7의 저장 의미를 변경하지 않고 다음 기존 계약을 회귀 검증합니다.

- 현재 권위 Agent domain·아이템 런타임·RNG·다음 경계 저장/복원
- Characters v2 현재 월드 슬롯 round-trip과 state hash
- 체크섬·길이·잘림·잘못된 섹션·journal 불일치·손상 상태 거부
- 실패한 restore의 무변경 원자성
- 임시 쓰기·원자 교체·backup/temporary 복구

이전 버전 저장 파일을 위한 새로운 복원·마이그레이션 계약은 Alpha 1.0.8에 추가하지 않았습니다.

## 설치 방법

1. 정식 서명 ARM64 Release APK를 다운로드합니다.
2. Android에서 해당 브라우저 또는 파일 관리자의 **알 수 없는 앱 설치** 권한을 허용합니다.
3. APK를 실행해 설치합니다.

과거 Debug APK나 다른 서명 채널이 설치되어 있으면 정식 Release를 덮어쓸 수 없습니다. 기존 앱을 삭제한 뒤 설치해야 할 수 있으며, 앱 삭제 시 로컬 데이터도 함께 삭제될 수 있습니다.

## 무결성 확인

릴리스에 첨부된 `.sha256` 파일과 서명 인증서 정보를 기준으로 다운로드 파일을 확인하세요.

- APK SHA-256: `2cae0c06cde01809610792c821b9c05ad26b3949b4ef472f899244e311dc9772`
- 서명 인증서 SHA-256: `0b243b8ad8773e46257cf0237fdc87f59ebf76a77e0dc65aa6a1bd499676cc44`
- 내부 버전: `versionName 1.0.8`, `versionCode 1000008`
- APK 계약: zipalign, `arm64-v8a`, 비디버그, APK Signature Scheme v2/v3 검증 통과

```bash
sha256sum -c xianxia-chronicle-1.0.8-arm64-release.apk.sha256
apksigner verify --verbose --print-certs xianxia-chronicle-1.0.8-arm64-release.apk
```

## 현재 제한

- 현재 모든 공개 버전은 Alpha 개발 버전입니다.
- Android `arm64-v8a` 기기만 공개 지원합니다.
- production 자질 분포·확률·가중치와 미모 세부 공식·효과는 아직 확정되지 않았습니다.
- 구체 아이템 품계·전체 장착 슬롯·완성 제작 콘텐츠·확률·비용·AI 정책은 아직 포함하지 않았습니다.
- 일반 아이템 통계는 현재 실제 연결 데이터가 없어 숨김 처리됩니다.
- 지도·공간·이동·탐색·AI 확장 범위는 Alpha 1.0.9로 이관되어 있습니다.
- 실행 오류, 데이터 초기화, 기능 삭제·변경과 밸런스 변경이 발생할 수 있습니다.
- 이 저장소는 APK 배포 전용이며 게임 소스 코드는 포함하지 않습니다.

## 과거 릴리스

- [Alpha 1.0.7](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.7)
- [Alpha 1.0.6](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.6)
- Alpha 1.0.4 Debug 사전 릴리스는 과거 진단 기록으로만 유지합니다.
