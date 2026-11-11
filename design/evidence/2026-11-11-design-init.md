# 2026-11-11 디자인 시스템 초기화 근거

DESIGN.md(Core v2)의 결정 근거. OmD `omd:init` 절차로 만들었다.

## 1. 사용자 결정 (prompt-fact)

| 질문 | 선택 |
|---|---|
| 바탕 레퍼런스 (OmD 추천 top5: hyundai · kia · greencar · tesla · tmap, 모두 verified_v2) | **hyundai** |
| 테마 방향 | **다크 + 기상 화면만 밝게** — 밤 화면(설정·계획·캠핑·수면)은 다크, 아침 기상 화면만 라이트 |
| DESIGN.md 미리보기 | **승인, 레이아웃까지 진행** (YBSeok) |

## 2. 레퍼런스에서 가져온 것 (verified-reference-inspiration)

`.claude/data/references/hyundai/DESIGN.md` (verified_v2, 2026-07-13 검증) — 웹사이트 캡처라 차량 UI 값이 아니므로 **분위기 근거로만** 사용.
- 네이비 `#002c5f`(주 동작), 청록 `#007fa8`, 시안 `#00aad2`
- 그림자 없는 평면 구성, 각진 모서리(0~6px), 400·500 위주의 가벼운 굵기
- Hyundai Sans는 공개 라이선스가 없어 **쓰지 않음**

## 3. 앱 레포 사실 (repository-fact)

[`Goodnight-Camp/goodnight-camp`](https://github.com/Goodnight-Camp/goodnight-camp) 기준.
- 색 토큰: `automotive/src/main/res/values/colors.xml`, `values-night/colors.xml` (원래 Pleos Connect Figma 토큰과 1:1)
- 치수: `values`(1920 기준) · `values-w2000dp` · `values-w2500dp`, 에뮬레이터 실측 2560×1440 · 밀도 160 → `values-w2500dp` 적용
- 타입 스케일·스타일: `values/styles.xml`, 글꼴 `res/font/asta_sans_*.ttf`
- 문구: `values/strings.xml` 해요체, `values-en/strings.xml`
- 테마: `Theme.Material3.DayNight` 기반 → 밤/아침 팔레트를 `AppCompatDelegate` 야간 모드로 전환

## 4. 글꼴 라이선스 (verified)

Asta Sans — **SIL Open Font License 1.1**, 제작 **42dot**(현대차그룹).
- 글꼴 파일 `asta_sans_regular.ttf` 내장 이름 테이블: "This Font Software is licensed under the SIL Open Font License, Version 1.1."
- Google Fonts `ofl/astasans/METADATA.pb`: `license: "OFL"`, `designer: "42dot"`, 출처 https://github.com/42dot/Asta-Sans

## 5. 명암비 계산 (WCAG 2.x 상대 휘도)

| 전경 | 배경 | 비율 |
|---|---|---|
| 밤 text-primary `#F2F5F9` | surface `#121D30` | 15.44 |
| 밤 text-tertiary 64% | surface | 6.98 |
| 밤 on-accent `#06121F` | accent `#00AAD2` | 6.89 |
| 밤 accent-soft `#5CC8E8` | surface | 8.75 |
| 밤 positive `#2BD98A` / negative `#FF6A4D` / warm `#FFA233` | surface | 9.16 / 5.96 / 8.41 |
| 아침 text-primary `#0A1B30` | surface `#FFFFFF` | 17.32 |
| 아침 text-tertiary 64% | surface | 5.24 |
| 아침 accent-soft `#006B8F` | surface | 6.00 |
| 아침 positive `#007A48` / negative `#C42E12` / warm `#A85A00` | surface | 5.42 / 5.60 / 5.09 |
| 흰 글자 | 아침 accent `#002C5F` | 13.77 |
| 수면 text 40% | sleep `#05080F` | 3.74 (큰 글자 전용) |

## 6. 에뮬레이터 확인

Pleos Connect 에뮬레이터에서 설정·밤 계획·캠핑·수면 오버레이·기상 화면에 팔레트를 적용해 스크린샷으로 확인 (앱 브랜치 `feature/design-refresh`).
