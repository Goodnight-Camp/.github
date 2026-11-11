# 굿나잇 캠프 디자인 기준

| 파일 | 내용 |
|---|---|
| `core/DESIGN.md` | 디자인 시스템 (OmD Core v2) — 밤 다크 + 기상 화면만 라이트, 현대 네이비·시안 톤 |
| `core/.omd/system/` | 컴파일러가 만든 그래프·출처·적용 범위·매니페스트 (해시로 DESIGN.md와 묶임) |
| `core/owner-approval.json` | 프로젝트 오너(YBSeok) 미리보기 승인 기록 |
| `evidence/2026-11-11-design-init.md` | 결정 근거 — 사용자 선택, 레퍼런스, 명암비 계산, 글꼴 라이선스 |

## 상태: 검토·승인·컴파일 통과, 루트 채택은 보류

`omd design-md compile`의 선언 적합성 검사까지 통과한 패키지를 손대지 않고 보관한다.
루트(`/DESIGN.md`) 채택(`omd design-md adopt`)은 OmD 2.0.6 프로젝트 검증기의 아래 조건 때문에 보류:

- **320px·200% 반응형 계약 필수** — 웹 기준 규칙. 굿나잇 캠프는 차량 디스플레이 2560×1440 가로 고정이라 사실대로 적으면 통과할 수 없다 (거짓 값으로 우회하지 않음).
- 한국어 문서의 섹션 제목을 컴파일러는 한국어로 쓰고 검증기는 영어만 받는 도구 간 불일치.

앱 반영: [`goodnight-camp`](https://github.com/Goodnight-Camp/goodnight-camp)의 `values/colors.xml`(아침) · `values-night/colors.xml`(밤) · `dimens.xml` · `styles.xml`.
값을 바꿀 땐 이 문서를 먼저 고치고 앱 리소스에 옮긴다.
