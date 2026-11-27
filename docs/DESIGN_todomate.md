# todo mate (투두메이트) — Style Reference
> 흰 종이 위에 색 스티커를 붙이는 소셜 투두 — 흑백 크롬 뼈대에, 사용자가 고른 카테고리 색이 클로버 체크와 캘린더를 채운다.

**Theme:** light (시스템 설정에 따라 완전한 블랙 dark 모드)

출처: todomate.net 웹앱(게스트 모드) 실사용 화면을 800px 뷰포트(1:1 CSS px)에서 무손실 캡처해 픽셀 측정. 폰트는 웹앱이 실제 로드하는 파일, 카테고리 팔레트는 앱 내 색상 선택 시트에서 직접 샘플링. 투두메이트 웹은 Flutter 캔버스 렌더링이라 CSS 토큰이 없으므로 **색은 렌더링 픽셀 실측(±3 오차)**, 크기는 **픽셀 측정값**입니다(기본 카테고리 색 `#1E2F98`만 앱 내 HEX 표시로 확인). 보조 자료: Google Play 공식 스크린샷. HTML 예시는 재구성이며 원본 컴포넌트가 아닙니다.

투두메이트의 크롬은 사실상 흑백입니다: 순백 `#ffffff` 배경, 거의 검정 텍스트, 연회색 `#f2f2f2` 필(pill)과 리스트 행. 색은 **사용자의 카테고리 색**에서만 나옵니다 — 92개 프리셋 + 자유 HEX 중 고른 색이 칩 라벨, 클로버 체크, 캘린더를 채우며 "한 일이 색으로 쌓이는" 경험을 만듭니다. 시그니처 형태는 **네잎 클로버(4개 원이 합쳐진 블롭)** 로 로고·체크박스·달력 날짜 표시·마스코트에 반복됩니다. 선택 상태는 검정 필 + 흰 글자로 반전하고, 그림자는 거의 쓰지 않으며, 모든 칩·버튼은 완전한 필 모양입니다.

## Tokens — Colors

### 크롬 (Neutral, light) — 실측

| Name | Value | Token | Role |
|------|-------|-------|------|
| Paper | `#ffffff` | `--color-paper` | 앱 배경, 바텀시트, 플로팅 메뉴 카드 |
| Pill Gray | `#f2f2f2` | `--color-pill` | 카테고리 칩, 친구 아이콘 필, 설정 리스트 행, 점선 구분선, 메뉴 항목 |
| Button Gray | `#f5f5f5` | `--color-button` | 보조 버튼(수정하기/삭제하기/종료하기), 확인 버튼 |
| Avatar Gray | `#eeeeee` | `--color-avatar` | 기본 아바타 원 |
| Empty Clover | `#d4d8db` | `--color-empty` | 미완료 체크박스, 기록 없는 날짜 클로버 |
| Handle | `#cdcdcd` | `--color-handle` | 바텀시트 그랩 핸들 |
| Lock Gray | `#9f9ea3` | `--color-lock` | 공개범위 자물쇠 아이콘 |
| Ink | `#000000` | `--color-ink` | 선택 필, 오늘 날짜 원, 아이콘 |
| Text | `#1a1a1a` | `--color-text` | 제목·이름·할 일 텍스트(렌더 코어 `#161616`~`#1f1f1f`) |
| Text Secondary | `#6e6e6e` | `--color-text-secondary` | 요일 라벨, 안내 문구, "편집" |
| Scrim | `rgba(0,0,0,.54)` | `--color-scrim` | 바텀시트·메뉴 뒤 딤 (흰색이 `#757575`로 보임) |
| Sunday Red | `#f04452` | `--color-sunday` | 일요일 라벨·날짜, 삭제 텍스트 (근사) |
| Saturday Blue | `#3b7cf6` | `--color-saturday` | 토요일 라벨·날짜 (근사) |
| Tooltip Yellow | `#fbf3c4` | `--color-tooltip` | 온보딩 말풍선 배경 (텍스트 `#7f6e40`) |

