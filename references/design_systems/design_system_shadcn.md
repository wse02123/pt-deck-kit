---
name: shadcn/ui Design System 스킬
version: 1.0
source: https://www.figma.com/design/BaLdmCm8aiE4ujQjlwvA3D/-shadcn-ui---Design-System--Community-
extracted: 2026-03-27
platform: Web (React + Radix UI + Tailwind CSS)
---

# shadcn/ui Design System 스킬

> **목적**: shadcn/ui의 CSS 변수 기반 테마 시스템과 컴포넌트-퍼스트 철학을 이해하고, 동일한 수준의 적응형 색상 시스템을 직접 만들 수 있게 된다.

---

## 1. shadcn/ui의 핵심 철학

### "복사해서 소유하는" 컴포넌트
- npm 패키지가 아니라 **컴포넌트 코드를 직접 프로젝트에 복사**
- 완전한 커스터마이징 가능 → 라이브러리 업데이트에 종속되지 않음
- **Radix UI Primitives** 위에 구축 → 접근성 자동 보장

### CSS 변수 기반 적응형 색상 시스템
```css
/* 단 하나의 변수 세트, Light/Dark 자동 전환 */
:root {
  --background: 0 0% 100%;
  --foreground: 222.2 47.4% 11.2%;
  --primary: 222.2 47.4% 11.2%;
  --primary-foreground: 210 40% 98%;
}
.dark {
  --background: 224 71% 4%;
  --foreground: 213 31% 91%;
  --primary: 210 40% 98%;
  --primary-foreground: 222.2 47.4% 1.2%;
}
```

**배울 점**: 색상을 Hex가 아닌 **HSL로 저장**하면 Light/Dark 전환이 단순 변수 교체로 해결됨.

---

## 2. 디자인 토큰 (CSS Variable 시스템)

### 2-1. 시맨틱 색상 변수 체계

shadcn의 색상 이름 규칙: `{역할}` + `{역할}-foreground` (쌍으로 작동)

| 변수 | 역할 | 쌍 변수 |
|---|---|---|
| `--background` | 페이지 배경 | `--foreground` (기본 텍스트) |
| `--card` | 카드 배경 | `--card-foreground` |
| `--popover` | 팝오버 배경 | `--popover-foreground` |
| `--primary` | 주요 액션 색상 | `--primary-foreground` |
| `--secondary` | 보조 액션 색상 | `--secondary-foreground` |
| `--muted` | 흐린 배경/텍스트 | `--muted-foreground` |
| `--accent` | 강조/선택 배경 | `--accent-foreground` |
| `--destructive` | 삭제/위험 | `--destructive-foreground` |
| `--border` | 경계선 | — |
| `--input` | 입력 필드 테두리 | — |
| `--ring` | 포커스 링 색상 | — |

#### 기본 Light 테마 예시 (Figma 추출 색상 포함)
| 변수 | 값 (HSL) | 대략적 색상 |
|---|---|---|
| `--background` | `0 0% 100%` | `#FFFFFF` |
| `--foreground` | `222.2 84% 4.9%` | `#0F1629` |
| `--primary` | `221.2 83.2% 53.3%` | `#3B82F6` |
| `--secondary` | `210 40% 96.1%` | `#F1F5F9` |
| `--muted` | `210 40% 96.1%` | `#F1F5F9` |
| `--muted-foreground` | `215.4 16.3% 46.9%` | `#64748B` |
| `--border` | `214.3 31.8% 91.4%` | `#E2E8F0` |
| `--destructive` | `0 84.2% 60.2%` | `#EF4444` |
| `--ring` | `221.2 83.2% 53.3%` | `#3B82F6` (Primary와 동일) |

### 2-2. 타이포그래피
**기반 폰트**: Inter (기본), 프로젝트별 커스터마이징

| 역할 | 크기 | 굵기 | 줄높이 |
|---|---|---|---|
| Large Display | 36px+ | 700-800 | 1.1 |
| H1 | 30px | 700 | 1.2 |
| H2 | 24px | 600 | 1.25 |
| H3 | 20px | 600 | 1.3 |
| H4 | 18px | 600 | 1.35 |
| Body Large | 18px | 400 | 1.7 |
| Body | 16px | 400 | 1.7 |
| Body Small | 14px | 400 | 1.7 |
| Caption | 12px | 400 | 1.5 |

