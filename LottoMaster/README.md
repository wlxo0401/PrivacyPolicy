# LottoMaster — 개인정보 처리방침

iOS 앱 **로또마스터 (LottoMaster)** 의 개인정보 처리방침입니다. 동행복권(로또6/45) 공개 당첨번호를 조회하고, 이용자가 직접 생성·저장한 번호를 기기 내에서 관리하며, 실물 복권의 QR 코드를 스캔해 당첨을 확인하는 도구 앱입니다.

각 언어 폴더의 루트 URL이 **App Store Connect 등록용 안정 URL**입니다.

## 언어 선택 / Language

| 언어 | Language | URL (App Store Connect 등록용) |
|---|---|---|
| 한국어 | Korean | [`ko/`](./ko/) |

## 적용 법령 기준

- `ko/` — 한국 「개인정보 보호법(PIPA)」 + 정보통신망법 (앱 UI 단일 언어 / 한국 시장 전용)

## 앱 데이터 특징

- 이용자가 저장한 번호 데이터는 **기기 내 SwiftData에만 저장**, 외부 서버 미전송
- 클라우드 동기화 기능 없음 — 저장 번호는 기기를 벗어나지 않음
- **카메라 + QR 스캔**: 당첨 확인 시에만 카메라 활성화, 영상은 기기 내 QR 인식에만 실시간 사용·미저장
- **QR 당첨 확인**: 스캔한 동행복권 조회 URL(구매 회차·번호 포함)을 앱 내 WebView로 열어 dhlottery.co.kr에 전송 → 동행복권 정책 적용
- 외부 통신: 동행복권 공개 당첨번호 API(dhlottery.co.kr), Apple App Store 공개 정보(iTunes Lookup) — 비식별 정보만 전송
- 자동 수집: Firebase Analytics, Firebase Crashlytics, Google AdMob, Google UMP(광고·추적 동의 관리, ATT 기반), Apple SKAdNetwork
- 분석·충돌 데이터는 출시 빌드에서만 수집(디버그 빌드 비수집)
- 피드백 메일은 Apple Mail로 사용자 직접 발송 — 개발자 서버 거치지 않음
- 인앱 결제·로컬 알림·로그인 기능 없음

## 연락처

- 개발자: 김지태 (Jitae Kim)
- 이메일: wlxo0401@gmail.com
