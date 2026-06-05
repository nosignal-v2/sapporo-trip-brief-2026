# AZITMAKER Design Guide

Source reference: `/Users/shinhoeroe/Downloads/01. 250108_AZITMAKER_CI guideline.ai`

## Brand Principles

AZITMAKER는 `F&B EATERTAINMENT COMPANY`라는 슬로건을 가진 식음료 기반 브랜드다. 단순한 F&B보다 더 편집적이고 감각적인 인상을 가져야 한다. 전체 톤은 미니멀, 하이컨트라스트, 장인적, 클래식 세리프 감성을 기준으로 한다.

핵심 인상:

- Minimal
- High contrast
- Editorial
- Artisan
- F&B eatertainment
- Classic serif attitude

디자인 판단 기준:

- 음식 브랜드처럼 따뜻하지만, 카페 메뉴판처럼 가볍게 보이지 않는다.
- 스타트업 UI처럼 둥글고 친근하게 만들기보다, 편집물과 브랜드 북에 가까운 긴장감을 유지한다.
- 장식보다 여백, 타이포그래피, 흑백 대비, 제한된 오렌지 포인트로 감각을 만든다.
- 오렌지는 브랜드 시그니처이지만 많이 쓰지 않는다. 강조와 행동 지점에만 사용한다.
- 브랜드 자산은 재조합하지 않는다. 로고는 가능한 경우 원본 에셋을 사용한다.

## Assets

### Logo Typo

`AZITMAKER` 대문자 워드마크가 기본 로고다. 클래식한 세리프 기반의 고급스럽고 에디토리얼한 인상이 핵심이다.

사용 규칙:

- 로고를 임의의 텍스트로 다시 조합하지 않는다.
- 웹폰트나 유사 세리프 폰트로 `AZITMAKER`를 대체하지 않는다.
- 로고에는 한글 폰트를 사용하지 않는다.
- 가능한 경우 원본 벡터, SVG, PNG 에셋을 사용한다.
- 로고 주변에는 충분한 여백을 둔다.

### Logo Symbol

타원 안의 유기적인 블랙 심볼을 사용한다. 기하학적 아이콘이 아니라 수공예적 시그니처에 가깝다.

사용 규칙:

- 심볼을 단순 원형 아이콘으로 재해석하지 않는다.
- 라인을 정교하게 정리하거나 기하학적으로 보정하지 않는다.
- 독립 사용 시 배경과 충분한 대비를 확보한다.

### Favicon

오렌지색 비정형 원형 마크가 브랜드 포인트를 강하게 보여준다.

사용 규칙:

- favicon, 작은 배지, selected state, active state에 사용할 수 있다.
- CTA 장식이나 패턴으로 과도하게 반복하지 않는다.
- 정확한 원본 형태가 있으면 원본 에셋을 우선한다.

### Slogan

공식 슬로건은 `F&B EATERTAINMENT COMPANY`다.

사용 규칙:

- 영문 대문자 사용을 기본으로 한다.
- 브랜드 슬로건, 캡션, 섹션 라벨에서는 넓은 자간의 편집적 인상을 유지한다.
- 본문, UI 입력, 긴 문장에는 넓은 자간을 적용하지 않는다.

## Typography

### Brand Typefaces

원본 CI 기준:

- Logo and brand headline: `Day Roman Regular +0.25 stroke`
- English meta, caption, UI label: `DIN2014 Regular W110%`

사용 방향:

- `Day Roman`은 로고, 큰 브랜드 헤드라인, 감성적 강조에만 사용한다.
- `DIN2014`는 영문 캡션, 작은 라벨, 숫자, UI 메타 텍스트에 적합하다.
- 라이선스 또는 웹 적용이 불확실하면 실제 서비스에서는 대체 폰트와 fallback을 명시한다.

### Korean Text

원본 가이드에서 한글 본문 서체는 별도 정의가 필요하다. 실무 구현에서는 다음 fallback을 우선한다.

```css
--font-ko: "Pretendard Variable", "Pretendard", "Noto Sans KR", "Apple SD Gothic Neo", system-ui, sans-serif;
```

한글 사용 규칙:

- 본문, UI, 상세 설명은 `Pretendard` 계열을 기본으로 한다.
- 한글 제목은 너무 둥글거나 캐주얼한 인상을 피한다.
- 로고 영역에는 한글 폰트를 적용하지 않는다.
- 긴 본문은 자간을 넓히지 않는다.

### English and Meta

```css
--font-brand-serif: "Day Roman", "Cormorant Garamond", "Times New Roman", serif;
--font-meta: "DIN 2014", "DIN2014", "IBM Plex Mono", "Helvetica Neue", Arial, sans-serif;
```

Meta typography:

- 영문 라벨은 uppercase를 기본으로 한다.
- 숫자, 시간, 캡션, 가격, 상태값은 DIN 계열로 단정하게 처리한다.
- 넓은 자간은 슬로건과 브랜드 캡션에만 제한적으로 사용한다.

## Color Tokens

공식 컬러 시스템:

