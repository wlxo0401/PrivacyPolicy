# NumberOfPictures — 개인정보 처리방침

iOS 앱 **사진에 숫자 입력 (Number on Photos)** 의 개인정보 처리방침 모음입니다.

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

- **사진 데이터**: 이용자가 선택한 사진은 **기기 내에서만 처리**되며 외부 서버로 업로드되지 않음 (숫자 합성 후 카메라 롤로 저장은 사용자의 선택)
- **작업 내역**: 생성 일시·이미지 이름(참조)·입력 모드를 기기 내 SwiftData에 로컬 저장, 외부 전송 X
- 자동 수집(제3자 SDK·시스템): Firebase Analytics, Firebase Crashlytics, Google AdMob, Google UMP(광고·추적 동의 관리, ATT 기반), Apple SKAdNetwork
- 추적: App Tracking Transparency 동의 시에만 IDFA 사용
- 저장: SwiftData(로컬), 외부 클라우드 동기화 없음

## 연락처

- 개발자: 김지태 (Jitae Kim)
- 이메일: wlxo0401@gmail.com