### 크롬 (dark) — 실측

| Name | Light | Dark |
|------|-------|------|
| 배경 | `#ffffff` | `#000000` |
| 칩·필 | `#f2f2f2` | `#1c1c1c` |
| 아바타 | `#eeeeee` | `#232323` |
| 빈 클로버 | `#d4d8db` | `#333333` |
| 구분선 | `#f2f2f2` | `#0f0f0f` |
| 선택 필 | 검정 + 흰 글자 | **흰색 + 검정 글자 (반전)** |
| 칩 안 + 버튼 | 흰 원 | 검정 원 |
| 텍스트 | `#1a1a1a` | `#ffffff` |

### 카테고리 색 (사용자 선택 — 유일한 액센트)

게스트 계정 기본 3개 카테고리:

| Name | Value | Role |
|------|-------|------|
| Default Navy | `#1e2f98` | 카테고리 1 (앱 HEX 표시로 확인) |
| Default Forest | `#205543` | 카테고리 2 (근사, 팔레트 일치) |
| Default Slate Teal | `#426f75` | 카테고리 3 (근사, 팔레트 일치) |

색상 선택 시트는 3페이지: **① 따뜻한/뉴트럴 48색 ② 초록·파랑·보라 44색 ③ 자유 HSV 피커 + HEX 입력.**

**Page 1 (6×8)**
```
#181818 #af9fb9 #a9a19f #80939a #856f95 #716e83
#ffb2cc #f792b4 #f975c9 #e27298 #cb7f99 #e56892
#da4da9 #c93361 #bb434d #7d4e48 #60332e #61253e
#f5977d #d67473 #f55b63 #ac6465 #43192d #13070b
#fa9782 #b1946c #ab8b80 #957358 #734724 #393939
#d0ae88 #c6ac93 #f49426 #ce9a4e #d3983e #e57140
#ffcd64 #c7d478 #96c63f #8f995a #7c844b #698e4b
#55e48c #56cd3f #9bbb89 #6ebca2 #4f9a59 #162d19
```

**Page 2 (6×8, 마지막 줄 4개)**
```
#5cbaa8 #44b08e #4ea3a6 #449479 #2e6756 #205543
#79c3c6 #71c6cb #50a1a4 #538e9c #426f75 #2b687d
#78d2ec #59b0f5 #78a3d8 #7ba0d4 #51a4e6 #649ef0
#4092e8 #2b7fe2 #3474f2 #4058f8 #4254b6 #3257a8
#a0aadf #7788da #7680ef #797fed #5d6dc2 #6948f9
#5c37f9 #4a42cb #3241a0 #1e2f98 #1a257f #2a2e5d
#b366e8 #745abb #655077 #4519ec #5023be #6d0ea8
#443061 #460488 #251a3c #150d34
```

> 카테고리 색 사용처: 칩 라벨 텍스트(14px 700), 완료 클로버 채움(+ 흰 체크), 입력 중 밑줄(2px), 설정 화면 색상 점, 월간 캘린더 날짜 클로버.

### 액션 아이콘 색 (할 일 옵션 시트) — 실측

| 기능 | Value |
|------|-------|
| 오늘/내일/다른 날 또 하기 | `#eb7b2f` (오렌지) |
| 루틴 등록하기 | `#4f57d4` (인디고) |
| 시간 알림 · 타이머 | `#c678ce` (오키드) |
| 사진 인증 | `#5ab275` (그린) |
| 하위 할 일 | `#55a992` (틸) |
| 메모 | `#f1df71` (옐로) |
| 정보 보기 | `#363636` (차콜) |
| 수정하기 아이콘 | `#788ce2` |
| 삭제하기 아이콘 | `#ec716c` |

### 브랜드 (마케팅·감정 화면)

| Name | Value | Role |
|------|-------|------|
| Brand Violet | `#6433ff` | 일기 바텀시트, 마스코트 (스토어 스크린샷 기준) |
| Promo Purple | `#8437ff` | 스토어 이미지 예시 카테고리 |
| Promo Blue | `#2c34ff` | 스토어 이미지 예시 카테고리 |
| Promo Pink | `#f858b0` | 스토어 이미지 예시 카테고리 |

