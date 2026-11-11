# Goodnight Camp Design System

<!-- design-md:section experience -->
## 1. 경험

<!-- design-md:claim scope kind=product-surface lang=ko -->
### Scope

전기차 차박(차 안에서 하룻밤)을 위한 차량 인포테인먼트 앱. 잠들기 전 배터리·공조 계획을 세우고, 자는 동안 화면을 어둡게 유지하며, 아침에 차가 성에 제거·조명·환기로 깨운 뒤 집으로 출발시키는 하룻밤의 흐름을 담는다.
<!-- design-md:claim-end -->

<!-- design-md:claim primary-tasks kind=user-outcomes count=4 lang=ko -->
### Primary tasks

- 기상 시각·목적지·온도·여유 배터리·인원을 정하고 밤 계획 만들기

- 아침까지 남는 배터리와 집까지 필요한 배터리를 한눈에 확인하기

- 수면 중 어두운 화면에서 기상까지 남은 시간 확인하기

- 기상 후 밤새 기록을 보고 집으로 경로 안내 시작하기
<!-- design-md:claim-end -->

### Design direction

- 밤 화면(설정·계획·캠핑·수면)은 현대 네이비를 깊게 낮춘 다크 테마, 아침 기상 화면만 밝은 라이트 테마로 바꿔 시간의 흐름을 표현한다

- 현대(hyundai 레퍼런스)의 절제된 네이비·청록 톤과 그림자 없는 평면 구성을 분위기 근거로 삼는다

- 차량 화면 거리에서 읽히도록 숫자는 크게, 라벨은 작고 흐리게 — 정보 위계는 크기와 명도로만 만든다

### Principles

- 밤에 눈부시지 않게: 다크 배경 위 큰 흰 면이나 채도 높은 넓은 면을 쓰지 않는다

- 한 화면에 강조색 하나: 청록(시안)은 지금 누를 수 있는 핵심 동작과 진행 상태에만 쓴다

- 숫자가 주인공: 배터리 %, 시각, 남은 시간은 가장 큰 글자로, 단위와 라벨은 보조로

- 운전석에서 닿는 크기: 터치 대상은 최소 높이 88dp(1920 기준) 이상을 유지한다

### Avoid

- Hyundai Sans 등 라이선스 없는 현대 전용 글꼴 사용 또는 그렇게 표기하기

- 카드마다 그림자·두꺼운 테두리를 겹쳐 쓰는 장식

