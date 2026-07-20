# Wayp — 개인정보 처리방침

iOS 앱 **Wayp** 의 개인정보 처리방침 모음입니다. GPS로 주행 속도와 이동 경로를 실시간으로 측정·표시하고 주행 기록을 남기는 속도계·주행기록 앱입니다.

각 언어 폴더의 루트 URL이 **App Store Connect 등록용 안정 URL**입니다.

## 언어 선택 / Language

| 언어 | Language | URL (App Store Connect 등록용) |
|---|---|---|
| 한국어 | Korean | [`ko/`](./ko/) |
| English | English | [`en/`](./en/) |
| 日本語 | Japanese | [`ja/`](./ja/) |
| 简体中文 | Simplified Chinese | [`zh-Hans/`](./zh-Hans/) |
| 繁體中文 | Traditional Chinese | [`zh-Hant/`](./zh-Hant/) |

## 적용 법령 기준

- `ko/` — 한국 「개인정보 보호법(PIPA)」 + 「위치정보의 보호 및 이용 등에 관한 법률」
- `en/` — EU GDPR + CCPA/CPRA (캘리포니아) 섹션 포함
- `ja/` — 일본 「個人情報の保護に関する法律(APPI)」
- `zh-Hans/`, `zh-Hant/` — GDPR 베이스 번역본

## 앱 데이터 특징

- **모든 데이터가 기기 내에서만 처리됨** — 위치(GPS), 주행 기록, 앱 설정 전부 외부 서버 미전송
- 주행 기록은 **기기 내 SwiftData**, 설정은 UserDefaults 저장. iCloud(CloudKit) 동기화 사용 안 함 — 데이터가 기기를 벗어나지 않음
- **주행 기록 중 백그라운드 위치 수집** — 화면이 꺼져 있거나 앱이 백그라운드에 있어도 속도·경로 측정 유지 (`UIBackgroundModes = location`). 위치 권한은 "앱 사용 중(WhenInUse)"만 요청
- **서드파티 SDK·애널리틱스·광고·크래시 리포팅·계정 전부 없음** — 개발자가 수집·전송·제3자 제공하는 데이터 없음
- 네트워크 전송 코드 없음. 지도 표시 시 Apple 지도(MapKit)가 지도 타일을 불러오는 통신만 발생하며 이는 Apple 정책에 따름
- 인앱 구매 없음

## 연락처

- 개발자: 김지태 (Jitae Kim)
- 이메일: wlxo0401@gmail.com