## Tokens — Typography

### Pretendard — 단일 UI 서체 (실제 로드 확인) · `--font-ui`
- **로드되는 굵기:** 400 Regular, 500 Medium, 600 SemiBold, 700 Bold, 800 ExtraBold
- **Fallback:** Roboto(Flutter 기본), Noto Color Emoji(이모지)
- **Letter spacing:** 0 (제목 포함 대부분 기본 자간)
- **Role:** 정보 텍스트는 400, 칩·이름·월 표시는 700~800. 크기 차이는 작고 굵기 대비가 큼.

### 꾸미기 폰트 (일기·텍스트 꾸미기용, 앱이 함께 로드)
Goyang, Balsam Tint, 카페24 써라운드 에어, 카페24 쑥쑥, Tdtd, 카페24 시시, 꼬마나비, Little Bear, 교보 손글씨 2019, G마켓 산스 Medium — **UI에는 쓰지 않고 사용자 콘텐츠 꾸밈 전용**.

### 워드마크
"todo mate" 로고는 이미지(둥근 기하학 소문자 extra-bold, Poppins 계열 형태). 대체 시 Poppins 800.

### Type Scale (1:1 px 측정)

| Role | Size | Weight | 예 |
|------|------|--------|----|
| caption | 12px | 400 | 요일 라벨, 안내문 |
| meta | 13px | 400–500 | 날짜 숫자, "편집", 리스트 메뉴 |
| body | 14–15px | 400 | 할 일 텍스트, 설정 행, 액션 시트 항목 |
| chip | 14px | 700 | 카테고리 칩 라벨, 선택 필 "me" |
| title-sm | 16px | 700 | 상단 바 제목("카테고리"), 시트 제목 |
| title | 17–18px | 700–800 | 프로필 이름, 월 표시 "2026년 11월" |
| heading | 22–28px | 800 | 마케팅 헤드라인 |

## Tokens — Spacing & Shapes

**Base unit:** 4px · **Density:** comfortable

### Spacing (측정)
| 용도 | 값 |
|------|----|
| 화면 좌우 여백 | 20–24px |
| 필 사이 간격 | 6–8px |
| 설정 리스트 행 간격 | 4px |
| 체크박스 ↔ 텍스트 | 10px |
| 할 일 행 사이 | 8–12px |
| 카테고리 그룹 사이 | 24–28px |
| 시트 내부 패딩 | 24px |

### Size (측정)
| 요소 | 값 |
|------|----|
| 선택 프로필 필 / 아이콘 필 | 높이 40px |
| 카테고리 칩 | 높이 32px, 내부 + 버튼 24px 흰 원 |
| 체크 클로버(할 일) | 24px |
| 달력 날짜 클로버 | 26px |
| 오늘 날짜 원 | 26px 검정 |
| 프로필 아바타 | 64px |
| 이전/다음 원형 버튼 | 32px |
| 설정 리스트 행 | 높이 48px |
| 보조 버튼 | 높이 52px (리스트 화면 40px) |
| 액션 시트 아이콘 원 | 28px |
| 하단 탭 아이콘 | 24px |

### Border Radius
| Element | Value |
|---------|-------|
| 설정 리스트 행 | 10px |
| 보조 버튼 | 10px |
| 플로팅 메뉴 카드 | 20px |
| 바텀시트 상단 | 24px |
| 칩·필·확인 버튼·메뉴 항목 | 999px |
| 아바타·날짜·아이콘 원 | 50% |
| 체크·날짜 표시 | 클로버 블롭 (커스텀) |

### Layout
- 데스크톱/태블릿 웹: 좌측 프로필+월간 달력(≈360px) / 우측 할 일 리스트 2단, 하단 중앙 탭바
- 바텀시트·색상 선택 시트: 최대 폭 500px 중앙 정렬
- 상단 우측: 검색·햄버거 아이콘 24px

