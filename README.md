# 선협 역사 기록서 — Android APK

이 저장소는 **선협 역사 기록서 시뮬레이션 게임**의 Android APK 공개 배포 전용 저장소입니다. 원본 소스와 개발 자료는 비공개 저장소에서 관리하며, 여기에는 정식 배포 APK·체크섬·서명 정보·변경 내역만 공개합니다.

> 현재 제공되는 빌드는 기능 개발 중인 Alpha 버전입니다. Alpha 1.0.7은 이전 버전 저장 파일의 복원·마이그레이션을 보장하지 않습니다.

## 최신 배포 상태

- 최신 버전: **Alpha 1.0.7**
- 지원 ABI: **ARM64 (`arm64-v8a`)**
- 공개 채널: **정식 서명 Release**
- Debug 릴리스: **제공하지 않음**
- 빌드 입력: `2e42b8543d7c1d60ee17ec0e23b27c15b28974ec`
- 전체 검증: [고정 소스 검증 run 31309497541](https://github.com/junghara/xianxia-chronicle-releases/actions/runs/31309497541)
- 공식 배포: [릴리스 run 31310078530](https://github.com/junghara/xianxia-chronicle-releases/actions/runs/31310078530)
- 상태: **Host·Sanitizer·Android·서명·검증·공개 배포 완료**

## 다운로드

### Alpha 1.0.7 정식 서명 Release

- [Alpha 1.0.7 정식 릴리스 열기](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.7)
- [ARM64 Release APK 바로 다운로드](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.7/xianxia-chronicle-1.0.7-arm64-release.apk)
- [업데이트 요약본](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.7/xianxia-chronicle-1.0.7-update-summary.md)
- [상세 업데이트 내역](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.7/xianxia-chronicle-1.0.7-detailed-changelog.md)
- [SHA-256 체크섬](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.7/xianxia-chronicle-1.0.7-arm64-release.apk.sha256)
- [서명 인증서 정보](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.0.7/signing-certificate.txt)

## Alpha 1.0.7 주요 변경

- checked time과 검증 후 한 번에 반영되는 원자적 행동 전이 요청을 추가
- 수행·회복·경지 경계를 같은 권위 시간 진행 경로로 연결
- 오성 세부값 기반 12개 파생 능력과 의존 자질 선택 갱신 캐시를 추가
- 인물 자질 관찰에 대표값·10개 세부값·계산 근거와 선천/영구/임시/유효 변화층 표시를 추가
- 선천자질 아래 수행자질과 미모, 수행자질 아래 오성·근골·체질·영근을 배치하는 안정 ID 분류를 추가
- 범용 아이템 정의·인스턴스·보유·예약·소비·장착·제작·후처리·조회·저장 계약을 추가
- 상세 자질·체질·공법·돌파·자원·부상·경지 권위 스냅샷과 Characters v2 현재 월드 슬롯을 확장
- checkpoint provenance, 현재 state hash, 손상 거부, 실패 원자성, backup/temporary 복구를 검증
- StorageWorkflow 단계별 decode와 저장·불러오기 hot path를 최적화
- B0–B7 결정론·성능·메모리, ASan/UBSan, Android 양 ABI 빌드와 Release 에뮬레이터 검증을 통과

미모 수치·공식·효과, production 자질 분포·가중치·확률, 구체 아이템 콘텐츠와 AI 정책은 이번 버전에 임의로 추가하지 않았습니다.

## 저장 정책

Alpha 1.0.7은 이전 버전 저장 파일의 복원·마이그레이션을 공개 호환 계약으로 보장하지 않습니다.

현재 1.0.7에서는 다음 경로를 검증합니다.

- 현재 권위 Agent domain·아이템 런타임·RNG·다음 경계 저장/복원
- Characters v2 현재 월드 슬롯 round-trip과 state hash
- 체크섬·길이·잘림·잘못된 섹션·journal 불일치·손상 상태 거부
- 실패한 restore의 무변경 원자성
- 임시 쓰기·원자 교체·backup/temporary 복구

## 설치 방법

1. 정식 서명 ARM64 Release APK를 다운로드합니다.
2. Android에서 해당 브라우저 또는 파일 관리자의 **알 수 없는 앱 설치** 권한을 허용합니다.
3. APK를 실행해 설치합니다.

과거 Debug APK나 다른 서명 채널이 설치되어 있으면 정식 Release를 덮어쓸 수 없습니다. 기존 앱을 삭제한 뒤 설치해야 할 수 있으며, 앱 삭제 시 로컬 데이터도 함께 삭제될 수 있습니다.

## 무결성 확인

릴리스에 첨부된 `.sha256` 파일과 서명 인증서 정보를 기준으로 다운로드 파일을 확인하세요.

```bash
sha256sum -c xianxia-chronicle-1.0.7-arm64-release.apk.sha256
apksigner verify --verbose --print-certs xianxia-chronicle-1.0.7-arm64-release.apk
```

공식 워크플로는 zipalign, `arm64-v8a`, 비디버그, APK Signature Scheme v2/v3와 SHA-256 생성을 통과한 파일만 게시합니다.

## 현재 제한

- 현재 모든 공개 버전은 Alpha 개발 버전입니다.
- Android `arm64-v8a` 기기만 공개 지원합니다.
- production 자질 분포·확률·가중치와 미모 세부 공식·효과는 아직 확정되지 않았습니다.
- 구체 아이템 품계·전체 장착 슬롯·완성 제작 콘텐츠·확률·비용·AI 정책은 아직 포함하지 않았습니다.
- 실행 오류, 데이터 초기화, 기능 삭제·변경과 밸런스 변경이 발생할 수 있습니다.
- 이 저장소는 APK 배포 전용이며 게임 소스 코드는 포함하지 않습니다.

## 과거 릴리스

- [Alpha 1.0.6](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.6)
- Alpha 1.0.4 Debug 사전 릴리스는 과거 진단 기록으로만 유지합니다.
