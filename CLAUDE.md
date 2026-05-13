# CLAUDE.md

이 파일은 PrivacyPolicy 레포에서 Claude Code 세션이 따라야 할 컨벤션과 주의사항입니다. 새 세션 시작 시 자동으로 로드됩니다.

Notion 프로젝트명: PrivacyPolicy

## 레포 목적

김지태가 개발한 iOS 앱들의 개인정보 처리방침을 한 곳에서 관리합니다. GitHub Pages로 호스팅되며 각 앱의 App Store Connect Privacy Policy URL로 사용됩니다.

- 라이브: https://wlxo0401.github.io/PrivacyPolicy/
- GitHub: https://github.com/wlxo0401/PrivacyPolicy
- 호스팅: Jekyll (theme: `jekyll-theme-cayman`, GitHub Pages 기본 플러그인만 사용)
- 책임자 / 연락처: 김지태 / wlxo0401@gmail.com (모든 정책에서 동일하게 사용)

## 폴더 구조 — 반드시 이대로

```
PrivacyPolicy/
├── README.md                    ← 레포 루트: 앱 목록 (Pages 인덱스)
├── _config.yml                  ← Jekyll 설정
├── CLAUDE.md                    ← 이 파일
├── .gitignore
└── {AppName}/                   ← 앱별 폴더 (e.g. NumberOfPictures)
    ├── README.md                ← 앱별 언어 선택 페이지
    └── {locale}/                ← BCP 47 로케일 (ko, en, ja, zh-Hans, zh-Hant 등)
        ├── index.md             ← 안정 URL — App Store Connect에 등록되는 URL이 이걸 가리킴
        └── YYYY-MM-DD.md        ← 시행일자별 정책 (히스토리로 누적)
```

**원칙: 차원은 언어(locale)만. 국가 폴더는 만들지 않음.** 안전은 폴더 구조가 아니라 **정책 본문 내용**으로 확보합니다. 각 locale의 정책 본문이 해당 언어 사용자에게 적용될 수 있는 가장 엄격한 법(보통 GDPR)을 충족하도록 작성하세요.

예외 발생 조건: 한 국가가 일반 정책으로 커버 안 되는 별도 법령을 요구하고 사용자가 그 시장을 직접 출시 대상으로 운영하는 경우만 `{App}/{Country}/{locale}/`로 마이그레이션. 미리 만들지 말 것.

## `{App}/README.md` 표준 구조 (앱 진입 페이지)

각 앱 폴더의 README.md(GitHub Pages에서 `…/{App}/` 으로 노출되는 진입 페이지)는 다음 순서를 따릅니다. 기준 예시: **`MoneyCalc/README.md`**.

1. **# 제목 + 한 줄 개요** — `# {App} — 개인정보 처리방침` + 앱 설명 한 줄 + "각 언어 폴더의 루트 URL이 App Store Connect 등록용 안정 URL입니다" 안내 한 줄
2. **## 언어 선택 / Language** — 지원 언어와 App Store Connect 등록용 locale 폴더 URL 표
3. **## 적용 법령 기준** — 각 locale이 어느 법령을 베이스로 작성됐는지 한 줄씩 (PIPA / GDPR+CCPA / APPI / GDPR 번역본 등)
4. **## 앱 데이터 특징** — 이 앱만의 데이터 처리 특징: 사용자 입력 데이터의 저장 위치·외부 전송 여부, 사용 SDK 한 줄 요약, 위젯·메일·IAP·푸시 등 특이사항
5. **## 연락처** — 개발자 이름 + 이메일

**앱 README에 넣지 말 것**: 폴더 구조, 정책 갱신 워크플로, Jekyll 빌드 디버깅 등 메타 정보. 이런 내용은 이 CLAUDE.md에만 통합. 앱 README는 사용자·App Store 리뷰어가 첫 눈에 이해할 수 있는 내용만.

## 정책 본문 작성 원칙

- **베이스라인**: GDPR (가장 엄격). 모든 locale 정책은 GDPR을 충족하도록 작성.
- **지역별 추가 섹션**: 해당 언어의 주 사용자가 거주하는 지역의 법령 섹션을 명시적으로 포함.
  - `ko/` — 한국 PIPA + 정보통신망법 (개인정보분쟁조정위원회 등 구제기관 정보)
  - `en/` — GDPR + CCPA/CPRA (California Residents 섹션)
  - `ja/` — 일본 APPI (개인정보보호위원회 PPC 참조 포함)
  - `zh-Hans`, `zh-Hant` — GDPR 번역본 (중국 본토는 직접 출시 대상 아님 — ICP 등록·법인 필요)
- 정책 본문 상단에 **시행일자(Effective date)** 반드시 명시.
- 정책 파일에는 YAML front matter를 넣지 않음(라이브 .html 렌더링은 `jekyll-relative-links` 기본 동작에 의존).

## 안정 URL 메커니즘 (중요)

App Store Connect에 등록한 URL이 정책 갱신 때마다 바뀌면 안 됩니다. 그래서:

- App Store URL → `https://wlxo0401.github.io/PrivacyPolicy/{App}/{locale}/` (**locale 폴더 루트**)
- 각 locale 폴더의 `index.md`가:
  - Liquid `{% raw %}{% include_relative <최신 정책>.md %}{% endraw %}`로 최신 정책 전문을 인라인
  - 상단 배너 blockquote에 "현재 시행 중인 버전" 날짜 + "이전 버전" 링크 목록 + "다른 언어" 링크 표시
- 과거 정책은 같은 폴더에 `YYYY-MM-DD.md`로 누적되어 `{App}/{locale}/YYYY-MM-DD.html`로 직접 접근 가능

