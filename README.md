# .github

Goodnight Camp 조직 공용 설정 — 지금은 **디자인 설정(oh-my-design)** 을 둔다.
앱 레포(`goodnight-camp`)에는 디자인 도구 파일을 넣지 않고, 결과물(Android 레이아웃·리소스)만 반영한다.

## 디자인 설정 (oh-my-design)

[oh-my-design](https://oh-my-design.kr/docs/en) `2.0.6` — AI 코딩 에이전트(Claude Code)가 `DESIGN.md`를 기준으로 UI를 만들게 하는 스킬 묶음.

| 경로 | 내용 |
|---|---|
| `.claude/skills/` | 디자인 스킬 32개 (디자인 시스템 초기화·적용·리뷰·한국어 문구 등) |
| `.claude/agents/` | 전문 서브에이전트 20개 (아트 디렉터, 접근성 감사, UX 라이터 등) |
| `.claude/data/references/<id>/DESIGN.md` | 디자인 레퍼런스 530개 오프라인 사본 |
| `.claude/hooks/`, `.claude/settings.json` | 프롬프트·편집 시 DESIGN.md 준수를 돕는 훅 (로컬 파일만 읽고 씀, 네트워크 없음) |
| `DESIGN.md`, `.omd/preferences.md` | (디자인 시스템을 정하면 생김) 팀이 합의한 디자인 기준 — 커밋해서 공유 |

### 쓰는 법

```bash
git clone https://github.com/Goodnight-Camp/.github.git
cd .github
claude            # 이 폴더에서 Claude Code 실행 → 스킬 자동 인식
```

처음 한 번, 디자인 시스템 잡기:

> 굿나잇 캠프 디자인 시스템 잡아줘. 차박하는 밤에 차 안 큰 화면(Pleos, 2560×1440 가로)으로 보는 앱이야.
> hyundai랑 asleep을 레퍼런스로, DESIGN.md 쓰기 전에 미리보기 먼저 보여줘.

이후 화면 작업은 `DESIGN.md` 기준으로 요청하고, 나온 결과를 `goodnight-camp`의 XML 레이아웃·`colors.xml`·`dimens.xml`에 옮긴다.

### 굿나잇 캠프에 맞는 레퍼런스

| id | 쓸 곳 |
|---|---|
| `hyundai` | 현대차 브랜드 톤 (verified_v2 — 실제 제품과 대조 검증됨) |
| `42dot` | 현대차그룹 차량 소프트웨어 — Pleos와 가까운 맥락 |
| `tesla` | 차량 인포테인먼트의 큰 터치 영역·단순한 정보 구조 |
| `asleep`, `headspace` | 수면·휴식 앱의 차분한 밤 분위기 |
| `toss` | 정보 위계, 숫자 강조, 한국어 문구 |

### 업데이트·점검

```bash
npx oh-my-design-cli@latest update --dir .
npx oh-my-design-cli@latest doctor --dir .
```

처음부터 다시 설치: `npx oh-my-design-cli@2.0.6 install-skills --dir . --agent claude-code --all --lang ko`
