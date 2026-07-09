# MEMORY.md — 룸메이커 AI 누적 지식 인덱스

> Hermes Agent의 "persistent fact memory" 원칙 적용.
> 세션이 끊겨도 이 파일이 지식을 유지한다.
> 각 항목은 파일 링크 + 한 줄 요약. 50개 초과 시 정리.

---

## 완성된 작품

- [ROOM:ZERO (스릴러 ⭐⭐⭐⭐)](story/output/story_20260523_thriller.md) — 신뢰-배신 반전 구조. 파트너가 조직원인 24시간 방탈출. 3분기 엔딩(공범/무력화/신호). v2 수정 완료.

---

## 장르별 학습 결과

- [스릴러 테마 가이드](story/themes/thriller.md) — 현재 비어있음. 첫 작품 완료 후 채워야 함.

---

## 스킬 라이브러리

- [스킬 전체 인덱스](skills/index.md) — 모든 재사용 스킬 목록 + 트리거 패턴

### 스토리 스킬
- [thriller-trust-betrayal](skills/story/thriller_trust_betrayal.skill) — 신뢰 구축 → 배신 반전. ROOM:ZERO에서 검증.
- [ambient-foreshadowing](skills/story/ambient_foreshadowing.skill) — 공간/감각 묘사로 복선 심기.

### 퀴즈 스킬
- [acrostic-warning](skills/quiz/acrostic_warning.skill) — 문장 첫 글자 조합으로 경고 메시지. 감정 충격용.
- [meta-deduction](skills/quiz/meta_deduction.skill) — 스토리 전체를 역산해 조작된 단서를 찾는 메타 추리.

### 미니게임 스킬
- [cooperation-trap](skills/minigame/cooperation_trap.skill) — 협동 장치로 신뢰 형성 → 나중에 배신 복선.
- [darkness-navigation](skills/minigame/darkness_navigation.skill) — 어둠 속 공간 탐색. 공포감 극대화.

---

## 피드백 핵심 사실

- ROOM:ZERO 초안 → v2 수정 요청: "공포도 더 높게, 결말 더 박진감 있게"
  - 적용: 공간 냄새/온도 묘사 강화, 폴라로이드 실종자 사진 추가, 어둠 속 격투 추가

---

## 시스템 메모

- 에이전트 구조: story → quiz → image → minigame 순서 파이프라인
- 2026-06-18: Hermes Agent 폐쇄형 루프 구조 적용 완료
- Phase 1 운영 중 (이미지 API 없음, 프롬프트 문서 방식)

---

## 업데이트 규칙

작업 완료 시마다:
1. "완성된 작품"에 링크 + 한 줄 요약 추가
2. 새 스킬 생성 시 "스킬 라이브러리"에 링크 추가
3. 피드백 핵심 내용은 "피드백 핵심 사실"에 기록
4. 50줄 초과 시 오래된 항목 압축