- 밤 화면에서 순백(#FFFFFF) 넓은 면이나 채도 높은 배경

- 강조색을 여러 개 동시에 쓰는 무지개 상태 표시

<!-- design-md:section foundations -->
## 2. 기반

<!-- design-md:claim foundations kind=rules-or-constraints lang=ko -->
### Semantic tokens

- **border.card**: `1dp` — 카드 테두리 두께
- **color.morning.accent**: `#002C5F` — 아침 테마 핵심 버튼 (현대 네이비)
- **color.morning.accent-pressed**: `#001F44` — 아침 테마 핵심 버튼 눌림
- **color.morning.accent-soft**: `#006B8F` — 아침 테마 아이콘·진행 표시 강조 (청록)
- **color.morning.background**: `#F4F6F9` — 아침(기상) 테마 앱 배경
- **color.morning.border**: `#DDE3EA` — 아침 테마 카드 테두리
- **color.morning.negative**: `#C42E12` — 아침 테마 경고
- **color.morning.positive**: `#007A48` — 아침 테마 정상·완료
- **color.morning.surface**: `#FFFFFF` — 아침 테마 카드 면
- **color.morning.surface-high**: `#E9EDF2` — 아침 테마 높은 면
- **color.morning.text-primary**: `#0A1B30` — 아침 테마 주 텍스트 (네이비 잉크)
- **color.morning.text-tertiary**: `#A30A1B30` — 아침 테마 라벨
- **color.morning.warm**: `#A85A00` — 아침 테마 따뜻한 강조
- **color.night.accent**: `#00AAD2` — 밤 테마 핵심 동작 버튼 (현대 시안 계열)
- **color.night.accent-pressed**: `#0090B3` — 밤 테마 핵심 버튼 눌림
- **color.night.accent-soft**: `#5CC8E8` — 밤 테마 아이콘·진행 표시 강조
- **color.night.background**: `#0B1322` — 밤 테마 앱 배경 (깊은 네이비)
- **color.night.border**: `#22334D` — 밤 테마 카드 테두리
- **color.night.info**: `#4DA3FF` — 밤 테마 정보
- **color.night.negative**: `#FF6A4D` — 밤 테마 경고·부족
- **color.night.on-accent**: `#06121F` — 시안 버튼 위 텍스트
- **color.night.positive**: `#2BD98A` — 밤 테마 정상·완료
- **color.night.surface**: `#121D30` — 밤 테마 카드 면
- **color.night.surface-high**: `#1B2940` — 밤 테마 높은 면 (아이콘 박스, 세그먼트 트랙)
- **color.night.text-primary**: `#F2F5F9` — 밤 테마 주 텍스트
- **color.night.text-quaternary**: `#6BF2F5F9` — 밤 테마 힌트 (42%, 큰 글자 전용)
- **color.night.text-secondary**: `#D9F2F5F9` — 밤 테마 보조 텍스트 (85%)
- **color.night.text-tertiary**: `#A3F2F5F9` — 밤 테마 라벨 (64%)
- **color.night.warm**: `#FFA233` — 밤 테마 난방·일출 따뜻한 강조
- **color.sleep.background**: `#05080F` — 수면 중 화면 배경
- **color.sleep.text**: `#66FFFFFF` — 수면 중 텍스트 (40%)
- **elevation.card**: `0dp` — 카드 그림자 없음 — 면 명도 차이로만 구분
- **radius.button**: `14dp` — 버튼 모서리 (2560 기준)
- **radius.card**: `16dp` — 카드 모서리 (2560 기준, 기존 32dp에서 절반으로 줄여 각진 인상)
- **radius.control**: `12dp` — 아이콘 버튼·아이콘 박스 모서리 (2560 기준)
- **size.touch-min**: `88dp` — 1920 기준 최소 터치 높이 (2560에서 비례 확대)

### Contrast pairs

- color.night.text-primary on color.night.surface: minimum 4.5:1
- color.night.text-tertiary on color.night.surface: minimum 4.5:1
- color.night.on-accent on color.night.accent: minimum 4.5:1
- color.night.accent-soft on color.night.surface: minimum 4.5:1
- color.morning.text-primary on color.morning.surface: minimum 4.5:1
- color.morning.text-tertiary on color.morning.surface: minimum 4.5:1
- color.morning.accent-soft on color.morning.surface: minimum 4.5:1
- color.sleep.text on color.sleep.background: minimum 3:1

### Reduced motion

Required.

### Foundation rules

- 색은 Android colors.xml 토큰 이름(background_primary, surface_basic, text_primary 등)을 유지하고 값만 바꾼다 — 밤 값은 values-night, 아침 값은 values

- 앱 기본은 밤 테마로 고정하고 기상 화면(WakeActivity)만 아침 테마로 연다

- 카드는 그림자 없이 1dp 테두리와 면 명도 차이로만 구분한다

- 강조색(accent)은 화면당 주 동작 하나에만 채운다. 나머지 버튼은 반투명 기본 버튼
<!-- design-md:claim-end -->

<!-- design-md:section typography-assets -->
## 3. 타이포그래피와 에셋

### Type roles

| Role | Usage | Family | Size | Weight | Line height |
|---|---|---|---|---|---|
| display-number | 배터리 %, 남은 시간 등 핵심 숫자 | Asta Sans | 56sp (2560 기준) | 700 | 1.1 |
| headline | 화면 헤드라인 (예: 20°C로 아침까지 따뜻하게 잘 수 있어요) | Asta Sans | 52sp (2560 기준) | 700 | 1.25 |
| card-title | 카드 제목 | Asta Sans | 28sp (1920 기준) | 700 | 1.3 |
| body | 설정 값·행 텍스트 | Asta Sans | 26sp (1920 기준) | 500 | 1.35 |
| label | 지표 라벨·보조 설명 | Asta Sans | 22sp (1920 기준) | 500 | 1.35 |
| sleep-clock | 수면 중 큰 시계 | Asta Sans | 165sp (1920 기준) | 300 | 1 |

### Assets

| Asset | Kind | Source status | License status | Source | Notes |
|---|---|---|---|---|---|
| asta-sans | font | official | verified | 42dot Asta Sans (https://github.com/42dot/Asta-Sans, Google Fonts) — 레포 res/font/asta_sans_*.ttf | SIL Open Font License 1.1 — 글꼴 파일 내장 라이선스 문구와 Google Fonts METADATA(license: OFL, designer: 42dot)로 확인. 현대차그룹 42dot 제작 |
| gc-icons | icon | project-owned | not-required | goodnight-camp/automotive/src/main/res/drawable/gc_ic_*.xml |  |

### Rules

- 글꼴은 레포의 Asta Sans(42dot, OFL 1.1)만 쓴다. 현대 전용 글꼴(Hyundai Sans)은 라이선스가 없어 쓰지 않는다

- 굵기는 700(제목·숫자)과 500(본문·라벨) 두 단계만 쓴다. 800은 쓰지 않는다 — 밤 화면에서 덜 공격적으로

- 수면 시계만 300(Light)

<!-- design-md:section components-states -->
## 4. 컴포넌트와 상태

### Component: button-primary

**Semantics:** 화면당 하나뿐인 주 동작 (밤 계획 만들기, 이대로 잘게요, 일어날게요, 집으로 안내)

- Anatomy: 면 (accent), 라벨, 선택적 앞 아이콘
- Variants: night: 시안 면 + 짙은 네이비 글자, morning: 현대 네이비 면 + 흰 글자
- States: default, pressed, disabled
- Token references: color.night.accent, color.night.accent-pressed, color.night.on-accent, color.morning.accent, color.morning.accent-pressed, radius.button, size.touch-min

- Interaction kind: interactive

#### State applicability

| State | Applicability | Reason |
|---|---|---|
| default | applicable |  |
| hover | not-applicable | 차량 터치 화면에는 포인터 호버가 없음 |
| focus-visible | not-applicable | 앱 매니페스트에서 로터리(CCP) 미지원을 선언함 |
| disabled | applicable |  |
| loading | applicable |  |
| error | not-applicable | 버튼 자체는 오류 상태를 갖지 않고 결과는 토스트·카드로 알림 |
| success | not-applicable | 성공 결과는 화면 전환으로 표현 |

### Component: button-basic

**Semantics:** 보조 동작 (수정, 5분만 더, 변경, 차박 종료)

- Anatomy: 반투명 면, 라벨
- States: default, pressed, disabled
- Token references: radius.button, size.touch-min

- Interaction kind: interactive

#### State applicability

| State | Applicability | Reason |
|---|---|---|
| default | applicable |  |
| hover | not-applicable | 차량 터치 화면에는 포인터 호버가 없음 |
| focus-visible | not-applicable | 로터리(CCP) 미지원 |
| disabled | applicable |  |
| loading | not-applicable | 보조 동작은 즉시 반응 |
| error | not-applicable | 버튼 자체 오류 상태 없음 |
| success | not-applicable | 결과는 화면 전환으로 표현 |

### Component: card

**Semantics:** 정보 묶음 컨테이너

- Anatomy: 면 (surface), 1dp 테두리, 제목, 내용
- States: default
- Token references: color.night.surface, color.night.border, radius.card, border.card, elevation.card

- Interaction kind: non-interactive
- Interaction reason: 카드 자체는 누를 수 없고 안의 버튼만 동작

### Component: stat

**Semantics:** 배터리·온도·남은 시간 지표

- Anatomy: 큰 숫자, 단위, 라벨
- States: default
- Token references: color.night.text-primary, color.night.text-tertiary

- Interaction kind: non-interactive
- Interaction reason: 읽기 전용 지표 (디버그 빌드의 시연용 길게 누르기는 제품 기능이 아님)

### Rules

- 주 동작 버튼은 화면당 하나, 나머지는 기본 버튼

- 눌림 상태는 면 명도만 바꾼다 (크기·그림자 변화 없음)

<!-- design-md:section layout-platforms -->
## 5. 레이아웃과 플랫폼

### Responsive constraints

- Minimum supported width: 1920px

### Layout rules

- 가로 고정 레이아웃. 세로 회전 시 기존 경고 오버레이를 유지한다

- 치수는 values(1920 기준) · values-w2000dp · values-w2500dp 세 단계로 비례 확대한다

- 왼쪽은 핵심 지표·헤드라인, 오른쪽은 조작·목록의 2열 구성을 유지한다

### Platform: android

- Android Automotive (Pleos Connect), minSdk 28, targetSdk 34
- AppCompat DayNight 테마로 밤/아침 팔레트 전환 — 앱 기본 MODE_NIGHT_YES, WakeActivity만 MODE_NIGHT_NO

<!-- design-md:section content-locales -->
## 6. 콘텐츠와 로케일

### Voice

- 기존 앱 문구처럼 짧은 해요체 (예: 20°C로 아침까지 따뜻하게 잘 수 있어요)

- 차가 한 일은 결과 중심으로 (성에 제거 마쳤어요)

### Locale: ko (supported)

- 기본 언어

### Locale: en (supported)

- values-en 문자열, 키와 포맷 인자는 한국어와 동일

<!-- design-md:section governance -->
## 7. 거버넌스

<!-- design-md:claim authority kind=project-system lang=ko -->
### Authority

이 문서는 명시된 범위의 프로젝트 디자인 계약이다.
<!-- design-md:claim-end -->

<!-- design-md:claim application-priority order=prompt-fact,repository-fact,system-contract,reference-inspiration lang=ko -->
### Application priority

1. 요청 범위의 명시적 사용자 지침.
2. 저장소 사실.
3. 이 시스템 계약.
4. 레퍼런스 영감.
<!-- design-md:claim-end -->

<!-- design-md:claim unknowns policy=absent-at-smallest-unresolved-boundary lang=ko -->
### Unknowns

가장 작은 미확정 값이나 그룹만 생략한다. 그럴듯한 기본값으로 대체하지 않는다.
<!-- design-md:claim-end -->

<!-- design-md:claim changes policy=review-record-validate-before-adoption lang=ko -->
### Changes

채택 전에 변경을 기록하고 검토하고 검증한다.
<!-- design-md:claim-end -->

### Project priority details

1. 밤 화면 눈부심 최소화

2. 차량 거리 가독성

3. 레퍼런스 톤 일치

### Additional change rules

- 토큰 값 변경은 이 문서를 먼저 고친 뒤 colors.xml / dimens.xml에 반영한다

- 디자인 설정 파일은 Goodnight-Camp/.github 레포에만 두고 앱 레포에는 결과 리소스만 커밋한다

### Decision provenance

- /experience/design_direction — prompt-fact; evidence: design/evidence/2026-11-11-design-init.md
- /foundations/tokens — agent-proposed-greenfield-decision; evidence: design/evidence/2026-11-11-design-init.md
- /typography_assets/roles — repository-fact; evidence: design/evidence/2026-11-11-design-init.md
- /typography_assets/rules — agent-proposed-greenfield-decision; evidence: design/evidence/2026-11-11-design-init.md
- /layout_platforms/rules — repository-fact; evidence: design/evidence/2026-11-11-design-init.md
- /content_locales/voice — repository-fact; evidence: design/evidence/2026-11-11-design-init.md
- /components_states/components — agent-proposed-greenfield-decision; evidence: design/evidence/2026-11-11-design-init.md
