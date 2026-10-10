# english-study

33년째 제자리인 영어를 **진단 → 처방 → 훈련 → 재측정** 순서로 고치는 프로젝트.

막연히 "영어를 못한다"가 아니라 어디가 막혔는지 숫자로 찾고, 그 약점만 겨냥해서 4주 단위로 훈련한 다음, 같은 진단으로 변화를 확인합니다.

## 현재 상태

- **2026-10-10 진단 완료** → [`docs/diagnosis.md`](docs/diagnosis.md)
  인식 어휘는 약 7,000으로 충분. 막힌 곳은 실시간 처리: 받아쓰기 48% (긴 문장 22%), 즉석 영작 문장당 27.6초, 읽기 79 wpm.
- **4주 처방 진행 중 (2026-10-12 ~ 11-08)** → [`docs/plan.md`](docs/plan.md)
- **재진단 예정: 2026-11-08 무렵**

## 도구

| 도구 | 링크 | 소스 |
|---|---|---|
| 진단 (30분) | https://claude.ai/artifact/BymfpinRcVDjLDZSNqK7Sc | `diagnostic/english-diagnostic.html` |
| 매일 30분 훈련 | https://claude.ai/artifact/2op2WDt63YrGqHi8MFbHWB | `training/daily-training.html` |

두 페이지 모두 기록을 Artifact 저장소에 남기고, Claude가 그 기록을 읽어서 채점하고 계획을 조정합니다. 링크는 소유자만 열 수 있습니다.

훈련 앱 구성:
- **귀**: 오늘의 문장 받아쓰기 → 원문 대조 → 따라 말하기 3회
- **입**: 한국어 보고 5초 안에 소리 내어 영어로. 간격 반복 (1 → 2 → 4 → 7 → 14 → 30일)
- **흐름**: BBC 6 Minute English를 대본 보며 멈추지 않고 듣기
- **주간 작문**: Claude 교정 → 틀린 문장을 순간영작 카드로 추가

## 문서

- [`docs/why-stuck.md`](docs/why-stuck.md): 오래 해도 늘지 않는 일곱 가지 원인과 진단 방법
- [`docs/diagnosis.md`](docs/diagnosis.md): 2026-10-10 진단 결과와 재채점
- [`docs/plan.md`](docs/plan.md): 4주 처방

## 참고

- `.html` 파일은 claude.ai Artifact로 게시되는 페이지 소스입니다 (게시할 때 `<html>`/`<head>` 골격이 자동으로 붙습니다).
- 음성은 브라우저 음성 합성(Web Speech API)을 씁니다. 일부 안드로이드 앱 내부 화면에서는 소리가 나지 않을 수 있습니다.
- 진단의 어휘 문항은 빈도 순위 구간(1–1천 … 1.2–2만)별 8개 단어와 가짜 단어 16개로 구성됩니다. 가짜 단어를 안다고 고른 비율만큼 점수를 보정합니다.