- `Perfection`: `#f2efe6`, RGB `242 239 230`, CMYK `4 4 9 0`
- `Concentration`: `#000000`, RGB `0 0 0`, CMYK `75 68 67 90`
- `Artisan`: Pantone `7578C`, `#f15d22`, RGB `224 103 55`, CMYK `0 79 100 0`

주의:

- 원본 가이드 안에서 `Artisan` 컬러는 `#f15d22`와 RGB `224 103 55`가 함께 적혀 있다.
- 두 값은 디지털 색상 기준으로 정확히 일치하지 않는다.
- CSS token은 우선 공식 HEX 표기인 `#f15d22`를 사용한다.
- 원본 가이드의 RGB 표기와 HEX 표기 불일치는 브랜드 담당 확인이 필요하다.

### CSS Tokens

```css
:root {
  --azit-perfection: #f2efe6;
  --azit-concentration: #000000;
  --azit-artisan: #f15d22;

  --azit-bg: var(--azit-perfection);
  --azit-text: var(--azit-concentration);
  --azit-line: var(--azit-concentration);
  --azit-accent: var(--azit-artisan);

  --azit-inverse-bg: var(--azit-concentration);
  --azit-inverse-text: var(--azit-perfection);
}
```

Alpha or rgba usage:

```css
:root {
  --azit-perfection-rgb: 242 239 230;
  --azit-concentration-rgb: 0 0 0;
  --azit-artisan-rgb-from-hex: 241 93 34;
}
```

Do not use `224 103 55` as the CSS RGB value until the brand color inconsistency is resolved.

## Color Usage

### Primary Light Mode

브랜드 기본 배경은 `Perfection`, 기본 텍스트와 라인은 `Concentration`, 액션과 강조는 `Artisan`을 사용한다.

```css
.page {
  background: var(--azit-perfection);
  color: var(--azit-concentration);
}
```

사용 기준:

- 일반 웹사이트
- 브랜드 소개
- 문서형 페이지
- 메뉴, 리스트, 운영 정보
- F&B 콘텐츠 아카이브

### Inverse Editorial Mode

검은 배경을 사용하는 인버스 모드는 강한 브랜드 순간에만 사용한다.

```css
.section-inverse {
  background: var(--azit-concentration);
  color: var(--azit-perfection);
}
```

사용 기준:

- 첫 화면 hero
- 캠페인 섹션
- 발표자료 chapter
- 임팩트 있는 quote 또는 statement
- 심볼 중심 브랜드 컷

### Accent Use

`Artisan`은 제한적으로 사용한다.

적합:

- CTA
- active state
- focus state
- 선택된 nav item
- 핵심 수치
- 작은 심볼 또는 favicon

부적합:

- 넓은 배경 반복
- 긴 본문
- 모든 버튼
- 카드 테두리 전체
- 장식 패턴 남용

## Layout System

기본 레이아웃은 여백이 큰 편집물처럼 구성한다.

원칙:

- 화면 가장자리에 충분한 margin을 둔다.
- 라인과 구획은 얇고 명확하게 쓴다.
- 카드 형태를 쓰더라도 radius를 크게 만들지 않는다.
- 시각적 밀도는 낮추고, 정보 위계는 크게 만든다.
- 중앙 정렬보다 왼쪽 정렬을 기본으로 한다.
- 한 섹션에는 하나의 메시지를 둔다.

Recommended base:

```css
:root {
  --space-page-x: clamp(24px, 5.5vw, 88px);
  --space-page-y: clamp(28px, 5.5vh, 72px);
  --radius-card: 0px;
  --line-width: 1px;
}
```

Cards:

- 배경은 `Perfection` 또는 아주 옅은 tint를 쓴다.
- 라인은 `Concentration`을 낮은 opacity로 쓴다.
- 내부 여백은 넉넉하게 둔다.
- 카드 안에 카드를 넣지 않는다.

## Implementation Notes

- 여행 브리핑 화면에서는 정보 구조가 우선이다. 날짜, 시간, 장소, 이동 판단이 먼저 읽혀야 한다.
- 부록이나 표형 정보는 카드 대신 얇은 라인과 넉넉한 행간을 사용해 문서형으로 처리한다.
- 오렌지 포인트는 active state, 핵심 숫자, 작은 섹션 라벨에 제한한다.
- 발표 화면용 본문은 14px 아래로 내리지 않는다.
- `letter-spacing`은 전역적으로 `0`을 유지한다.
- 그라디언트, blob, bokeh, 장식용 SVG를 사용하지 않는다.

## Verification Checklist

- 브랜드 토큰이 `Perfection / Concentration / Artisan` 범위 안에 있는가
- 로고와 슬로건을 텍스트로 재조합하지 않았는가
- 작은 본문이 발표 화면에서 읽히는가
- 카드 안에 카드가 들어가지 않았는가
- nav dot 개수와 슬라이드 개수가 같은가
- 키보드, 클릭, 터치 이동이 작동하는가
- GitHub Pages 배포 후 공개 URL에서 새 CSS와 `design.md`가 반영됐는가
