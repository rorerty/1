# Notion Widgets — 미니멀 임베드 위젯 5종

노션 `/embed`에 URL만 넣으면 동작하는 **단일 파일 위젯**입니다. 빌드·서버·계정·API 키가 필요 없고, 모든 데이터는 브라우저 `localStorage`에만 저장됩니다.

**갤러리(미리보기)**: https://rorerty.github.io/1/

## 위젯

| 파일 | 설명 | 권장 높이 |
|---|---|---|
| `dday.html` | 시험일·마감일 D-day 카운터 + 진행률 + 실시간 시계 | 240px |
| `pomodoro.html` | 25/50분 집중 타이머 + 오늘 세션 카운터 + 알림음·화이트노이즈 | 280px |
| `matrix.html` | 드래그 앤 드롭 4분면(아이젠하워) 포커스 보드 + 3초 빠른 입력 | 420px |
| `gauge.html` | 매출·예산·회독 목표 달성률 원형+바 게이지 + 월 페이스 | 240px |
| `clock-quote.html` | 플립 디지털 시계 + 오늘의 한 줄 다짐(클릭 수정) | 240px |

## 공통 파라미터

- `theme=cream|sage|navy|blush` — 크림(기본) / 세이지 / 네이비(다크) / 블러시
- `title=...` — 창 상단 제목 (dday는 시험·마감 이름, gauge는 `label` 사용)
- `key=...` — localStorage 저장 공간 분리용. 같은 종류 위젯을 여러 개 쓸 때 지정

## 예시

```
https://rorerty.github.io/1/dday.html?theme=sage&title=건강운동관리사+필기&date=2027-05-15&start=2026-11-01
https://rorerty.github.io/1/pomodoro.html?theme=cream&title=오전+집중
https://rorerty.github.io/1/matrix.html?theme=navy&title=오늘의+포커스
https://rorerty.github.io/1/gauge.html?theme=cream&label=11월+매출+목표&current=2200000&goal=3000000&unit=원
https://rorerty.github.io/1/clock-quote.html?theme=blush&title=오늘의+다짐
```

## 파라미터 상세

**dday.html** — `date=YYYY-MM-DD`(목표일), `start=YYYY-MM-DD`(진행률 기준 시작일, 선택), `title`
**gauge.html** — `label`, `current`(현재값), `goal`(목표값), `unit=원|%|권|...`(선택), `theme`
그 외 위젯은 `theme`, `title`, `key`만 사용합니다.

## 노션에 넣는 법

1. 페이지에서 `/embed` 입력 → **임베드** 선택
2. 위 URL 붙여넣기 → `임베드 링크 만들기`
3. 블록 아래 가장자리를 끌어 권장 높이로 맞추기 (매트릭스는 420px 이상 권장)

## 참고

- 데이터는 **그 기기·그 브라우저**의 localStorage에만 남습니다. 기기를 바꾸면 따라가지 않습니다.
- 시계·D-day는 접속한 기기의 로컬 시간대를 따릅니다.
- 외부 요청·추적·광고가 전혀 없습니다(폰트는 시스템 폰트).
