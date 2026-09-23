---
name: Ant Design System 스킬
version: 1.0
source: https://www.figma.com/design/d0yziYro8boRYOl3F3AEZN/Ant-Design-System-for-Figma--Free-version---Community-
extracted: 2026-03-27
platform: Web (React 기반)
---

# Ant Design System 스킬

> **목적**: Ant Design의 체계적인 토큰 아키텍처와 컴포넌트 철학을 이해하고, 동일한 수준의 시스템을 직접 설계할 수 있게 된다.

---

## 1. Ant Design의 핵심 철학

### "자연미(Natural)" 디자인 원칙
```
Certainty    → 사용자가 결과를 예측할 수 있어야 함
Meaningful   → 모든 요소가 의미를 가져야 함
Growth       → 사용자와 함께 성장하는 디자인
Natural      → 자연스러운 인터랙션 패턴
```

### 토큰 계층 구조 (Design Tokens V2)
Ant Design의 가장 중요한 아키텍처 특징: **4단계 토큰 계층**

```
1. Seed Tokens (씨앗 토큰)
   └── 단 1-2개의 원본 값 (예: colorPrimary: #1677FF)
   
2. Map Tokens (맵 토큰) ← 자동 생성
   └── Seed에서 파생된 10단계 팔레트
       예: blue-1 ~ blue-10 자동 계산
   
3. Alias Tokens (별칭 토큰)
   └── 역할 기반 명칭 부여
       colorBgContainer, colorBorderSecondary 등
   
4. Component Tokens (컴포넌트 토큰)
   └── 컴포넌트별 오버라이드
       Button.colorPrimary, Input.colorBorder 등
```

**배울 점**: 색상 1개만 정하면 나머지 10단계가 자동 파생됨. → 테마 변경이 극단적으로 쉬워짐.

---

## 2. 디자인 토큰 (Figma API 추출 + 공식 스펙)

### 2-1. 색상 시스템

#### Seed Token (원본 — Figma에서 확인됨)
| 토큰 | Hex | 역할 |
|---|---|---|
| `colorPrimary` | `#1677FF` | 브랜드 주색 - 모든 Primary 파생의 원천 |
| `colorError` | `#FF4D4F` | 에러/Destructive |
| `colorWarning` | `#FAAD14` | 경고 |
| `colorSuccess` | `#52C41A` | 성공 |
| `colorInfo` | `#1677FF` | 정보 (Primary와 동일) |

#### 자동 파생 팔레트 (Map Tokens — Blue 예시)
| 단계 | Hex | 용도 |
|---|---|---|
| blue-1 | `#E6F4FF` | 선택 배경, 하이라이트 배경 |
| blue-2 | `#BAE0FF` | Hover 배경 |
| blue-3 | `#91CAFF` | Active 배경 |
| blue-4 | `#69B1FF` | 아이콘, 비활성 링크 |
| blue-5 | `#4096FF` | Primary Hover |
| blue-6 | `#1677FF` | **Primary (메인)** |
| blue-7 | `#0958D9` | Primary Active (눌림) |
| blue-8 | `#003EB3` | 강조 텍스트 |
| blue-9 | `#002C8C` | 다크 배경 |
| blue-10 | `#001D66` | 최강조 |

> **핵심 패턴**: 단계 6이 항상 Primary. 5는 Hover, 7은 Active. 1-3은 배경용.

#### 중성 색상 (Neutral Palette)
| 토큰 | Hex | 용도 |
|---|---|---|
| `colorBgContainer` | `#FFFFFF` | 카드/컨테이너 배경 |
| `colorBgLayout` | `#F5F5F5` | 페이지 레이아웃 배경 |
| `colorBorderSecondary` | `#F0F0F0` | 보조 경계선 |
| `colorBorder` | `#D9D9D9` | 기본 경계선 |
| `colorTextQuaternary` | `#BFBFBF` | 비활성/Placeholder |
| `colorTextTertiary` | `#8C8C8C` | 보조 텍스트 |
| `colorTextSecondary` | `#595959` | 2차 텍스트 |
| `colorText` | `#000000` (alpha 0.88) | 기본 텍스트 |

### 2-2. 타이포그래피 스케일 (Figma 추출)
**기반 폰트**: SF Pro Text (Figma), 실제 웹: `system-ui, -apple-system`

| 레벨 | 크기 | 굵기 | 줄높이 | Ant 토큰명 |
|---|---|---|---|---|
| H1 | 38px | 600 | 46px | `fontSizeHeading1` |
| H2 | 30px | 600 | 38px | `fontSizeHeading2` |
| H3 | 24px | 600 | 32px | `fontSizeHeading3` |
| H4 | 20px | 600 | 28px | `fontSizeHeading4` |
| XL Normal | 20px | 400 | 28px | `fontSizeXL` |
| LG (body) | 16px | 400/600 | 24px | `fontSize` (base) |
| MD (default) | 14px | 400/600 | 22px | `fontSizeSM` |
| SM | 12px | 400/600 | 20px | `fontSizeXS` |

