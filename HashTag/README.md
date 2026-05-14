# HashTag — 개인정보 처리방침

iOS 앱 **복붙태그 (CopyTag)** 의 개인정보 처리방침 모음입니다. 해시태그·태그 그룹·포스트를 만들고 복사해 SNS에 빠르게 붙여넣을 수 있는 도구 앱입니다.

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

- `ko/` — 한국 「개인정보 보호법(PIPA)」 + 정보통신망법
- `en/` — EU GDPR + CCPA/CPRA (캘리포니아) 섹션 포함
- `ja/` — 일본 「個人情報の保護に関する法律(APPI)」
- `zh-Hans/`, `zh-Hant/` — GDPR 베이스 번역본

## 앱 데이터 특징

- 이용자가 입력한 태그·태그 그룹·포스트 데이터는 **기기 내 Realm + SwiftData에만 저장**, 외부 서버 미전송
- iCloud(CloudKit) 동기화 사용 안 함 — 입력 데이터는 기기를 벗어나지 않음
- 사용 통계(차트)는 본인 기기 내 사용 기록을 시각화만 — 외부 전송 X
- 자동 수집: Firebase Analytics, Google AdMob, Google User Messaging Platform(광고 동의), Apple SKAdNetwork, Apple 시스템 크래시 로그(옵트인)
- 피드백 메일은 Apple Mail로 사용자 직접 발송 — 개발자 서버 거치지 않음

## 연락처

- 개발자: 김지태 (Jitae Kim)
- 이메일: wlxo0401@gmail.com
