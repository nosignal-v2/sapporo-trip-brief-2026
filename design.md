# Dark Magazine Itinerary Brief Design Guide

## Concept

여행 일정 브리핑을 위한 어두운 매거진형 프레젠테이션 디자인이다. 목표는 장식보다 동선 이해를 우선하는 것이다. 화면은 검은 종이 위에 큰 제목, 얇은 라인, 오렌지 포인트, 단단한 카드 구조를 배치해 고급스럽지만 실무적으로 읽히게 만든다.

핵심 인상:

- Dark editorial
- Magazine spread
- High contrast itinerary
- Minimal orange accent
- Calm but interactive

## Design Principles

- 첫 화면은 브랜드나 여행명 자체가 크게 보여야 한다.
- 일정 브리핑은 감성 문장보다 날짜, 시간, 장소, 이동 판단이 먼저 읽혀야 한다.
- 한 슬라이드는 하나의 질문에 답한다.
- 주요 일정은 Day별 타임라인으로 보여준다.
- 예산, 대체안, 예약 순서는 별도 슬라이드로 분리한다.
- 장식용 이미지, 그라디언트, 블롭, 오브젝트를 쓰지 않는다.
- 색상은 제한된 팔레트만 사용한다.
- 작은 설명문도 발표 화면에서 읽혀야 한다.

## Color Tokens

새 색상을 추가하지 않는다.

```css
:root {
  --c-bg: #111111;
  --c-bg-alt: #1a1a18;
  --c-bg-orange: #e85d26;
  --c-fg: #f0ece5;
  --c-fg-2: #888880;
  --c-fg-3: #505048;
  --c-fg-light: #111111;
  --c-fg-light-2: #2a1810;
  --c-fg-light-3: rgba(17,17,17,0.55);
  --c-accent: #e85d26;
  --c-border: #282826;
}
```

사용법:

- `#111111`: 기본 배경
- `#1a1a18`: 카드 배경
- `#e85d26`: 챕터 배경, 포인트, 활성 네비게이션
- `#f0ece5`: 메인 제목과 핵심 텍스트
- `#888880`: 본문 설명
- `#505048`: 보조 메타, 그래프 기본 바
- `#282826`: 라인과 카드 테두리

## Typography

폰트:

- Korean UI/body: `Pretendard Variable`, `Pretendard`
- Display heading: `Barlow`
- Meta/label/time: `IBM Plex Mono`

```css
@import url("https://fonts.googleapis.com/css2?family=Barlow:wght@400;500;700;800;900&family=IBM+Plex+Mono:wght@400;500;700&display=swap");
@import url("https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/variable/pretendardvariable.css");
```

Font size tokens:

```css
:root {
  --sz-display: 160px;
  --sz-h1: 94px;
  --sz-h2: 56px;
  --sz-h3: 34px;
  --sz-lead: 20px;
  --sz-body: 15px;
  --sz-meta: 9px;
}
```

Body readability:

- 타임라인 설명문 `.vt-body`: `14px`, `line-height: 1.55`
- 카드 리스트 본문 `.bullet-list li`: `14px`
- 예약 설명 `.flow-desc`: `14px`
- 멤버 카드 본문 `.mini-card .body`: `14px`
- 가장 작은 본문은 14px 아래로 내리지 않는다.
- 메타 라벨은 작게 유지해도 되지만 핵심 정보로 쓰지 않는다.
- `letter-spacing`은 전역적으로 `0`을 유지한다.

## Layout System

Base slide:

```css
.slide {
  width: 100vw;
  height: 100vh;
  padding: 5.5vh 5.5vw;
  display: grid;
  grid-template-rows: auto 1fr auto;
  overflow: hidden;
}
```

Structure:

- 상단: 작은 섹션 라벨과 페이지 번호
- 중앙: 제목, 핵심 내용, 타임라인 또는 카드
- 하단: 짧은 보조 메타
- 오른쪽: 세로 nav dot

Spacing:

- 큰 화면에서는 여백을 넉넉하게 둔다.
- 카드 내부는 제목과 설명이 붙어 보이지 않도록 `gap`을 유지한다.
- 카드 안에 또 다른 카드를 넣지 않는다.

## Slide Types

### Cover

오렌지 배경을 사용한다. 여행명과 기간을 가장 크게 보여준다.

필수 요소:

- 여행명
- 기간
- 짧은 설명

### Chapter

오렌지 배경으로 흐름을 끊는다. 결론을 짧게 말한다.

예:

- 무리하지 않는 쪽
- 차량이 관건

### Statement

한 문장 결론을 크게 보여주는 슬라이드다.

