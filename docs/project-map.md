# 자료 지도

## 서비스
- 이름: 어디까지 했어?
- 컨셉: 조별과제에서 결과물을 단계별로 올리면 그게 곧 진행 기록이 되어, 서로 어디까지 했는지 한 화면에 보이는 가입 없는 웹 링크

## 파일 위치
| 자료 | 파일 |
|---|---|
| 서비스 기획서 | `docs/기획서_v2.md` (원본 v1: `docs/superpowers/specs/2026-11-13-progress-visibility-design.md`) |
| 퍼소나 | `docs/personas.md` (정리본 PDF: `docs/persona-report-v6.pdf`) |
| 인터뷰, 조사 | `docs/interviews/` (P1–P3 답변, P4–P7 인터뷰, P8–P10 전사 PDF, P8–P11 전사 md), `data/transcripts.md`, `data/cards.csv`(카드 238장), `data/variables.csv`, `data/variable_evidence.csv`, `data/participants.csv`, `data/README.md` |
| 메뉴 구조 | `docs/기획서_v2.md` 7-1 메뉴 구조, 7-3 화면 목록, 12-2 추가 화면 |
| 와이어프레임 | `docs/hifi/` 화면 캡처 18장, 클릭 프로토타입 `design/prototype.html`, 와이어프레임 캔버스(아티팩트) https://claude.ai/artifact/Kfd6hboNdQe5GPjPf5TeEm |
| 기타 | 디자인 참고 `docs/DESIGN.md`, `docs/DESIGN_1.md` (현재 적용본은 DESIGN_1) |

## 핵심 기능 (기획서 그대로)
1. 올리는 순간 진행이 바뀐다 — 체크박스가 없다 (단계마다 파일·링크·한 줄 메모를 올리면 '올림'으로 바뀜)
2. 늦을 땐 사람 대신 화면이 말해 준다 — 사유 고르기 + 승인 없는 연장
3. 올린 것에 "확인했어요" 한 번 — 읽음 숫자 대신 반응
4. 공통 기반: 가입·설치 없는 링크 (이름만 적고 들어온다)
5. (v2 추가) "오늘 현황 단톡에 공유" — 누구나 누를 수 있음, 문구 자동 생성

## 주요 사용 시나리오 (기획서 그대로, 7-4)
1. A. 팀장 김민수가 팀을 만들고 링크를 퍼뜨린다: 01 → 02 → 03 → 05 → 11 → 01
2. B. 팀원 이수아가 들어와 남의 진행을 보고 초안을 올린다: 04 → 06 → 07 → 06 → 08 → 06
3. C. 팀원 한도윤이 기한 하루 전 알림을 받고 연장한다: 10(나에게만) → 09 → 06 → 10(팀 알림)
4. D. 팀장이 기한 지남 알림을 확인하고 단톡에 공유한다: 01 → 06 → 10 → 공유 완료 → 06 → 07
5. E. 오류에서 빠져나온다: 12-A → 01 / 08 → 12-B → 08

## 화면 목록
기획서에 이미 화면 번호(01~13)가 있어 그대로 씀.

| ID | 화면 이름 | 와이어프레임 파일 | 비고 |
|---|---|---|---|
| 01 | 홈 · 내 팀 목록 | `docs/hifi/Home.png` | 1뎁스 |
| 02 | 팀 만들기 | `docs/hifi/Create.png` | |
| 03 | 링크 공유 | `docs/hifi/Share.png` | |
| 04 | 링크로 들어오기 | `docs/hifi/Join.png` | 팀원 진입 화면 |
| 05 | 단계·파트 정하기 | `docs/hifi/Stages.png` | 06에서 "단계·파트 수정"으로 재사용 |
| 06 | 팀 진행 | `docs/hifi/Main.png` | 팀 안의 중심 화면 |
| 06-b | 올린 직후 | `docs/hifi/MainDone.png` | 06의 상태 |
| 07 | 팀원 파트 · 결과물 보기 | `docs/hifi/Detail.png` | |
| 07-b | 내 파트 | `docs/hifi/DetailMine.png` | |
| 07-c | 기한 지남 팀원 | `docs/hifi/DetailLate.png` | |
| 08 | 결과물 올리기 | `docs/hifi/Upload.png` | |
| 09 | 연장 요청 | `docs/hifi/Extend.png` | |
| 09-b | 도움 요청 | `docs/hifi/Help.png` | |
| 10 | 알림 · 팀 알림 | `docs/hifi/Alerts.png` | |
| 10-b | 알림 · 나에게만 | `docs/hifi/AlertsMine.png` | |
| 11 | 빈 상태 | `docs/hifi/Empty.png` | |
| 12-A | 오류 · 잘못된 링크 | `docs/hifi/ErrorLink.png` | |
| 12-B | 오류 · 업로드 실패 | `docs/hifi/ErrorUpload.png` | |
| 13 | 단톡방에 보이는 모습 | (캡처 없음) | 캔버스·프로토타입에만 있음 |

## 비어 있는 것
- 13 "단톡방에 보이는 모습"은 `docs/hifi/` 캡처가 없음 (와이어프레임 캔버스 아티팩트에는 있다고 기획서에 적혀 있음)
- 시나리오 D의 "공유 완료 안내"는 화면 번호가 없음 (토스트인지 화면인지 `/flow`에서 정하기)
- 06-b, 07-b, 07-c, 09-b, 10-b, 13은 7-1 메뉴 구조 그림에는 아직 안 들어가 있음 (12-2에만 있음)