> **Ant Design 기본 base**: `fontSize: 14px`, `lineHeight: 1.5714` (22px)

### 2-3. 스페이싱 스케일 (4px 기반)
```
xxs:  4px   (내부 아이콘-문자 간격)
xs:   8px   (컴포넌트 내부 소형 패딩)
sm:  12px   (컴포넌트 내부 패딩)
md:  16px   (기본 패딩)
lg:  20px   
xl:  24px   (섹션 간격)
2xl: 32px   
3xl: 48px   
4xl: 64px   (대형 섹션 간격)
```

### 2-4. Border Radius
```
borderRadiusSM:  4px   (태그, 배지)
borderRadius:    6px   (버튼, 입력, 기본)
borderRadiusLG:  8px   (카드, 모달)
borderRadiusXL: 16px   (대형 카드)
```

---

## 3. 컴포넌트 인벤토리 (Free 버전 기준 ✅)

### General
- `Button` — 5가지 타입 (Primary, Default, Dashed, Text, Link)
- `FloatButton` — 플로팅 액션 버튼
- `Icon` — 1000+ Ant Design 아이콘
- `Typography` — Text, Title, Paragraph, Link

### Navigation
- `Breadcrumb` — 현재 위치 경로
- `Dropdown` — 드롭다운 메뉴
- `Menu` — 사이드/탑 네비게이션
- `Pagination` — 페이지 이동
- `Steps` — 단계별 진행 표시
- `Anchor` — 페이지 내 앵커 링크

### Data Entry
- `Checkbox` — 다중 선택
- `Input` — 텍스트 입력 (+ Textarea, Password, Search)
- `Rate` — 별점 평가
- `Switch` — 토글
- `Upload` — 파일 업로드

### Data Display
- `Avatar` — 사용자 아이디앤티티
- `Badge` — 숫자/상태 표시
- `Image` — 이미지 + 미리보기
- `Popover` — 팝오버
- `Statistic` — 수치 데이터 표시
- `Tag` — 분류 레이블
- `Tour` — 온보딩 가이드

### Feedback
- `Message` — 전역 상단 알림
- `Skeleton` — 로딩 스켈레톤
- `Spin` — 로딩 스피너

---

## 4. 버튼 5-Type 시스템 (Ant 고유)
Ant Design은 버튼을 5가지로 분류한다:

| 타입 | 시각 | 사용 시점 |
|---|---|---|
| **Primary** | 파란 배경 + 흰 텍스트 | 가장 중요한 단 하나의 액션 |
| **Default** | 흰 배경 + 회색 테두리 | 보조 액션 |
| **Dashed** | 점선 테두리 | 추가/생성 (드래그 존 등) |
| **Text** | 텍스트만 | 낮은 강조, 클릭 가능한 텍스트 |
| **Link** | 파란 텍스트, 하이퍼링크처럼 | 링크 이동 |

> **Ant 고유 패턴**: `danger` prop 추가 시 어떤 타입이든 빨간색으로 변환.
> Primary + danger = `#FF4D4F` 배경 / Default + danger = 빨간 테두리

---

## 5. 상태 시스템

| 상태 | 색상 처리 | 토큰 |
|---|---|---|
| Default | 기본 토큰 색상 | — |
| Hover | Palette step 5 (Primary 기준) | `colorPrimaryHover` |
| Active | Palette step 7 | `colorPrimaryActive` |
| Disabled | `colorTextDisabled: rgba(0,0,0,0.25)` + 배경 `#F5F5F5` | `colorBgContainerDisabled` |
| Focus | `#1677FF` 0px 0px 0px 2px, alpha 0.2 shadow | `controlOutline` |
| Error | `#FF4D4F` + 에러 메시지 아래 표시 | `colorError` |

---

## 6. Ant Design에서 배울 핵심 방법론

### 시맨틱 토큰 명명 규칙
```
형식: color{역할}{변형}
예시:
  colorBg{Container/Layout/Elevated/Spotlight}
  colorBorder{Default/Secondary}
  colorText{Default/Secondary/Tertiary/Quaternary}
  colorFill{Default/Secondary/Tertiary/Quaternary}
```

### 테마 변경 아키텍처
```javascript
// Seed 1개 변경 → 전체 시스템 자동 업데이트
theme: {
  token: { colorPrimary: '#722ED1' }  // 보라색 테마로 전환
}
```
→ 새 프로젝트에 디자인 시스템 만들 때, Seed Token을 먼저 정의하고 나머지를 파생시키는 방식이 가장 확장성이 높다.

---

## 7. 금지 규칙
```
❌ 임의 파란색 사용 (#007bff, #0066CC 등) — 반드시 #1677FF 파생 팔레트 사용
❌ 스페이싱 4px 배수 외 사용 (5px, 7px, 9px 등)  
❌ borderRadius를 4/6/8px 외 임의 값으로 설정
❌ 컴포넌트 토큰 없이 글로벌 토큰을 직접 오버라이드
❌ Primary 버튼 2개 이상 (Ant도 동일 규칙 적용)
```
