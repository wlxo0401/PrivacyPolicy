# NumberOfPictures — 개인정보 처리방침

iOS 앱 **사진에 숫자 입력 (Number on Photos)** 의 개인정보 처리방침 모음입니다.

각 언어 폴더의 루트 URL이 **App Store Connect 등록용 안정 URL**입니다. 이 URL은 정책이 갱신되어도 바뀌지 않으며, 자동으로 최신 정책 + 이전 버전 목록을 표시합니다.

## 언어 선택 / Language

| 언어 | Language | URL (App Store Connect 등록용) |
|---|---|---|
| 한국어 | Korean | [`ko/`](./ko/) |
| English | English | [`en/`](./en/) |
| 日本語 | Japanese | [`ja/`](./ja/) |
| 简体中文 | Simplified Chinese | [`zh-Hans/`](./zh-Hans/) |
| 繁體中文 | Traditional Chinese | [`zh-Hant/`](./zh-Hant/) |

## 폴더 구조

```
NumberOfPictures/
├── ko/
│   ├── index.md          ← 안정 URL (App Store 등록) — 최신 정책 + 이전 버전 목록 자동 표시
│   └── YYYY-MM-DD.md     ← 시행일자별 정책 (히스토리)
├── en/
├── ja/
├── zh-Hans/
└── zh-Hant/
```

## 정책 갱신 워크플로

1. 새 날짜 파일 추가: `{언어}/YYYY-MM-DD.md`
2. 해당 언어의 `index.md`에서:
   - `현재 시행 중인 버전` 날짜를 새 날짜로 변경
   - `{% raw %}{% include_relative ... %}{% endraw %}` 줄의 파일명을 새 파일명으로 변경
   - `이전 버전 / Archive` 섹션에 기존 버전 링크 추가
3. 5개 언어 모두 동일하게 갱신
4. `git commit && git push` → GitHub Pages 자동 재빌드 → App Store URL은 그대로

## 적용 법령 기준

- `ko/` — 한국 「개인정보 보호법(PIPA)」 + 정보통신망법
- `en/` — EU GDPR (최대 안전 베이스라인) + CCPA/CPRA (캘리포니아) 섹션 포함
- `ja/` — 일본 「個人情報の保護に関する法律(APPI)」
- `zh-Hans/`, `zh-Hant/` — GDPR 베이스 번역본 (중국 본토 App Store 직접 출시 대상 아님)

## 연락처

- 개발자: 김지태 (Jitae Kim)
- 이메일: wlxo0401@gmail.com