### 2-3. Border Radius
```css
--radius: 0.5rem; /* 기본: 8px */
/* 파생 */
--radius-sm: calc(var(--radius) - 4px);  /* 4px */
--radius-md: calc(var(--radius) - 2px);  /* 6px */
--radius-lg: var(--radius);              /* 8px */
--radius-xl: calc(var(--radius) + 4px);  /* 12px */
```
> **핵심**: `--radius` 하나만 바꾸면 전체 컴포넌트 radius가 일관되게 변함.

### 2-4. 스페이싱 (Tailwind 연동)
shadcn/ui는 Tailwind의 스페이싱 스케일을 그대로 사용:
```
0.5 = 2px
1   = 4px
2   = 8px
3   = 12px
4   = 16px
6   = 24px
8   = 32px
12  = 48px
16  = 64px
```

---

## 3. 컴포넌트 인벤토리 (Figma 73개 추출)

### Inputs & Controls
`Button`, `Input`, `Textarea`, `Select`, `Checkbox`, `Radio Group`, `Switch`, `Slider`, `Date Picker`, `Time Picker`, `File Input`, `Toggle`, `Toggle Group`

### Display & Layout
`Card`, `Table`, `Badge`, `Avatar`, `Separator`, `Skeleton`, `Aspect Ratio`, `Scroll Area`, `Resizable`

### Navigation
`Navigation Menu`, `Tabs`, `Breadcrumb`, `Pagination`, `Sidebar`, `Menubar`, `Command`

### Overlay & Feedback
`Dialog`, `Drawer`, `Sheet`, `Alert Dialog`, `Popover`, `Tooltip`, `Toast`, `Alert`, `Progress`, `Sonner`

### Typography & Content
`Typography` (h1-h4, p, lead, large, small, muted, blockquote, inline code, list)

---

## 4. 버튼 Variant 시스템 (shadcn 방식)

| Variant | 시각 | 용도 |
|---|---|---|
| `default` | Primary 색 배경 | 주요 액션 |
| `secondary` | 회색 배경 | 보조 액션 |
| `outline` | 테두리만 | 덜 강조된 액션 |
| `ghost` | 투명, Hover만 배경 | 메뉴 아이템, 아이콘 버튼 |
| `link` | 텍스트 링크 스타일 | 링크 이동 |
| `destructive` | 빨간 배경 | 삭제/위험 |

Size 옵션: `sm`, `default`, `lg`, `icon`

---

## 5. shadcn에서 배울 핵심 방법론

### 1) HSL 변수 기반 색상 시스템
```css
/* ❌ 하드코딩 방식 */
background-color: #3B82F6;

/* ✅ shadcn 방식 — 테마 전환이 자유로움 */
background-color: hsl(var(--primary));
```
→ 새 프로젝트에서 다크모드를 처음부터 지원하려면 HSL 변수 시스템을 써야 한다.

### 2) Foreground 쌍 원칙
모든 배경 색상에는 반드시 그 위에 올라갈 텍스트 색상을 쌍으로 정의:
```
배경: --primary → 텍스트: --primary-foreground
배경: --card → 텍스트: --card-foreground
```
→ 대비 문제 없이 어떤 배경에도 읽기 좋은 텍스트 보장.

### 3) `cn()` 유틸리티 패턴
```typescript
// clsx + tailwind-merge 조합
className={cn("base-classes", conditionalClass && "conditional", props.className)}
```
→ 컴포넌트 기본 스타일 + 외부 커스터마이징 동시 지원.

---

## 6. 금지 규칙
```
❌ CSS 변수 대신 직접 Hex/HSL 값 하드코딩
❌ Light/Dark 모드 색상을 별도 클래스로 관리 (변수로 처리해야 함)
❌ Tailwind 스케일 외 임의 px 값 사용
❌ Button의 foreground 색상을 배경과 비슷하게 설정 (대비 부족)
❌ destructive 타입 없이 삭제 액션에 일반 버튼 사용
```
