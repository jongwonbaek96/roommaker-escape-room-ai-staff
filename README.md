# 룸메이커 온라인 방탈출 제작 직원

Cowork에서 사용하는 "온라인 방탈출 제작 AI 직원들" 설정 파일 모음입니다.
다른 컴퓨터에서도 같은 세팅으로 이어서 작업할 수 있도록 이 레포에 백업합니다.

## 폴더 구성

- `roommaker_ai/` - 룸메이커 AI 총괄 디렉터 + 4개 에이전트(스토리/퀴즈/이미지/미니게임) 정의
-   - `CLAUDE.md`, `SOUL.md`(정체성), `USER.md`(피그말리온 유저 모델), `MEMORY.md`(누적 지식 인덱스)
    -   - `story/`, `quiz/`, `image/`, `minigame/` - 각 에이전트의 `agent.md`, `feedback.json`, 산출물
        -   - `skills/` - 트리거 패턴 기반 스킬 라이브러리(`.skill` 파일들)
            -   - `assets/` - 로고 등 공용 자산
                - - `헤르메스/` - 헤르메스 에이전트 정의 (`CLAUDE.md`, `SOUL.md`, `USER.md`, `MEMORY.md`)
                  - - `global-memory/` - Cowork 전역 자동 메모리(`MEMORY.md` 인덱스 + 프로젝트별 메모리 파일)
                   
                    - ## 새 컴퓨터에서 이어서 작업하는 법
                   
                    - 1. 새 컴퓨터의 Cowork 작업 폴더(예: `온라인 방탈출 제작 직원들`)에 이 레포를 clone 하거나 파일을 그대로 복사합니다.
                      2. 2. Cowork에서 해당 폴더를 선택(mount)하고 대화를 시작하면, `CLAUDE.md` / `SOUL.md` / `MEMORY.md` / `USER.md` / `skills/`를 그대로 이어서 참조할 수 있습니다.
                         3. 3. `global-memory/` 안의 파일은 Cowork 자동 메모리 시스템이 읽는 형식과 동일하므로, 필요 시 새 세션의 메모리 폴더에 내용을 참고해 반영하면 됩니다.
                            4. 
