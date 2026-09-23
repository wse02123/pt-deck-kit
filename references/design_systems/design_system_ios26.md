---
name: Apple iOS 26 Design System 스킬
version: 1.0
source: https://www.figma.com/design/fPaqqJS6WJbB2UiEXx1Ga6/Apple-iOS-26-Library--Community-
extracted: 2026-03-27
platform: Mobile (iOS/iPadOS) — 웹과 단위/규칙 완전히 다름
---

# Apple iOS 26 Design System 스킬

> **목적**: iOS Human Interface Guidelines(HIG)의 모바일 디자인 철학과 단위 체계를 이해하고, 웹과 모바일의 근본적 차이를 바탕으로 모바일 UI를 올바르게 설계할 수 있게 된다.

> [!IMPORTANT]
> **iOS 디자인은 웹 디자인과 단위 체계가 완전히 다릅니다.**
> `px` 대신 `pt(point)` 사용. 1pt = 1px(1x) / 2px(2x Retina) / 3px(3x Super Retina)

---

## 1. iOS 26의 핵심 철학 ("Liquid Glass" 디자인 언어)

### iOS 26 = Apple의 최신 디자인 언어
- **반투명 유리 소재(Liquid Glass)**: 배경이 블러되어 보이는 투명한 레이어
- **적응형 동작(Adaptive Behavior)**: 콘텐츠와 환경에 따라 자동 조정
- **시스템 우선(System First)**: 커스텀보다 시스템 컴포넌트 사용을 강하게 권장

### 핵심 원칙
```
Clarity      → 텍스트 가독성 최우선, 여백을 두려워하지 말 것
Deference    → UI가 콘텐츠를 방해하지 않음
Depth        → Z축(레이어)으로 계층을 표현
Fluidity     → 애니메이션이 공간감을 만들어냄
```

---

## 2. 디자인 토큰 (Figma 75컬러 추출 + HIG 공식 스펙)

### 2-1. iOS 시스템 색상 (Dynamic Colors — 라이트/다크 자동 변환)

#### Primary System Colors
| 이름 | Light Hex | Dark Hex | 용도 |
|---|---|---|---|
| Blue (System) | `#007AFF` | `#0A84FF` | 기본 링크, 인터랙티브 요소 |
| Green | `#34C759` | `#30D158` | 성공, 수신, 확인 |
| Indigo | `#5856D6` | `#5E5CE6` | 그룹/카테고리 |
| Orange | `#FF9500` | `#FF9F0A` | 경고, 미디어 컨트롤 |
| Pink | `#FF2D55` | `#FF375F` | 소셜, 즐겨찾기 |
| Purple | `#AF52DE` | `#BF5AF2` | 앱 아이콘 강조 |
| Red | `#FF3B30` | `#FF453A` | 삭제, 위험 |
| Teal | `#5AC8FA` | `#64D2FF` | 알림, 강조 |
| Yellow | `#FFCC00` | `#FFD60A` | 경고, 즐겨찾기 별 |
| Mint | `#00C7BE` | `#63E6E2` | 건강, 피트니스 |
| Cyan | `#32ADE6` | `#32ADE6` | 제어 센터 아이콘 |
| Brown | `#A2845E` | `#AC8E68` | 카테고리 |

#### Semantic / Label Colors
| 이름 | 용도 | 중요도 |
|---|---|---|
| `Label` (Primary) | 기본 텍스트 | 최고 대비 |
| `Secondary Label` | 보조 텍스트 | 60% opacity |
| `Tertiary Label` | 힌트/placeholder | 30% opacity |
| `Quaternary Label` | 거의 보이지 않는 | 18% opacity |

#### Background Colors (iOS 고유 레이어 시스템)
| 레이어 | 색상 | 용도 |
|---|---|---|
| `systemBackground` | `#FFFFFF` | 앱 기본 배경 |
| `secondarySystemBackground` | `#F2F2F7` | 그룹화된 콘텐츠 배경 |
| `tertiarySystemBackground` | `#FFFFFF` | 3단계 배경 |
| `systemGroupedBackground` | `#F2F2F7` | 테이블뷰 그룹 배경 |

