# 스킬 인덱스 (Skills Index)

> Hermes Agent의 skill retrieval 원칙 적용.
> 작업 시작 시 트리거 패턴을 보고 관련 스킬을 로드한다.
> 스킬이 많아질수록 에이전트가 더 빠르고 정확해진다.

---

## 사용 방법

1. 작업 요청 들어오면 → 트리거 패턴 매칭
2. 관련 스킬 파일 로드 → 성공 패턴 활용
3. 작업 완료 후 → 새 패턴 추출 → 스킬 업데이트 또는 신규 생성

---

## 스토리 스킬 (story/)

| 스킬명 | 트리거 패턴 | 성공률 | 사용 횟수 | 파일 |
|---|---|---|---|---|
| thriller-trust-betrayal | 스릴러, 반전, 배신, 파트너, 신뢰 | 90% | 1 | [링크](story/thriller_trust_betrayal.skill) |
| ambient-foreshadowing | 복선, 공간 묘사, 감각, 분위기 | 90% | 1 | [링크](story/ambient_foreshadowing.skill) |

---

## 퀴즈 스킬 (quiz/)

| 스킬명 | 트리거 패턴 | 성공률 | 사용 횟수 | 파일 |
|---|---|---|---|---|
| acrostic-warning | 아크로스틱, 첫 글자, 경고, 감정 충격 | 85% | 1 | [링크](quiz/acrostic_warning.skill) |
| meta-deduction | 역산, 메타 추리, 조작된 단서, 전체 역산 | 85% | 1 | [링크](quiz/meta_deduction.skill) |

---

## 이미지 스킬 (image/)

| 스킬명 | 트리거 패턴 | 성공률 | 사용 횟수 | 파일 |
|---|---|---|---|---|
| *(첫 이미지 작업 완료 후 추가)* | | | | |

---

## 미니게임 스킬 (minigame/)

| 스킬명 | 트리거 패턴 | 성공률 | 사용 횟수 | 파일 |
|---|---|---|---|---|
| cooperation-trap | 협동, 발판, 신뢰 형성, 둘이서 | 90% | 1 | [링크](minigame/cooperation_trap.skill) |
| darkness-navigation | 어둠, 손전등, 공포, 선 피하기 | 85% | 1 | [링크](minigame/darkness_navigation.skill) |

---

## 성공률 업데이트 기준

```
작업 완료 후:
- 피그말리온이 "좋아" / "이런 거 더" → 해당 스킬 성공률 +5%
- 피그말리온이 "수정해줘" → 해당 스킬 성공률 -5% + 실패 원인 기록
- 사용 횟수 1회 추가
- 3회 이상 연속 실패 → 스킬 재작성 또는 폐기
```