## Components

### Profile Pill Tabs (나 / 친구 전환)
화면 최상단. `[피드 아이콘 원 40px #f2f2f2] [선택 필: 검정, 좌측 32px 아바타 + "me" 흰 14px 700, 높이 40px, radius 999] [친구 아이콘 원 40px #f2f2f2]`. 다크 모드에선 선택 필이 흰색 + 검정 글자로 반전.

### Profile Header
64px 원형 아바타(`#eeeeee`, 기본 이미지는 흰 클로버) + 이름 17px 800. 우측 끝에 응원 추가 아이콘(점선 스마일+, `#c0c0c0`, 24px).

### Calendar Header
`[카테고리 색 클로버 + ▾ 칩(흰 배경, 1px #f2f2f2 아웃라인, 필)] 2026년 11월(18px 800) ......... (‹)(›)`. 이전/다음은 32px 흰 원에 아주 옅은 외곽(`#f4f4f4`).

### Calendar Day Cell
요일 라벨 12px `#6e6e6e`(토 파랑·일 빨강) → 26px 클로버 → 날짜 숫자 13px. 미완료 클로버 `#d4d8db`. 그날 할 일을 모두 완료하면 클로버가 카테고리 색으로 채워지고 흰 체크, 일부만 했으면 남은 개수를 흰 숫자로 표시. **오늘 날짜는 숫자 대신 26px 검정 원 + 흰 숫자 700.**

### Category Chip
높이 32px, 배경 `#f2f2f2`, radius 999px, padding 0 4px 0 12px. `[자물쇠/지구 아이콘 16px #9f9ea3] 6px [라벨 14px 700 카테고리 색] 8px [+ 24px 흰 원, 검정 + 아이콘]`.

### Todo Row
24px 클로버 체크 + 10px + 텍스트 15px 400 `#1a1a1a`. 완료: 카테고리 색 채움 + 흰 체크(텍스트는 그대로, 취소선 없음). 미완료: `#d4d8db` 채움, 보더 없음. 새 할 일 입력 시 텍스트 필드 아래 **2px 카테고리 색 밑줄**, 플레이스홀더 "할 일 입력".

### List Divider & List Menu
카테고리 목록 끝에 1px 점선 `#f2f2f2`(dark `#0f0f0f`), 그 아래 우측 정렬 "☰ 리스트 메뉴" 13px 500.

### Floating Menu (햄버거)
화면 우상단에 뜨는 흰 카드(radius 20px, padding 12px), 뒤 딤 `rgba(0,0,0,.54)`. 항목은 세로로 쌓인 `#f2f2f2` 필 버튼(높이 40px, 간격 8px, 텍스트 15px 500 중앙): 카테고리 관리 / 루틴 관리 / 디데이 관리 / 리마인더 관리.

### Settings List Row (관리 화면)
높이 48px, 배경 `#f2f2f2`, radius 10px, 좌우 padding 16px, 행 간격 4px. 좌측 라벨 14px 500, 우측 값(아이콘+텍스트 `#6e6e6e`) + `›` 셰브론 `#b0b0b0`. 상단 바: 좌 `‹` 24px, 중앙 제목 16px 700, 우 텍스트 액션 "확인" 16px 700.

### Secondary Buttons
나란히 2개, 각 높이 52px, 배경 `#f5f5f5`, radius 10px, 간격 6px, 텍스트 14px 500. 파괴적 동작은 텍스트만 빨강(`#f04452`) — 배경은 같은 회색. 아이콘 버전은 좌측에 16px 컬러 아이콘(수정 `#788ce2`, 삭제 `#ec716c`).

### Action Bottom Sheet (할 일 옵션)
흰 배경, 상단 radius 24px, 최대 폭 500px, 그랩 핸들 40×4px `#cdcdcd`. 제목(할 일 이름) 16px 700 중앙. **2열 그리드**: 각 항목 = 28px 컬러 원 아이콘(흰 글리프) + 12px + 라벨 15px 400, 행 높이 55px. 하단에 보조 버튼 2개(수정하기/삭제하기). 딤 `rgba(0,0,0,.54)`.