#### Separator & Fill
| 이름 | 용도 |
|---|---|
| `separator` | 구분선 (opaque) |
| `opaqueSeparator` | 완전 불투명 구분선 |
| `systemFill` | 배경 채우기 (버튼 등) |
| `secondarySystemFill` | 보조 채우기 |

### 2-2. Materials (Liquid Glass / Vibrancy)
iOS의 소재(Material)는 단순 색상이 아닌 **불투명도 + 블러 효과** 조합:

| 소재 | 용도 | 특성 |
|---|---|---|
| `Ultra Thin` | 오버레이 최소 | 배경 가장 많이 비침 |
| `Thin` | 팝업 배경 | 약간 불투명 |
| `Regular` | 카드, 툴바 배경 | 적당한 불투명도 |
| `Thick` | 모달, 시트 | 불투명도 높음 |
| `Ultra Thick` | 완전 차단 필요 시 | 거의 불투명 |
| `Chrome` | 상태바, 내비게이션 바 | 시스템 소재 |

### 2-3. 타이포그래피 (Dynamic Type 지원)

**기반 폰트**: SF Pro (Display, Text, Rounded 3가지 variant)
**중요**: iOS는 사용자가 시스템 글자 크기를 조절할 수 있음 → 고정 px 금지, Dynamic Type 사용 필수

| 스타일 | 기본 크기 | 굵기 | 용도 |
|---|---|---|---|
| Large Title | 34pt | 700 | 내비게이션 대형 제목 |
| Title 1 | 28pt | 700 | 주요 섹션 제목 |
| Title 2 | 22pt | 700 | 보조 섹션 제목 |
| Title 3 | 20pt | 600 | 소 섹션 제목 |
| Headline | 17pt | 600 | 카드/셀 제목 |
| Body | 17pt | 400 | **기본 본문** |
| Callout | 16pt | 400 | 보조 본문 |
| Subheadline | 15pt | 400 | 보조 정보 |
| Footnote | 13pt | 400 | 메타데이터 |
| Caption 1 | 12pt | 400 | 작은 설명 |
| Caption 2 | 11pt | 400 | 최소 크기 |

**SF Symbol**: 텍스트와 자동 정렬되는 시스템 아이콘 (SF Symbols 6.0+)

---

## 3. 모바일 고유 치수 규칙

### 3-1. 터치 타겟 — 절대 규칙
```
최소: 44 × 44pt  ← Apple HIG 강제 기준
권장: 48 × 48pt  ← 더 편안한 터치
```
> ❌ 버튼/아이콘을 24×24pt로 만드는 것 절대 금지 (터치 불가)

### 3-2. Safe Area Insets (iOS 26 기준)
```
iPhone 16: Status Bar 59pt, Home Indicator 34pt
iPad: 동적으로 변함 (Split View, Stage Manager 대응 필수)
```

### 3-3. 화면 크기 기준
| 기기 | 논리 해상도 | 스케일 |
|---|---|---|
| iPhone SE | 375 × 667pt | @2x |
| iPhone 15/16 | 393 × 852pt | @3x |
| iPhone 15/16 Plus | 430 × 932pt | @3x |
| iPhone 15/16 Pro Max | 430 × 932pt | @3x |
| iPad 11" | 834 × 1194pt | @2x |
| iPad 13" | 1024 × 1366pt | @2x |

### 3-4. 스페이싱 스케일 (iOS 기준)
```
4pt  → 최소 간격 (아이콘 내부)
8pt  → 관련 요소 간 간격
12pt → 보조 패딩
16pt → 기본 컨테이너 패딩 (가장 많이 사용)
20pt → 섹션 헤더 패딩
24pt → 그룹 간 간격
```

---

## 4. 컴포넌트 인벤토리 (iPhone 기준 주요 항목)

