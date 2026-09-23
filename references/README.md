# references — 외부 자료

`guides/`의 규칙이 어디서 왔는지, 더 깊이 볼 때 어디로 가면 되는지 모아 두었다. 스킬 생성 때 복사되지 않는다. 필요할 때 찾아본다.

## 이 폴더에 들어 있는 것

`design_systems/`에 공개 디자인 시스템 4종을 Figma Community 파일에서 토큰·컴포넌트 위주로 정리한 문서가 있다. 각 파일 머리에 원본 링크가 있다.

| 파일 | 원본 | 언제 보나 |
|---|---|---|
| `design_system_ant.md` | Ant Design System for Figma (Community, Free) | 정보 밀도 높은 기업용 화면. 토큰 계층 구조의 표준 예 |
| `design_system_shadcn.md` | shadcn/ui Design System (Community) | 무채색 기반 웹 UI. 절제된 톤이 필요할 때 |
| `design_system_ios26.md` | Apple iOS 26 Library (Community) | 모바일 앱 화면을 슬라이드에 재현할 때. 웹과 단위가 다르다 |
| `design_system_backstage.md` | Backstage Design System (Community) | 개발자 도구·내부 시스템 톤 |

조직에 디자인 시스템이 없고 참고할 톤을 고르고 싶을 때, 세팅 중에 이 넷 중 하나를 기준으로 삼을 수 있다. 어느 것을 고르든 `guides/02` 9장의 금지가 우선한다.

## 규칙의 원본 (직접 볼 곳)

### 슬라이드 구조
- Assertion-Evidence 공식 사이트 — https://www.assertion-evidence.com
- Alley 연구 (Penn State) — https://writing.engr.psu.edu/asee_5691.pdf
- Michael Alley, *The Craft of Scientific Presentations*, Springer (2013)
- Garr Reynolds, *Presentation Zen*

### 화면 디자인
- Atlassian Design System (간격·타이포 토큰) — https://atlassian.design
- Ant Design (팔레트 생성, 4px 그리드) — https://ant.design/docs/spec/colors
- IBM Carbon (타이포그래피) — https://carbondesignsystem.com/elements/typography/overview
- Material Design 3 (Color Role) — https://m3.material.io
- 토스 Seed Design System — https://seed.design
- Brad Frost, *Atomic Design* — https://atomicdesign.bradfrost.com
- Design Tokens W3C Community Group — https://www.designtokens.org
- Style Dictionary (토큰 3단계) — https://styledictionary.com
- Adam Wathan & Steve Schoger, *Refactoring UI* — https://www.refactoringui.com
- Pretendard 폰트 — https://github.com/orioncactus/pretendard
- WCAG 명도 대비 기준 — https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html

### AI티 안티패턴의 원본
- ui-ux-pro-max-skill (안티패턴 본목록, 업종별 192개 룰 포함) — https://github.com/nextlevelbuilder/ui-ux-pro-max-skill
- impeccable (pbakaus) — https://github.com/pbakaus/impeccable

업종별 세부 금지 항목이 필요하면 ui-ux-pro-max-skill 저장소의 `ui-reasoning.csv`를 본다. 이 키트에는 요약만 들어 있다.

### 문장
- Joseph M. Williams, *Style: Lessons in Clarity and Grace*
- Gopen & Swan, "The Science of Scientific Writing", *American Scientist* 78 (1990) — https://www.americanscientist.org/blog/the-long-view/the-science-of-scientific-writing
- Federal Plain Language Guidelines — https://www.plainlanguage.gov/guidelines
- 국립국어원 「쉬운 공문서 쓰기 길잡이」(2022) — https://www.korean.go.kr/front/etcData/etcDataView.do?mn_id=&etc_seq=700
- 국립국어원 「공공언어 바로 쓰기(개정판)」(2024) — https://www.korean.go.kr/front/etcData/etcDataView.do?mn_id=208&etc_seq=699
- Thomas & Turner, *Clear and Simple as the Truth* (Princeton)

### AI 문체
- im-not-ai (한국어 71패턴 분류체계, 정량 채점 스크립트, MIT) — https://github.com/epoko77-ai/im-not-ai
- imnotai.kr (웹 판정기. 대외비 문서 업로드 금지) — https://imnotai.kr
- Wikipedia: Signs of AI writing — https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing
- slop-gate (한국어 번역투 CLI, MIT) — https://github.com/hwajongpark/slop-gate

## 넣지 않은 것

- 타사 서비스 화면 스크린샷. 저작권 문제로 뺐다. 위 링크에서 직접 본다.
- 출처를 특정할 수 없는 분석 문서.
- HTML→PDF 변환 도구. 스킬이 사용자 환경의 브라우저를 쓰므로 별도 파일이 필요 없다.