### Color Picker Sheet
같은 바텀시트 구조, 제목 "색상 선택". 6열 그리드, 32px 원 스와치, 셀 간격 가로 ~84px·세로 48px. 선택된 색은 2px 흰 간격 + 2px 회색 링. 하단 페이지 점 6px(현재 검정, 나머지 `#c0c0c0`), 그 아래 전체폭 "확인" 필 버튼(높이 48px, `#f2f2f2`). 3페이지는 HSV 사각 피커 + 무지개 슬라이더 + 원형 미리보기 + HEX 입력 필.

### Onboarding Tooltip
`#fbf3c4` 말풍선(radius 16px, padding 14px 16px), 제목 14px 700 + 본문 12px 400 `#7f6e40`, 우상단 × 닫기, 대상 아이콘을 가리키는 손가락 이모지.

### Bottom Tab Bar
5개 아이콘(홈 / 둘러보기 / 알림 / 응원·피드 / 프로필), 24px 채움형, 선택 `#000`, 비선택 `#c8c8c8`, 라벨 없음, 알림 아이콘 우상단 4px 빨간 점.

### Diary Bottom Sheet (스토어 스크린샷 기준)
배경 `#6433ff`, 상단 radius 24px. 제목 "일기" 16px 700 흰색, 중앙 64px 3D 기분 클로버, 본문 흰색 15px line-height 1.7. 사용자 선택 꾸미기 폰트가 여기 적용.

## 우리 서비스 적용 규칙 (접근성 조정, 2026-11-27)

위 값은 투두메이트 원본을 잰 것이에요. "어디까지 했어?" 프로토타입(`design/prototype.html`)에서는 `/design 점검` 결과에 따라 아래만 바꿔 써요. 나머지는 원본 규칙을 그대로 따라요.

### 진한 기능색 (글자와 아이콘 원에만)

원본 기능색은 흰 바탕에서 작은 글자로 쓰면 대비가 4.5에 못 미쳐요. **클로버 채움과 큰 면은 원본 색**을 쓰고, **글자와 흰 기호가 올라가는 원**에만 진한 색을 써요.

| 원본 색 | 원본 대비 | 진한 색 | 흰 바탕 대비 | 쓰는 곳 |
|---|---|---|---|---|
| Sunday Red `#f04452` | 3.7 | `#c8202f` `--red-text` | 5.7 (회색 바탕 5.1) | "지남" 글자, 기한 지남 문구, 입력 오류, 알림 개수 배지, 오류 표시 원, 지남 알림 원 |
| 오렌지 `#eb7b2f` | 2.8 | `#a84e15` `--orange-text` | 5.6 | "연장" 글자, 연장 알림 원 |
| 오키드 `#c678ce` | 3.0 | `#9a4aa3` `--orchid-strong` | 5.4 | 도움 요청 알림 원 |
| 그린 `#5ab275` | 2.6 | `#2f7d4a` `--green-strong` | 5.1 | 확인 알림 원 |
| Tooltip 글자 `#7f6e40` | 4.45 (노란 바탕) | `#665830` | 6.2 (노란 바탕) | 노란 안내 말풍선 글자 |

### 크기

| 항목 | 원본 | 우리 규칙 | 이유 |
|---|---|---|---|
| 누를 수 있는 것 (작은 버튼, 칩, 아이콘 버튼, 탭) | 40px | **44px 이상** | 손가락으로 누르기 쉬운 최소 크기 |
| 가장 작은 글자 | 10~11px (달력 숫자 등) | **12px** | 진행 칸 날짜, 배지, 차트 눈금도 12px |

### 글꼴

Pretendard를 인터넷에서 불러오지 않아요 (`/design` 지침: 한 파일만으로 열려야 함). 기기에 Pretendard가 있으면 쓰고, 없으면 `-apple-system, Apple SD Gothic Neo, Malgun Gothic` 순서로 기본 글꼴을 써요.

## Do's and Don'ts

