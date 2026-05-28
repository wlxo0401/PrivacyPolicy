# ScheduleWork — 개인정보 처리방침

iOS 앱 **스케줄워크 (ScheduleWork)** 의 개인정보 처리방침 모음입니다. 교대·근무 일정, 근무 유형, 할 일, 일별 메모·기분을 관리하고 위젯으로 확인할 수 있는 도구 앱입니다.

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

- 이용자가 입력한 근무 일정·근무 유형·할 일·일별 메모·기분 데이터는 **기기 내 SwiftData에만 저장**, 외부 서버 미전송
- iCloud(CloudKit) 동기화 사용 안 함 — 입력 데이터는 기기를 벗어나지 않음. 위젯은 동일 기기 App Group 영역의 데이터만 표시
- **피드백 기능은 예외**: 이용자가 피드백을 보내면 작성 내용 + 기기 모델·iOS 버전·앱 버전·전송 시각이 **Google Firestore로 전송·저장** (계정·식별자 없음)
- 자동 수집: Firebase Analytics, **Firebase Crashlytics(충돌·진단 자동 수집 — Apple 옵트인 방식 아님)**, Google AdMob, Google User Messaging Platform(광고 동의), Apple SKAdNetwork
- 인앱 구매: Apple StoreKit으로 처리 — 결제수단 정보는 개발자가 수신하지 않음

## 연락처

- 개발자: 김지태 (Jitae Kim)
- 이메일: wlxo0401@gmail.com
