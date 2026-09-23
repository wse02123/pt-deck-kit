---
name: UI 시스템 마스터 스킬 (Backstage Design System 기반)
version: 1.0
source: https://www.figma.com/design/OQV8KEDl7B4R1UvQ4NerKf/Backstage-Design-System--Community-
extracted: 2026-03-27
token_expiry: 2026-06-25
---

# 🎨 UI 시스템 마스터 스킬

> **이 파일의 목적**: 디자이너·개발자 페르소나가 화면을 설계·구현할 때 판단 기준으로 사용하는 완전한 UI 시스템 지식.
> 단순 데이터 참조가 아니라 **"왜 이렇게 해야 하는가"까지 포함**한 판단 가이드.

---

## 1. UI 시스템 구성 요소 전체 인벤토리

UI 시스템은 아래 5계층으로 구성된다. 새 화면 설계 시 반드시 이 계층을 따라 위→아래 순서로 조립한다.

```
┌─────────────────────────────────────┐
│  5. PAGES     (실제 서비스 화면)       │
│  4. TEMPLATES (레이아웃 뼈대)          │
│  3. ORGANISMS (복합 UI 블록)           │
│  2. MOLECULES (기능 단위 조합)         │
│  1. ATOMS     (최소 UI 단위)           │
└─────────────────────────────────────┘
```

### 레벨 1: Atoms (최소 단위 — 더 이상 쪼갤 수 없는 것)
| 요소 | Figma 컴포넌트 명 | 설명 |
|---|---|---|
| 버튼 | `Button / Primary`, `Button / Secondary`, `Button / Text` | 단독 액션 유발 |
| 아이콘 | `Icon / *` | 단독 사용 불가, 텍스트와 함께 사용 권장 |
| 뱃지 | `Badge / *` | 숫자/상태 표시 |
| 태그/칩 | `Chip / *` | 필터, 선택 상태 표시 |
| 입력 필드 | `Input / *` | 텍스트 입력 |
| 드롭다운 | `Dropdown / *` | 선택지 제공 |
| 체크박스 | `Checkbox / *` | 다중 선택 |
| 라디오 | `Radio / *` | 단일 선택 |
| 스위치 | `Toggle / *` | 켜기/끄기 |
| 아바타 | `Avatar / *` | 유저 식별자 |
| 로딩 스피너 | `Progress / *` | 대기 상태 |

### 레벨 2: Molecules (기능 단위 조합)
| 요소 | 구성 | 설명 |
|---|---|---|
| 검색바 | Input + Icon(Search) + Button | 검색 입력 |
| 폼 필드 | Label + Input + Helper/Error Text | 데이터 입력 단위 |
| 탭 | Tab Item × N | 뷰 전환 |
| 브레드크럼 | Link × N + `/` 구분자 | 위치 표시 |
| 페이지네이션 | Button(이전) + Page Numbers + Button(다음) | 페이지 이동 |
| 상태 칩 | Color Dot + Label | 상태 시각화 |

### 레벨 3: Organisms (복합 UI 블록)
| 요소 | Figma 페이지 | 구성 |
|---|---|---|
| 카드 | `Cards` | Card Base + Header variant + Footer/CTA |
| 헤더 | `Header (w/ Breadcrumbs)` | Logo + Navigation + Actions |
| 사이드 내비게이션 | `Side Navigation` | 메뉴 아이템 tree |
| 테이블 | `Table` | Header Row + Data Rows + (Pagination) |
| 필터 패널 | `Filters` | 다중 필터 조합 |
| 폼/다이얼로그 | `Form Validation` | 복합 입력 + 에러 처리 |
| 배너 | `Dismissable Banner` | 경고/알림 전역 표시 |
| 사이드 패널 | `Side Panel` | 슬라이드 인 상세 패널 |
| 스테퍼 | `SimpleStepper` | 단계별 진행 |

### 레벨 4: Templates (레이아웃 뼈대)
| 패턴 | 구성 |
|---|---|
| 대시보드 | SideNav + Header + Card Grid |
| 디테일 페이지 | Header(Breadcrumb) + Detail Card + 관련 카드들 |
| 목록 페이지 | Header + Filter + Table + Pagination |
| 설정 페이지 | Side Tab + Form Sections |

---

## 2. 디자인 토큰 (원본 Figma API 추출값 — 100% 정확)

### 2-1. 색상 시스템

