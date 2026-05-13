---
name: crash-analyze
description: Find one crash-risk pattern in the app and analyze it from 5 perspectives. Use when writing crash-defensive code.
allowed-tools: Read, Grep, Glob, Agent, Edit, AskUserQuestion
---

# Crash Analysis Skill

Find **one** crash-risk pattern in the codebase and analyze it from 5 perspectives.

## Procedure

### Step 1: Search for Crash-Risk Patterns

Use Grep and Glob to search Swift files (`**/*.swift`) for the following patterns:

1. **Force unwrap (`!`)** — especially `Calendar.current.date(...)!`, `.first!`, `.last!`, `.randomElement()!`, etc.
2. **Force cast (`as!`)**
3. **Direct array/dictionary indexing** — using `array[index]` without bounds checking
4. **`fatalError()`** — exclude those inside `init(coder:)`
5. **`try!`** usage
6. **Implicitly Unwrapped Optional** declarations (`var name: Type!`)

Search directories: `ScheduleWork/`, `ScheduleWorkWidget/`, `ScheduleWorkDashBoard/`

### Step 2: Select One

Select the **single highest-risk** crash pattern found.
Selection criteria:
- Prioritize code executed during user interaction
- Prioritize code that depends on external data (network, storage)
- Skip already-guarded patterns (e.g., wrapped in `guard let`, `if let`)

Read the selected code with Read to understand its full context.

### Step 3: Output 5-Perspective Analysis

Output the analysis in the following format:

```
## 🔍 크래시 발견
- **파일**: (path:line)
- **코드**: (problematic code)
- **위험도**: HIGH / MEDIUM / LOW
- **크래시 시나리오**: (어떤 조건에서 크래시가 발생하는지)

## 1. 기존 로직 변경 여부
(수정이 기존 동작을 변경하는지 분석)

## 2. 기존 사용자에 대한 영향
(이미 앱을 사용 중인 사용자에게 미치는 영향)

## 3. 사이드 이펙트 범위
(이 코드를 참조하는 다른 파일/함수에 대한 파급 효과)

## 4. 작업 범위
(수정할 파일 목록 및 변경 내용 설명)

## 5. 최적 수정안
(모든 사이드 이펙트를 고려한 최적의 수정 코드 제시)
```

### Step 4: Confirm Fix

After outputting the analysis, use the `AskUserQuestion` tool to ask the user whether to apply the fix:

- **Question**: "위 분석을 바탕으로 크래시 방어 코드를 적용하시겠습니까?"
- If the user **approves**: Apply the code from "5. Optimal Fix" using the `Edit` tool.
- If the user **declines**: Keep only the analysis and end.

## Notes

- All output shown to the user (analysis, questions, explanations) must be in Korean.
- Code must not be modified without user approval after analysis.
- Find a new crash each time — avoid duplicating previously analyzed patterns.
- Ignore `fatalError()` inside `init(coder:)` as it is a Swift convention.
- Ignore patterns inside SwiftUI Preview code.