### Do
- 크롬(배경·텍스트·버튼)은 흑백 + `#f2f2f2`/`#f5f5f5` 두 단계 회색으로만 만든다.
- **색은 카테고리에서만** 나오게 한다. 같은 카테고리 색을 칩 라벨·체크·입력 밑줄에 일관되게 쓴다.
- 완료를 "회색 클로버 → 색 클로버" 채움으로 보상한다. 취소선은 쓰지 않는다.
- 선택 상태는 검정 필 + 흰 글자, 다크 모드에선 흰 필 + 검정 글자로 반전한다.
- 리스트형 설정은 회색 박스 행(48px, radius 10)을 4px 간격으로 쌓는다.
- 부가 기능은 바텀시트 2열 아이콘 그리드로 모으고, 기능마다 고유 색 원 아이콘을 준다.
- 파괴적 동작은 빨간 텍스트로만 구분하고 버튼 배경은 중립 회색을 유지한다.

### Don't
- 카드·리스트·버튼에 그림자를 넣지 않는다(분리는 회색 면과 딤으로).
- 체크박스에 테두리를 넣지 않는다 — 빈 상태도 회색 채움.
- 칩·필에 각진 모서리를 쓰지 않는다(999px). 각진 사각형은 설정 행·보조 버튼(10px)뿐.
- 브랜드 바이올렛 `#6433ff`을 기능 버튼에 쓰지 않는다 — 일기·마스코트 같은 감정 화면 전용.
- UI 텍스트에 손글씨 꾸미기 폰트를 쓰지 않는다 — Pretendard만.
- 하단 탭바에 텍스트 라벨을 추가하지 않는다.

## Surfaces

| Level | Name | Light | Dark | Purpose |
|-------|------|-------|------|---------|
| 1 | Paper | `#ffffff` | `#000000` | 기본 배경 |
| 2 | Pill | `#f2f2f2` | `#1c1c1c` | 칩, 설정 행, 메뉴 항목 |
| 3 | Button | `#f5f5f5` | — | 보조 버튼 |
| 4 | Sheet | `#ffffff` + scrim .54 | — | 바텀시트, 플로팅 메뉴 |
| 5 | Violet | `#6433ff` | — | 일기 시트 |

## Elevation
기본적으로 그림자 없음. 위계는 ① 흰 배경 ② `#f2f2f2` 면 ③ 딤(`rgba(0,0,0,.54)`) 위에 뜬 흰 시트 — 세 단계로만 표현. 원형 이전/다음 버튼과 칩 안 + 버튼에만 1px 수준의 아주 옅은 외곽선.

## Imagery
- **클로버 시스템**: 로고(검정), 체크(카테고리 색), 기본 아바타(흰 클로버), 기분 이모지(3D 질감 클로버), 마스코트(보라 털뭉치 클로버).
- 사용자 사진은 월간 캘린더 날짜 셀·사진 인증에 썸네일로 들어감 — 유일한 풀컬러 이미지.
- UI 아이콘: 채움형 단색 24px, 둥근 모서리.

## Agent Prompt Guide

