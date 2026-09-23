# pt-deck-kit

**클로드코드에 나만의 발표자료 스킬을 만들어주는 키트.** 내려받아 폴더를 열고 말을 걸면, 클로드코드가 이 자료와 내 자료를 합쳐 **내 컴퓨터에 나 전용 `/PT제작` 스킬을 만든다.** 그 뒤엔 이 폴더 없이도 어느 프로젝트에서든 쓸 수 있다.

코딩을 몰라도 된다. 터미널 명령을 외울 필요도 없다.

`presentation` `slides` `claude-code` `skill` `korean` `발표자료` `PT` `슬라이드` `AI문체` `assertion-evidence`

---

## 무엇이 들어 있나

| 구성 | 내용 |
|---|---|
| **규칙 문서 3개** | 슬라이드 구조 / 화면 디자인(슬라이드 레이아웃 규칙 포함) / 문장 쓰기. 출처가 있는 규칙만 담았다 |
| **온보딩 절차** | 클로드코드가 내 자료를 하나씩 받아 프로파일을 만들고, 스킬을 생성하는 7단계 |
| **스킬 원형 2개** | 제작(만들면서 보는 절차)과 검수(다 만들고 디자인을 다시 정리하는 절차). 내 프로파일이 채워져 내 스킬이 된다 |
| **참고 자료** | 규칙의 원본 링크와 공개 디자인 시스템 4종(Ant Design·shadcn·iOS 26·Backstage) 정리본 |

규칙의 근거는 이렇다. 슬라이드 구조는 Alley의 주장-증거(Assertion-Evidence) 연구, 화면은 Atlassian·Ant Design 디자인 시스템과 Refactoring UI, 문장은 Williams·Gopen&Swan·국립국어원 자료, AI 문체 제거는 im-not-ai 분류체계다. 근거가 없는 관행("한 줄 6단어", "장당 1분")은 일부러 넣지 않았다.

**완성된 플러그인이 아니다.** 규칙과 절차만 있고, 스킬은 받은 사람의 클로드코드가 그 사람 자료로 만든다. 그래서 만든 사람의 컴퓨터나 환경과 아무 관계가 없다.

**스킬은 소재를 발표자료로 바꾸는 변환기다.** 무엇을 말할지(결론)와 근거 자료가 정리돼 있으면, 그것을 16:9 HTML 슬라이드로 만들고 PDF로 변환해 준다. 소재를 대신 만들어 주지는 않는다.

---

## 시작하기

### 1. 클로드코드 준비

클로드코드가 없다면 먼저 설치한다. 공식 안내를 따르면 된다.

- 설치 안내: https://docs.claude.com/en/docs/claude-code/quickstart
- 데스크톱 앱이나 VS Code 확장으로 써도 된다. 어느 쪽이든 아래 절차는 같다.

### 2. 이 저장소 내려받기

**방법 A — ZIP으로 받기 (제일 쉬움)**
1. 이 페이지 위쪽의 초록색 **Code** 버튼을 누른다
2. **Download ZIP**을 누른다
3. 압축을 풀어 원하는 위치에 둔다 (예: `문서\pt-deck-kit`)

**방법 B — git으로 받기**
```
git clone https://github.com/wse02123/pt-deck-kit.git
```

### 3. 폴더를 열고 말 걸기

1. 압축을 푼 `pt-deck-kit` 폴더에서 클로드코드를 연다
   - 터미널이라면 그 폴더로 이동해서 `claude`를 입력한다
   - VS Code라면 그 폴더를 열고 클로드코드 패널을 켠다
2. 아무 말이나 한다. "안녕"도 된다
3. 클로드가 세팅을 제안한다. **"세팅해서 스킬 만들기"를 고른다.** 10분 정도 걸린다

이게 전부다. 끝나면 클로드코드를 한 번 껐다 켜고, 어느 폴더에서든 `/PT제작`이라고 하면 된다.

---

## 세팅 때 무엇을 묻나

클로드가 네 가지를 **하나씩** 묻는다. 파일이 없으면 없는 대로 진행된다.

| 묻는 것 | 어떻게 주나 | 무엇이 달라지나 |
|---|---|---|
| 어떤 자료를 누구에게 만드나 | 질문에 답하기만 하면 된다 | 청중 수준과 경어체가 고정된다 |
| 예전에 만든 PT 파일 | `my/samples/` 폴더에 넣는다 | 색·폰트·제목 방식 같은 시각 패턴이 내 것으로 바뀐다 |
| 본인만의 제작 원칙 | 질문에 답하거나 메모를 넣는다 | 조직 양식과 피드백이 규칙보다 우선 적용된다 |
| 평소 쓰는 말투 | AI 없이 직접 쓴 글을 `my/samples/`에 넣는다 | 내 습관을 AI 문체로 오판해 지우는 일이 없어진다 |

그다음 클로드가 내 컴퓨터에 스킬을 만든다.

```
~/.claude/skills/pt-deck/     ← 내 설정 + 규칙 문서 사본. 이 폴더 없이도 돌아간다
~/.claude/commands/PT제작.md · PT검수.md · PT설정.md
```