#### 그레이 스케일 (UI 기반색)
| 토큰명 | Hex | 주요 용도 |
|---|---|---|
| `color-black` | `#000000` | 최강 대비 텍스트 |
| `color-gray-900` | `#181818` | 다크 배경 |
| `color-gray-800` | `#282828` | 다이얼로그 배경 |
| `color-gray-700` | `#333333` | 보조 배경 |
| `color-gray-600` | `#404040` | 비활성 요소 배경 |
| `color-gray-500` | `#616161` | 비활성 아이콘, 비활성 텍스트 |
| `color-gray-400` | `#757575` | Placeholder, 힌트 텍스트 |
| `color-gray-300` | `#9E9E9E` | 경계선(Border) |
| `color-gray-200` | `#BDBDBD` | Disabled 상태 |
| `color-gray-100` | `#D9D9D9` | 구분선(Divider) |
| `color-gray-050` | `#EEEEEE` | 카드 배경 |
| `color-gray-025` | `#F8F8F8` | 페이지 배경 |
| `color-white` | `#FFFFFF` | 기본 배경, 반전 텍스트 |

#### 브랜드 & 상태 색상
| 토큰명 | Hex | 용도 |
|---|---|---|
| `color-primary` | `#2E77D0` | 주요 액션 버튼, 링크, 선택 상태 |
| `color-primary-hover` | `#388AED` | Primary 호버 상태 |
| `color-destructive` | `#E22134` | 삭제, 비가역적 액션, 에러 |
| `color-warning` | `#FFED51` | 경고 상태 |
| `color-warning-light` | `#FDFB9F` | 경고 배경 영역 |
| `color-success` | `#1DB954` | 성공, 완료, 정상 |
| `color-info` | `#FF9800` | 정보성 경고 |
| `color-teal` | `#9BF0E1` | 진행률, 액센트 |
| `color-teal-dark` | `#69DDC7` | 진행률 (짙은 버전) |
| `color-brand-pink` | `#F037A5` | 브랜드 강조 |

### 2-2. 타이포그래피 스케일
**기반 폰트**: Helvetica Neue (fallback: Arial, sans-serif)

| 레벨 | 크기 | 굵기 | 줄높이 | 자간 | 사용 시점 |
|---|---|---|---|---|---|
| Display 1 | 80px | 700 | 88px | -2.0 | 히어로/랜딩 헤드라인 |
| Display 2 | 48px | 700 | 56px | -1.0 | 대형 섹션 제목 |
| Heading 1 | 32px | 700 | 40px | -0.5 | 페이지 대표 제목 |
| Heading 2 Bold | 24px | 700 | 32px | -0.25 | 주요 섹션 제목 |
| Heading 2 Regular | 24px | 400 | 32px | -0.25 | 보조 섹션 |
| Heading 3 | 18px | 500 | 26px | -0.25 | 카드 제목, 서브 섹션 |
| Body 1 Bold | 16px | 700 | 24px | 0 | 강조 본문 |
| Body 1 Medium | 16px | 500 | 24px | 0 | 기본 본문 |
| CTA | 14px | 700 | 16px | +1.0 | 버튼 레이블 (반드시 대문자) |
| Body 2 | 14px | 500 | 20px | 0 | 보조 설명, 메타데이터 |
| Caption Bold | 12px | 700 | 20px | +0.25 | 강조 캡션 |
| Caption Medium | 12px | 500 | 20px | +0.25 | 일반 캡션, 타임스탬프 |
| Overline | 10px | 700 | 14px | +0.25 | 카테고리 라벨 (항상 대문자) |
| Breadcrumb | 10px | 400 | 14px | +0.25 | 브레드크럼 경로 |

### 2-3. 스페이싱 스케일 (8px Grid 기반)
모든 여백, 패딩, 간격은 반드시 아래 스케일 중 하나를 사용한다:
```
4px  →  xs  (아이콘-텍스트 사이 등 최소 간격)
8px  →  sm  (컴포넌트 내부 여백)
12px →  md- (작은 컴포넌트 간 간격)
16px →  md  (기본 컴포넌트 내부 패딩)
24px →  lg  (컴포넌트 간 기본 간격)
32px →  xl  (섹션 내부 간격)
48px →  2xl (섹션 간 간격)
64px →  3xl (대형 섹션 간격)
```
> [!CAUTION]
> **임의 px 절대 금지**: 13px, 17px, 22px 같은 스케일 외 값 사용 불가.

### 2-4. Border Radius
| 레벨 | 값 | 용도 |
|---|---|---|
| None | 0px | 테이블 셀, 구분선 |
| Small | 4px | 칩, 배지, 작은 버튼 |
| Medium | 8px | 입력 필드, 일반 버튼 |
| Large | 12px | 카드, 모달 |
| Full | 9999px | 알약형 태그, 아바타 |