**Quick Color Reference**
- text: #1a1a1a · secondary #6e6e6e
- background: #ffffff (dark #000000)
- neutral fill: #f2f2f2 (칩·행), #f5f5f5 (버튼)
- empty check: #d4d8db
- selected: #000000 필 + 흰 텍스트
- accent: 카테고리 색 (기본 #1e2f98)
- scrim: rgba(0,0,0,.54)

**Example Component Prompts**
1. **Category Group**: 높이 32px `#f2f2f2` 필(padding 0 4px 0 12px) 안에 자물쇠 16px `#9f9ea3` + "카테고리 1" Pretendard 14px 700 `#1e2f98` + 24px 흰 원 "+" 버튼. 아래 12px 간격으로 할 일 행: 24px 클로버(완료 `#1e2f98` + 흰 체크, 미완료 `#d4d8db`) + 10px + 15px 400 `#1a1a1a` 텍스트.
2. **Calendar Day**: 세로 스택 — 26px 클로버(`#d4d8db`) 위, 날짜 13px 아래, 간격 4px. 오늘은 숫자를 26px 검정 원 + 흰 13px 700으로 대체.
3. **Settings Row**: 높이 48px, `#f2f2f2`, radius 10px, padding 0 16px, 좌 "색상" 14px 500, 우 12px 카테고리 색 점 + `›`. 행 간격 4px.
4. **Action Sheet**: 흰 시트 상단 radius 24px, max-width 500px, 핸들 40×4 `#cdcdcd`, 제목 16px 700. 2열 그리드 항목 = 28px 원(`#eb7b2f`) 흰 아이콘 + "오늘 또 하기" 15px. 하단 52px `#f5f5f5` 버튼 2개(radius 10px).

## Similar Brands
- **MyRoutine** — 같은 국내 루틴/투두 앱이지만 초록 단일 액센트 + 표 vs 투두메이트는 흑백 크롬 + 사용자 색
- **Instagram** — 상단 프로필 필 전환, 흑백 크롬 위 사용자 콘텐츠가 색을 담당
- **Things 3** — 보더 없는 담백한 할 일 행

## Quick Start

### CSS Custom Properties

```css
:root {
  /* Neutral */
  --color-paper: #ffffff;
  --color-pill: #f2f2f2;
  --color-button: #f5f5f5;
  --color-avatar: #eeeeee;
  --color-empty: #d4d8db;
  --color-handle: #cdcdcd;
  --color-lock: #9f9ea3;
  --color-ink: #000000;
  --color-text: #1a1a1a;
  --color-text-secondary: #6e6e6e;
  --color-scrim: rgba(0, 0, 0, .54);
  --color-sunday: #f04452;
  --color-saturday: #3b7cf6;
  --color-tooltip: #fbf3c4;

  /* Category (사용자 선택값으로 교체) */
  --cat: #1e2f98;
  --cat-default-1: #1e2f98;
  --cat-default-2: #205543;
  --cat-default-3: #426f75;

  /* Action icons */
  --act-repeat: #eb7b2f;
  --act-routine: #4f57d4;
  --act-time: #c678ce;
  --act-photo: #5ab275;
  --act-subtask: #55a992;
  --act-memo: #f1df71;
  --act-info: #363636;

  /* Brand */
  --color-brand: #6433ff;

  /* Type */
  --font-ui: Pretendard, Roboto, -apple-system, system-ui, sans-serif;
  --text-caption: 12px;
  --text-meta: 13px;
  --text-body: 15px;
  --text-chip: 14px;
  --text-title-sm: 16px;
  --text-title: 18px;

  /* Size */
  --pill-h: 40px;
  --chip-h: 32px;
  --check: 24px;
  --day-clover: 26px;
  --avatar: 64px;
  --row-h: 48px;
  --btn-h: 52px;
  --sheet-max: 500px;

  /* Radius */
  --radius-row: 10px;
  --radius-menu: 20px;
  --radius-sheet: 24px;
  --radius-pill: 999px;
}

[data-theme="dark"] {
  --color-paper: #000000;
  --color-pill: #1c1c1c;
  --color-avatar: #232323;
  --color-empty: #333333;
  --color-text: #ffffff;
  --color-ink: #ffffff; /* 선택 필 반전 */
}
```

### Clover Check (SVG)

```html
<!-- 4개 원을 겹친 클로버. fill = var(--cat) 완료 / var(--color-empty) 미완료 -->
<svg width="24" height="24" viewBox="0 0 24 24" aria-hidden="true">
  <g fill="var(--cat)">
    <circle cx="8" cy="8" r="6.2"/><circle cx="16" cy="8" r="6.2"/>
    <circle cx="8" cy="16" r="6.2"/><circle cx="16" cy="16" r="6.2"/>
  </g>
  <path d="M7.5 12.2l3 3 6-6.2" fill="none" stroke="#fff" stroke-width="2.2"
        stroke-linecap="round" stroke-linejoin="round"/>
</svg>
```