`my/` 폴더는 깃에 올라가지 않으므로 개인 자료를 넣어도 된다.

---

## 만든 뒤에 쓰는 법

| 하고 싶은 것 | 이렇게 말한다 |
|---|---|
| 발표자료 만들기 | `/PT제작` 또는 "3분기 실적 보고 발표자료 만들어줘" |
| 만든 자료 점검 | `/PT검수` 또는 "이거 괜찮은지 봐줘" |
| 설정 보기·바꾸기 | `/PT설정` |
| 자료 더 넣기 | `/PT설정`에서 "이 파일 읽고 반영해줘" |
| 처음부터 다시 세팅 | 이 폴더를 다시 열고 말을 건다 |

발표자료를 만들 때 클로드는 **슬라이드별 주장 문장 목록을 먼저 보여주고 승인을 기다린다.** 구조를 확인하고 나서 화면을 만든다. 이 순서는 바꾸지 않는다.

---

## 폴더 구조

```
pt-deck-kit/
├─ CLAUDE.md                클로드코드가 읽는 온보딩과 규칙 (사람이 읽어도 된다)
├─ AGENTS.md                다른 AI 코딩 도구용 안내 (Codex·Cursor 등)
├─ TRUST.md                 이 저장소를 믿어도 되는 근거
├─ onboarding/세팅_절차.md   자료 수집 → 프로파일 → 스킬 생성 7단계
├─ guides/                  규칙 문서 3개 (스킬에 복사된다)
│  ├─ 01_PT자료_가이드.md
│  ├─ 02_디자인_가이드.md
│  └─ 03_글쓰기_가이드.md
├─ blueprints/              생성될 스킬의 원형
│  ├─ SKILL_PT제작.md        제작 스킬 (소재 → 슬라이드 → PDF)
│  ├─ SKILL_PT검수.md        검수 스킬 (완성본 디자인·문구 재정리)
│  ├─ commands/             /PT제작 /PT검수 /PT설정
│  └─ profile_templates/    개인 설정 빈 양식 4개
├─ references/              규칙 원본 링크 + 공개 디자인 시스템 정리본 4종
└─ my/                      세팅 중 내 자료를 두는 곳 (깃 제외)
   └─ samples/
```

---

## 이 저장소를 믿어도 되나

스타와 포크는 아직 없다. 대신 **직접 확인할 수 있는 근거**를 `TRUST.md`에 적어 두었다. 실행 코드가 없고 마크다운뿐이라는 것, 모든 규칙에 출처가 있다는 것, 근거 없는 관행을 뺐다는 것, 개인 자료 폴더가 깃에서 제외된다는 것. 각 항목에 확인 명령이 있다. AI 도구에게 "이 저장소 믿을 만한지 확인해줘"라고 하면 그 파일을 읽고 답한다.

---

## 자주 묻는 것

**결과물이 뭔가요?**
16:9 HTML 슬라이드를 만들고 크롬으로 PDF로 변환한다. PDF와 HTML 원본을 같이 받는다. PPT가 꼭 필요하면 클로드에게 말하면 되는데 별도 도구가 있어야 한다.

**규칙 문서를 고쳐도 되나요?**
이 저장소의 `guides/`는 그대로 두고, 세팅 때 "우리 회사는 이렇게 한다"고 말하면 그것이 규칙보다 우선 적용된다. 만든 뒤에는 `/PT설정`으로 바꾼다.

**세팅 없이 써도 되나요?**
된다. 이 폴더 안에서 "세팅 없이 한 번만 만들어보기"를 고르면 기본 규칙으로 만든다. 스킬은 생기지 않는다.

**내 자료가 어딘가로 올라가나요?**
`my/`는 `.gitignore`로 막혀 있어 깃에 올라가지 않는다. 생성된 스킬도 내 컴퓨터의 `~/.claude/` 안에만 있다. 클로드코드 자체의 데이터 처리는 Anthropic 정책을 따른다.

**클로드코드 말고 다른 도구에서도 되나요?**
`AGENTS.md`에 다른 AI 코딩 도구용 안내가 있다. 규칙 문서와 절차는 전부 마크다운이라 어느 도구든 읽을 수 있다. 다만 `/PT제작` 같은 슬래시 커맨드 생성은 클로드코드 기준으로 적었다.

---

## 라이선스

MIT. AI 문체 분류체계는 [im-not-ai](https://github.com/epoko77-ai/im-not-ai) (MIT)를 참조했다.

---

## English

**pt-deck-kit** is a Korean-first rule kit that lets Claude Code build a *personalized presentation-deck skill* on your machine. Download, open the folder, say hello. Claude walks you through four questions (audience, past decks, your own rules, your writing style), then writes `~/.claude/skills/pt-deck/` with your profile baked in. After that, `/PT제작` works from any project, and this folder is no longer needed.

Every rule in `guides/` cites its source (Alley's Assertion-Evidence research, Atlassian and Ant Design systems, Williams and Gopen & Swan on prose, the im-not-ai taxonomy for Korean AI-writing patterns). Folk rules without evidence were deliberately left out. No executable code, markdown only. See `TRUST.md` for verifiable claims and `AGENTS.md` for other AI coding tools.