### 내비게이션 & 구조
`Navigation Bar`, `Tab Bar`, `Toolbar`, `Search Bar`, `Status Bar`, `Side Bar (iPad)`

### 입력 & 컨트롤
`Button` (Plain, Tinted, Gray, Filled), `Segmented Control`, `Stepper`, `Toggle/Switch`, `Slider`, `Text Field`, `Text View`, `Picker`, `Date Picker`

### 콘텐츠 표시
`List/Table View`, `Collection View`, `Card`, `Image View`, `Map View`, `Web View`

### 피드백 & 오버레이
`Alert`, `Action Sheet`, `Modal Sheet`, `Popover (iPad)`, `Toast/HUD`, `Activity Indicator`, `Progress View`

### iOS 고유 컴포넌트
`Live Activities`, `Dynamic Island`, `Widget`, `Control Widget`, `Spotlight`

---

## 5. iOS 버튼 시스템 (4가지 Style)

| 스타일 | 시각 | 용도 |
|---|---|---|
| `Filled` | 색 배경 (Primary) | 가장 중요한 액션 1개 |
| `Tinted` | 연한 색 배경 | 보조 액션 |
| `Gray` | 회색 배경 | 중립 액션 |
| `Plain` | 텍스트만 | 취소, 낮은 강조 |

Configuration 옵션:
- `large` / `medium` / `small` / `mini`
- `cornerRadius`: capsule(알약형), `8pt`, `12pt`
- `imagePlacement`: leading / trailing / top / bottom

---

## 6. iOS에서 배울 핵심 방법론

### 1) Dynamic Color 시스템
```swift
// 색상을 Hex로 정의하지 않고, 상황별 적응 색상으로 정의
let color = UIColor { traitCollection in
    traitCollection.userInterfaceStyle == .dark
        ? UIColor(hex: "#0A84FF")  // dark
        : UIColor(hex: "#007AFF")  // light
}
```
→ 웹에서도 CSS `prefers-color-scheme`과 변수 시스템으로 동일 패턴 적용 가능.

### 2) 소재(Material) 기반 레이어 시스템
배경을 단순 색상이 아닌 **소재 + 진동 효과(Vibrancy)** 개념으로 설계.
→ 웹 구현: `backdrop-filter: blur()` + 반투명 배경색

### 3) 적응형 레이아웃 (iPad Stage Manager)
모든 화면을 **컬럼 없이 유연한 constraint 기반**으로 설계해야 함.
→ 웹: CSS Grid + Container Queries와 동일한 개념.

---

## 7. 웹 vs 모바일 핵심 차이

| 항목 | 웹 | iOS |
|---|---|---|
| 단위 | px | pt |
| 최소 터치 영역 | 44px | 44pt |
| 스크롤 방향 | 주로 세로 | 세로 + 수평 패닝 |
| 폰트 시스템 | 고정 px | Dynamic Type (사용자 조정) |
| 오버레이 | 모달/다이얼로그 | Sheet / Popover |
| 내비게이션 | 탭/사이드바 | Navigation Stack |
| 뒤로가기 | 브라우저 버튼 | 스와이프 제스처 |
| 컨텍스트 메뉴 | 우클릭 | 길게 누르기 |
| 색상 시스템 | CSS 변수 | Dynamic Color |

---

## 8. 금지 규칙
```
❌ 터치 타겟 44pt 미만 설계 (탭 불가능)
❌ 고정 px 폰트 크기 (Dynamic Type 미지원 → 접근성 위반)
❌ Safe Area 무시 (홈 인디케이터/상태바와 콘텐츠 겹침)
❌ 길게 누르기 기능을 단순 탭과 중복 사용 (예측 불가)
❌ iOS에 없는 Hover 상태 설계 (터치 기기는 Hover 없음)
❌ 커스텀 내비게이션으로 시스템 제스처 차단 (스와이프백 등)
❌ 웹 px값을 그대로 iOS pt로 전환 (환경이 완전히 다름)
```
