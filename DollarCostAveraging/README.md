# 루프 — 개인정보 처리방침

iOS 앱 **루프 - 적립식 투자 일지 작성 (Loop)** 의 개인정보 처리방침 모음입니다. 적립식(분할 매수) 투자 기록을 기기 내에 저장·관리하는 앱입니다.

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

- `ko/` — 한국 「개인정보 보호법(PIPA)」 + 정보통신망법 (앱 UI 기본 언어)
- `en/` — EU GDPR + CCPA/CPRA (캘리포니아) 섹션 포함 (App Store 등록 메타데이터 언어 / 글로벌 배포 대응)
- `ja/` — 일본 「個人情報の保護に関する法律(APPI)」
- `zh-Hans/`, `zh-Hant/` — GDPR 베이스 번역본

## 앱 데이터 특징

- 사용자가 입력한 투자 데이터(종목·증권사·목표 수량·매수/매도 거래·알림 일정)는 **기기 내 SwiftData에만 저장**, 외부 서버 미전송
- 클라우드 동기화 기능 없음 — 투자 데이터는 기기를 벗어나지 않음
- 알림은 **기기 내 로컬 알림**(원격 푸시 서버 미사용) — 사용자가 설정한 종목별 요일·시각 일정 기반
- 자동 수집: Firebase Analytics, Firebase Crashlytics, Google AdMob(ATT 기반 동의), Apple SKAdNetwork
- 분석·충돌 데이터는 출시 빌드에서만 수집(디버그 빌드 비수집)
- 피드백 메일은 Apple Mail로 사용자 직접 발송 — 개발자 서버 거치지 않음
- 최신 버전 안내용 Apple App Store 공개 정보 조회 — 개인 식별 정보 미수집

## 연락처

- 개발자: 김지태 (Jitae Kim)
- 이메일: wlxo0401@gmail.com