---

## 3. 컴포넌트별 사용 규칙

### 3-1. 버튼 계층 규칙 ⚠️ 가장 중요

```
화면 분석 → 가장 중요한 액션 1개 → Primary
          → 보조 액션 → Secondary
          → 이탈·취소 → Text
          → 삭제·위험 → Destructive (항상 확인 다이얼로그 동반)
```

| 강조 수준 | 컴포넌트 | 화면당 허용 개수 | 색상 |
|---|---|---|---|
| **Highest** | `Button / Primary` | **1개만** | `#2E77D0` 배경 + 흰 텍스트 |
| **Medium** | `Button / Secondary` | 제한 없음 | 투명 배경 + `#2E77D0` 테두리/텍스트 |
| **Low** | `Button / Text` | 제한 없음 | 텍스트만, 배경/테두리 없음 |
| **Danger** | Destructive 변형 | 1개만 | `#E22134` |
| **Inactive** | `Button / * Disabled` | — | `#333333` 배경 + `#616161` 텍스트 |

**금지 패턴**:
- ❌ Primary 버튼 2개 이상을 같은 화면에 배치
- ❌ Destructive 버튼을 확인 없이 직접 실행
- ❌ Secondary와 Text를 같은 위계로 혼용

### 3-2. 카드 선택 규칙

| 상황 | 사용 카드 | Figma 컴포넌트 |
|---|---|---|
| 단순 정보 표시 | 기본 카드 | `Card` (Header/Plain + Footer/CTA) |
| 여러 뷰 탭 전환 | 탭 카드 | `Card - Advanced` (Header/Tabbed) |
| 드롭다운으로 데이터 전환 | 피벗 카드 | `Card - Advanced` (Header/Pivot) |
| 부제목과 함께 정보 제공 | 서브헤드 카드 | `Card - Advanced` (Header/Subhead) |

### 3-3. 상태(Status) 색상 사용 규칙
| 상태 | 색상 | 텍스트 색상 | 금지 |
|---|---|---|---|
| 성공/정상 | `#1DB954` | 흰색 또는 다크 | 성공에 파란색 사용 금지 |
| 경고 | `#FFED51` | `#333333` (짙은 색) | 경고에 흰 텍스트 금지 (대비 부족) |
| 에러/위험 | `#E22134` | 흰색 | — |
| 정보 | `#2E77D0` | 흰색 | — |
| 비활성 | `#9E9E9E` | `#F8F8F8` | — |

---

## 4. 상태(State) 시스템 — 모든 인터랙티브 요소 필수

모든 클릭 가능한 요소는 아래 5가지 상태를 반드시 설계한다:

```
Default → Hover → Active (Pressed) → Disabled
                                   → Error (입력 요소)
```

| 상태 | 시각적 처리 | 주의사항 |
|---|---|---|
| Default | 기본 디자인 | — |
| Hover | 배경 밝기 10-15% 조정 또는 Primary는 `#388AED` | 명확히 구분되어야 함 |
| Active | 더 어두운 색조 또는 눌림 효과 | — |
| Disabled | `#333333` 배경 + `#616161` 텍스트 | `cursor: not-allowed` |
| Focus | 2px 파란 아웃라인 (`#2E77D0`) | 키보드 접근성 필수 |
| Error | `#E22134` 하이라이트 + 에러 메시지 | 아이콘 동반 권장 |

---

## 5. 레이아웃 시스템

### 5-1. 그리드

| 중단점 | 컬럼 수 | 거터 | 마진 |
|---|---|---|---|
| Mobile (<768px) | 4 col | 16px | 16px |
| Tablet (768-1024px) | 8 col | 24px | 24px |
| Desktop (>1024px) | 12 col | 24px | 32px |

### 5-2. 레이아웃 패턴 (Figma에서 확인된 템플릿)
```
[사이드 내비게이션 240px] | [메인 콘텐츠 영역 auto]
                           ├── [헤더 + 브레드크럼]
                           ├── [콘텐츠 카드 그리드]
                           └── [사이드 패널 320px (선택)]
```

---

## 6. 인터랙션 패턴 표준

### 6-1. 폼 유효성 검사
```
입력 중       → 기본 스타일 유지
포커스 아웃   → 즉시 유효성 검사 실행
에러 발생     → 빨간 테두리 (#E22134) + 에러 메시지 (아이콘 포함)
성공          → 초록 체크 (#1DB954) 또는 기본으로 복귀
```