**App Store URL을 `.html` 직접 파일로 등록하지 말 것** — 그러면 갱신 때마다 App Store Connect 수정 필요. 반드시 locale 폴더 루트로.

## 정책 갱신 워크플로 (반드시 이 순서)

1. **모든 지원 언어**에 대해 `{App}/{locale}/YYYY-MM-DD.md` 새 파일을 작성 (시행일자 본문 갱신 포함).
2. 각 `{locale}/index.md`에서 3곳 수정:
   - 배너의 "현재 시행 중" 날짜 → 새 날짜
   - `{% raw %}{% include_relative ... %}{% endraw %}` 줄의 파일명 → 새 파일명
   - "이전 버전 / Archive" 섹션에 기존 버전 링크 한 줄 추가
3. **모든 지원 언어 동시 갱신.** 일부 언어만 바꾸면 글로벌 사용자에게 다른 버전이 노출됨.
4. 경로 명시로 staging (`.claude/` 같은 의도치 않은 파일이 섞이지 않게):
   ```
   git add {App}/{locale1}/YYYY-MM-DD.md {App}/{locale1}/index.md ... (모든 변경 파일)
   ```
   `git add -A` / `git add .` 사용 금지 (아래 "과거 실수" 참조).
5. 커밋 + 푸시 → GitHub Pages 자동 재빌드 → App Store Connect URL은 그대로.

## 새 앱 추가 워크플로

1. **앱 코드 분석 먼저.** 해당 iOS 프로젝트 폴더(예: `/Users/kimjitae/Desktop/Project/Kimjitae/{AppName}/`)에서 실제 사용 SDK 확인:
   - `find ... -name "Package.resolved"` 및 `.swift` 파일의 `import` 구문
   - `Info.plist`의 권한 description, `GADApplicationIdentifier`(AdMob), `GoogleService-Info.plist`(Firebase 사용 여부)
   - `Localizable.xcstrings`의 지원 언어 목록 → locale 폴더 결정 기준
2. App Store 리스팅도 확인 (`WebFetch`). **App Store Connect의 App Privacy 데이터 선언과 실제 SDK가 일치하는지** 점검하고, 불일치 시 사용자에게 알릴 것.
3. `mkdir -p {NewApp}/{ko,en,...}` (지원 언어만큼)
4. 각 locale의 `YYYY-MM-DD.md` 작성 (위 "정책 본문 작성 원칙" 참조)
5. 각 locale의 `index.md` 작성 (`NumberOfPictures/{locale}/index.md`를 템플릿으로 복사 후 수정)
6. `{NewApp}/README.md` 작성 (위 "`{App}/README.md` 표준 구조" 참조, 예시 파일: `MoneyCalc/README.md`)
7. 루트 `README.md`의 Apps 표에 행 추가
8. 경로 명시로 staging → 커밋 → 푸시
9. 사용자에게 App Store Connect에 등록할 마켓별 URL 목록 제공

## ⚠️ 과거 실수 — 반복하지 말 것

1. **국가별 폴더 구조로 시작 (KR/US/EU)**  
   처음에 국가 폴더로 설계했다가 사용자가 "무지성 전체 출시" 라고 지적. 글로벌 App Store 출시면 언어 차원만 있으면 됨. 안전은 정책 본문 내용으로 확보.

2. **`git add -A` / `git add .` 사용**  
   `.claude/skills/` 폴더가 통째로 공개 레포에 푸시된 적 있음. 새 파일 staging 시 반드시 **경로 명시**. 예: `git add NumberOfPictures/ko/2027-01-15.md NumberOfPictures/ko/index.md`.

3. **App Store URL을 dated 파일(.html)로 등록**  
   그러면 갱신 때마다 App Store Connect 수정 필요. 반드시 locale 폴더 루트(`/{locale}/`)로 등록.

4. **일부 언어만 갱신**  
   한국어만 바꾸고 영어는 그대로 두면 마켓별로 다른 버전이 노출됨. 모든 지원 언어 동시 갱신.

5. **정책 작성을 코드 검증 없이 진행**  
   App Store Connect의 데이터 선언이 실제 SDK 사용과 어긋난 경우가 있었음 (예: NumberOfPictures는 Crashlytics 사용 중인데 App Store엔 "진단: 수집 안 함"으로 선언). 코드(`import`, `Package.resolved`, `Info.plist`)를 먼저 검사하고, 불일치 발견 시 사용자에게 App Store Connect 업데이트도 함께 안내.

6. **Jekyll 커스텀 플러그인 추가**  
   GitHub Pages는 화이트리스트 플러그인만 허용. `jekyll-relative-links`, `jekyll-redirect-from`, `jekyll-readme-index` 등 기본 활성화 플러그인 외에 추가하면 빌드 실패. `include_relative`는 Liquid 기본 태그라 안전.

## 호스팅 / 빌드 디버깅

- 푸시 시 GitHub Pages 자동 재빌드 (보통 30초 ~ 1분)
- 빌드 상태: `gh api repos/wlxo0401/PrivacyPolicy/pages/builds/latest --jq '.status'`
- 빌드 완료 확인 시: `built` 가 떨어질 때까지 폴링
- URL 검증: Python `urllib.request`로 HTTP 200 확인 (`curl`이 PATH에 없을 수 있음 — `/usr/bin/curl` 직접 호출 필요한 경우 있음)
- `_config.yml` 변경은 매우 신중하게. 테마 바꾸면 모든 페이지 영향.

## 연락처 / 메타

- 개발자: 김지태 (Jitae Kim)
- 이메일: wlxo0401@gmail.com
- GitHub: @wlxo0401
- 모든 정책의 책임자 표기는 위 정보 사용 (일관성 유지)