구성:

- 작은 kicker
- 큰 결론
- 한 줄 근거

### Overview

Day 1~4 전체 일정표를 카드 4개로 보여준다.

각 카드:

- 날짜
- 핵심 장소
- 3개 이하의 요약 bullet

### Vertical Timeline

일정을 이해시키는 핵심 슬라이드다. Day별 상세 일정은 반드시 이 타입을 쓴다.

구성:

- 왼쪽 시간
- 중앙 세로 라인과 오렌지 포인트
- 오른쪽 일정 카드

정보 기준:

- 시간
- 장소
- 이동이나 예약 판단
- 날씨나 지연 시 대체안

### Stats

교통비, 출발 시간, 도착 시간처럼 숫자로 판단해야 하는 내용을 보여준다.

### Compare

대체안이나 의사결정을 2열로 비교한다.

추천 옵션은 오렌지 패널을 써서 분명히 표시한다.

### Budget Chart

가로 바 차트로 예산 압박을 보여준다.

강조가 필요한 항목만 오렌지 바를 사용한다.

### Member Wish Map

구성원 희망사항이 어느 날짜에 반영됐는지 보여준다. 3열 카드 그리드를 사용한다.

### Booking Order

실행 순서를 4개 카드로 보여준다.

예:

1. 항공권
2. 숙소
3. 비에이 버스
4. 차량 견적

## Interaction

기본 인터랙션:

- 키보드 `ArrowRight`, `Space`: 다음 슬라이드
- 키보드 `ArrowLeft`: 이전 슬라이드
- 화면 오른쪽 클릭: 다음
- 화면 왼쪽 클릭: 이전
- 터치 스와이프 지원
- 오른쪽 세로 nav dot 클릭 이동

전환:

```css
#deck {
  transition: transform 0.78s cubic-bezier(0.77, 0, 0.175, 1);
}
```

애니메이션:

- `fade-up`: 제목과 카드 진입
- `fade-in`: 조용한 표시
- `reveal-right`, `reveal-left`: 챕터감 있는 등장
- `scale-in`: 숫자 강조
- `kBarRise`: 예산 바 차트 등장

애니메이션은 정보 이해를 방해하지 않아야 한다. 텍스트는 등장 후 바로 읽을 수 있어야 한다.

## Responsive Rules

좁은 화면 기준:

```css
@media (max-width: 760px) {
  :root {
    --sz-display: 96px;
    --sz-h1: 62px;
    --sz-h2: 36px;
    --sz-h3: 25px;
    --sz-lead: 15px;
    --sz-body: 12px;
    --sz-meta: 8px;
    --pad-y: 4.5vh;
    --pad-x: 6vw;
  }
}
```

Mobile behavior:

- 4열 그리드는 2열로 줄인다.
- 비교, 통계, 멤버 그리드는 1열로 줄인다.
- 타임라인은 시간 영역을 넓혀 텍스트가 깨지지 않게 한다.

## Content Rules

일정 브리핑에는 다음이 반드시 보여야 한다.

- 전체 일정표
- Day별 상세 타임라인
- 이동 수단과 이동 판단
- 핵심 예약 순서
- 예산이 흔들리는 지점
- 대체 가능한 일정
- 구성원 희망사항 반영 위치

문장 규칙:

- 한 카드에는 한 판단만 넣는다.
- 너무 긴 설명은 두 문장 이하로 줄인다.
- 날짜와 시간은 숨기지 않는다.
- 불확실한 정보는 단정하지 않는다.
- 메타 라벨에는 핵심 정보를 넣지 않는다.

## Do Not

- 그라디언트를 쓰지 않는다.
- 새 hex color를 추가하지 않는다.
- 장식용 blob, orb, bokeh를 쓰지 않는다.
- 카드 안에 카드를 넣지 않는다.
- 본문을 14px 미만으로 줄이지 않는다.
- 일정 브리핑에서 감성 카피만 남기고 시간표를 빼지 않는다.
- 발표 자료 안에 사용법 설명을 길게 넣지 않는다.

## Verification Checklist

수정 후 확인한다.

- 슬라이드 개수가 의도와 일치하는가
- Day 1~4 타임라인이 바로 읽히는가
- 가장 작은 본문이 발표 화면에서 읽히는가
- 콘솔 오류가 없는가
- nav dot 개수와 슬라이드 개수가 같은가
- 키보드와 클릭 이동이 작동하는가
- 금지 색상, 그라디언트, 긴 대시가 없는가
- GitHub Pages 배포 후 공개 URL에서 새 CSS가 반영됐는가