### 6-2. 로딩 상태
| 상황 | 처리 방법 |
|---|---|
| 페이지 최초 로딩 | Skeleton Screen (회색 플레이스홀더) |
| 버튼 클릭 후 처리 중 | 버튼 내 스피너 + 버튼 비활성화 |
| 데이터 갱신 중 | 기존 데이터 표시 + 상단 Progress Bar |
| 부분 로딩 | 카드 단위 Skeleton |

### 6-3. 빈 상태 (Empty State) — `Empty States` 페이지 참고
```
[일러스트 또는 아이콘]
[설명 텍스트 - Body 1 / Gray 400]
[Primary 버튼 - 주요 행동 유도]
```
> 빈 상태에서는 반드시 "다음에 할 수 있는 행동"을 제시한다.

### 6-4. 에러 상태 — `Error States` 페이지 참고
```
[에러 아이콘 - Destructive Red]
[에러 제목 - Heading 3]
[설명 - Body 2]
[재시도 버튼 - Secondary] [뒤로 가기 - Text]
```

---

## 7. 접근성 기준 (A11y)

| 항목 | 기준 |
|---|---|
| 색상 대비 | 일반 텍스트 ≥ 4.5:1 / 대형 텍스트(18px+ 또는 Bold 14px+) ≥ 3:1 |
| 포커스 표시 | 항상 가시적 (`#2E77D0` 2px 아웃라인) |
| 아이콘 단독 사용 | `aria-label` 필수 또는 텍스트 동반 |
| 에러 메시지 | 색상만으로 전달하지 말 것 → 텍스트/아이콘 병행 |
| 클릭 영역 | 최소 44×44px (터치 대응) |
| 색각 이상 | 빨강/초록만으로 상태 구분 금지 → 아이콘/텍스트 병행 |

---

## 8. 절대 금지 규칙 (AI 디자인 실수 방지)

> [!WARNING]
> 아래 규칙을 위반하면 디자인 시스템이 무너진다. 예외 없음.

```
❌ 스케일 외 임의 색상 사용 (예: #1a73e8, #ff5959 등 정의되지 않은 값)
❌ 스케일 외 임의 px 여백 사용 (예: 13px, 22px)
❌ Primary 버튼을 화면당 2개 이상 배치
❌ Destructive 액션에 확인 다이얼로그 없이 즉시 실행
❌ 상태(State) 없는 인터랙티브 요소 설계 (Hover/Disabled 최소 필수)
❌ 빈 상태(Empty State)를 빈 화면으로 방치
❌ 폼 에러를 색상만으로 표현 (텍스트 에러 메시지 필수)
❌ 경고색(#FFED51)에 흰색 텍스트 사용 (대비 부족)
❌ 새 컴포넌트를 기존 컴포넌트 확인 없이 만들기 (항상 인벤토리 먼저 확인)
❌ 타이포그래피 스케일 외 폰트 크기 사용 (예: 15px, 17px)
```

---

## 9. 신규 화면 설계 체크리스트

새 화면을 설계할 때 이 순서로 점검한다:

```
[ ] 1. 이 화면의 "단 하나의 Primary 액션"이 명확한가?
[ ] 2. 사용하는 모든 컴포넌트가 인벤토리에 존재하는가?
[ ] 3. 색상이 모두 토큰 목록 내의 값인가?
[ ] 4. 여백이 8px 그리드를 따르는가?
[ ] 5. 모든 인터랙티브 요소에 Hover/Disabled 상태가 있는가?
[ ] 6. 빈 상태/에러 상태/로딩 상태를 모두 설계했는가?
[ ] 7. 색상 대비가 4.5:1 이상인가?
[ ] 8. 사용자가 "학습 없이" 액션을 발견할 수 있는가?
```

---

## 10. Figma API 재추출 방법

```powershell
# 새 데이터 추출 시 실행 (90일마다 token 갱신 필요)
# Token 위치: .agents/config/figma_config.md
# Token 만료: 2026-06-25

python C:\tmp\parse_figma.py
# → .agents/skills/design_system_backstage.md 업데이트
```

페이지별 Node ID:
| 페이지 | ID |
|---|---|
| Type | `2:329` |
| Color | `2:394` |
| Buttons | `184:0` |
| Cards | `2:397` |
| Chips | `404:1` |
| Header | `2:396` |
| Side Navigation | `2:395` |
| Table | `2:399` |
| Tabs | `2:401` |
| Filters | `523:0` |
| Status | `2:400` |
| Progress | `140:0` |
| Empty States | `552:1816` |
| Error States | `636:887` |
| Form Validation | `831:0` |
| Side Panel | `1145:0` |
