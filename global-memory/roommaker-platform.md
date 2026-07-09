---
name: roommaker-platform
description: 방탈출 게임 관리 플랫폼(PWA) 구조와 배포 워크플로
metadata: 
  node_type: memory
  type: project
  originSessionId: 94918157-42ad-4be6-a612-7b125fd2ff46
---

방탈출 게임들을 모아 관리하는 웹앱(PWA) 플랫폼. 폴더: `스토리 제작 AI/룸메이커_플랫폼`.

구조: `index.html`(관리 대시보드 PWA), `registry.json`(게임 등재 명단), `games/`(게임 HTML들 - 단일파일 자체완결형), PWA 파일(manifest.webmanifest, sw.js, icons/), `vercel.json`, `setup-deploy.ps1`(최초 배포), `publish.ps1`(업데이트 배포).

배포: GitHub repo `jongwonbaek96/roommaker-platform` → Vercel 자동배포(기존, 라이브 URL: https://roommaker-platform.vercel.app) + Cloudflare Pages 자동배포(2026-07-07 추가, 라이브 URL: https://roommaker-platform.pages.dev). 같은 리포에 push하면 두 곳 모두 자동 배포됨. Cloudflare Pages 설정: 빌드 명령 없음, 출력 디렉토리 루트(정적 사이트라 빌드 불필요). 사용자가 Vercel에서 Cloudflare로 완전 이전을 원했으나 Vercel 정리는 보류(현재 둘 다 유지 중) — 나중에 Vercel 프로젝트 삭제 요청 시 Vercel MCP로 처리 가능.

새 게임 등재 워크플로: ① 게임 HTML을 `games/`에 영문슬러그명으로 저장 ② `registry.json`의 games 배열에 항목 추가(id, title, file, status, accent, emoji 등) ③ 사용자가 PC에서 `./publish.ps1 "메시지"` 실행 → push → Vercel 자동배포.

**Why:** OneDrive 마운트라 Claude 샌드박스에서는 git 조작 불가(권한 제한). git push/배포는 사용자 PC에서만 가능.
**How to apply:** 파일은 Claude가 폴더에 직접 작성/수정하되, 실제 배포(git push)는 사용자에게 `./publish.ps1` 실행을 요청. ps1 스크립트는 한글 인코딩 깨짐 방지 위해 메시지를 영문 ASCII로 작성.

현재 게임 5종: 빛이 먼저 왔다(SF, 퍼즐14), 마법학교 졸업은 글렀어요(판타지), 너의 편지를 아직 읽지 못했어(감성), 새벽 4시 44분(감성 심리극, 퍼즐20), 자정의 주파수(공포, 퍼즐13, 2026-07-07 등재 — midnight-frequency.html). 다음 단계 후보: 모든 기기 공유 편집(백엔드/GitHub 자동커밋).

2026-07-07 확인: 샌드박스에서 git status/add는 되지만 .git/index.lock 삭제가 'Operation not permitted' — commit/push 여전히 불가. 배포는 반드시 사용자 PC에서 ./publish.ps1. 또한 OneDrive 마운트는 Windows쪽 Edit 후 샌드박스 캐시가 갱신되지 않는 경우 있음(파일 크기/mtime 고착) — 이럴 땐 샌드박스에 남은 온전한 사본에 스크립트로 동일 수정을 적용해 재생성하는 우회가 유효.
