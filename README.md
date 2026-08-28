# 선협 역사 기록서 — Android APK

이 저장소는 **선협 역사 기록서 시뮬레이션 게임**의 Android APK 공개 배포 전용 저장소입니다. 원본 소스와 개발 자료는 비공개 저장소에서 관리하며, 여기에는 정식 배포 APK·체크섬·서명 정보·변경 내역·공개 가능한 검증 증거만 공개합니다.

> 현재 제공되는 빌드는 기능 개발 중인 Alpha 버전입니다. 실행 오류, 데이터 초기화, 기능 및 밸런스 변경이 발생할 수 있습니다.

## 최신 배포 상태

- 최신 버전: **Alpha 1.1.0**
- 지원 ABI: **ARM64 (`arm64-v8a`)**
- 공개 채널: **정식 서명 Release**
- 검증된 비공개 source SHA: `96a6667dd74d6707659a1fd1675de22d65d614f8`
- 전체 검증: [고정 소스 검증 run 33076315637](https://github.com/junghara/xianxia-chronicle-releases/actions/runs/33076315637)
- 공식 배포: [릴리스 run 33148766160](https://github.com/junghara/xianxia-chronicle-releases/actions/runs/33148766160)
- 요구사항 증거: **238/238**, 동일 source SHA 및 RELEASED 상태
- 공개 CI 성능: 평균 14.918ms/년, p95 20.679ms, p99 22.938ms, 최대 26.023ms
- 상태: **Host·Sanitizer·Android·Release emulator·성능·서명·Latest 공개 배포 완료**

## 다운로드

### Alpha 1.1.0 정식 서명 Release

- [Alpha 1.1.0 정식 릴리스 열기](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.1.0)
- [ARM64 Release APK 바로 다운로드](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.1.0/xianxia-chronicle-1.1.0-arm64-release.apk)
- [SHA-256 체크섬](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.1.0/xianxia-chronicle-1.1.0-arm64-release.apk.sha256)
- [서명 인증서 정보](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.1.0/signing-certificate.txt)
- [업데이트 요약본](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.1.0/xianxia-chronicle-1.1.0-update-summary.md)
- [상세 업데이트 내역](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.1.0/xianxia-chronicle-1.1.0-detailed-changelog.md)
- [238개 요구사항 공개 증거](https://github.com/junghara/xianxia-chronicle-releases/releases/download/v1.1.0/xianxia-chronicle-1.1.0-238-requirements.json)

## Alpha 1.1.0 주요 변경

- 14개 Master × 17개 수직 항목의 **238개 요구사항**, 58개 수식, SQLite R6 66개 테이블, 54개 법칙 후보, 5개 관찰 탭을 릴리스 범위로 고정
- 5대륙·10개 지도 인스턴스·30주·300지역·3,000장소·900영맥의 안정 주소 계약과 상세 인구 8,000명/상한 10,000명 지원
- 금단경·원영경·화신경, 심성·영혼 및 6개 사회 자질, 고정 시도 스냅샷 기반 돌파 판정 추가
- 윤회강 건너기와 수행·공법·관계·정체성·세계 지식·법칙의 여섯 기억 영역 추가
- Life·Spatial·Organization·Economy·Content·Book 여섯 정본의 원자 저장·복원·해시·SQLite 투영 연결
- 종문·가문·왕조 창건, 출산 후유증, 평판·충성, 영석 거래·가격·예약·보관 게이트 추가
- 세계·세계 역사·탐색·관찰 목록·설정 5탭, 최소 48dp 터치 영역과 320dp 최소 폭 계약 적용
- 개발자 모드 세션 잠금·실패 지연·28개 허용 명령과 공개 빌드의 평문 활성화 코드 금지 적용

## 저장 및 되돌리기 주의

SQLite R6는 1.0.x의 XIANSAVE와 다른 저장 경계입니다. 업데이트 전에 기존 저장을 별도로 보관하세요. 1.1.0 데이터베이스를 1.0.9에서 직접 여는 하위 호환은 보장하지 않습니다. 되돌릴 때는 1.1.0의 쓰기를 중지하고 기존 1.0.9 백업을 복원해야 합니다.

## 설치와 무결성 확인

1. 정식 서명 ARM64 Release APK를 다운로드합니다.
2. Android에서 해당 브라우저 또는 파일 관리자의 **알 수 없는 앱 설치** 권한을 허용합니다.
3. APK를 실행해 설치합니다.

과거 Debug APK나 다른 서명 채널이 설치되어 있으면 정식 Release를 덮어쓸 수 없습니다. 기존 앱을 삭제한 뒤 설치해야 할 수 있으며, 앱 삭제 시 로컬 데이터도 함께 삭제될 수 있습니다.

- APK SHA-256: `0db5ac735a8b0ebb1b3475fba47082fd3cea055381443ab7d8a4d217a8b1c7bc`
- APK 크기: **4,599,910 bytes**
- 내부 버전: `versionName 1.1.0`, `versionCode 1001000`
- APK 계약: zipalign, `arm64-v8a`, 비디버그, APK Signature Scheme v2/v3 검증 통과

```bash
sha256sum -c xianxia-chronicle-1.1.0-arm64-release.apk.sha256
apksigner verify --verbose --print-certs xianxia-chronicle-1.1.0-arm64-release.apk
```

## 검증 증거와 알려진 제한

동일 source SHA의 공개 검증 상태와 238행 공개 증거는 각각 [validation status](https://github.com/junghara/xianxia-chronicle-releases/blob/main/.validation-status/by-source/96a6667dd74d6707659a1fd1675de22d65d614f8.json), [same-SHA evidence](https://github.com/junghara/xianxia-chronicle-releases/blob/main/.validation-evidence/by-source/96a6667dd74d6707659a1fd1675de22d65d614f8.json)에서 확인할 수 있습니다.

실기기 프레임·배터리·열·저장 시간 증거는 아직 없으며 측정 완료로 주장하지 않습니다. 현재 공개 검증은 Host, Android 빌드, x86_64 Release 에뮬레이터와 서명 ARM64 APK 계약을 기준으로 합니다.

## 과거 릴리스

- [Alpha 1.0.9](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.9)
- [Alpha 1.0.8](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.8)
- [Alpha 1.0.7](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.7)
- [Alpha 1.0.6](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.6)
- [Alpha 1.0.5](https://github.com/junghara/xianxia-chronicle-releases/releases/tag/v1.0.5)
