# Assign04 - HTML Form

- 이름 / 학번: 박찬 / 22300330
- GitHub Repository: https://github.com/2026-2-OSS/assign04-c02-22300330 , https://github.com/underground-man/2026OSS_assign04
- Vercel Deploy URL: (배포 후 추가 예정)

## 파일 구성

| 파일 | 설명 |
|---|---|
| `index.html` | 메인 페이지, form1.html / form1_css.html 링크 |
| `form1.html` | HTML Form 요소 연습 (입력 항목 17개) + Checkout Form 클론 코딩 |
| `form1_css.html` | form1.html을 복사하여 CSS를 적용한 버전 |
| `form_ok.html` | Form 제출 후 이동하는 페이지 (전송된 값 표시) |

## Clone Coding 원본

- Bootstrap Checkout Example: https://getbootstrap.com/docs/5.2/examples/checkout/
- 디자인보다 Form 구조(장바구니 요약, Promo code, Billing address, Payment)와 입력 요소 사용에 집중해서 클론 코딩했습니다.

---

# Weekly Review

## 1. Key Learning

1. **`<form>`의 동작 방식**: `action`은 데이터를 보낼 주소, `method`는 보내는 방식입니다. `get`은 값을 URL의 query string(`?uname=...&email=...`)으로 보내고, `post`는 요청 본문(body)에 담아 보냅니다. 서버에서 값을 구분하는 기준은 `id`가 아니라 **`name` 속성**입니다.
2. **`<label>`과 입력 요소의 연결**: `label`의 `for` 값과 `input`의 `id` 값이 같아야 연결됩니다. 연결되면 label을 클릭해도 입력칸이 선택되고, 스크린리더 같은 접근성 도구도 올바르게 읽어 줍니다.
3. **CSS로 Form 꾸미기**: 속성 선택자(`input[type="text"]`)로 입력 타입별 스타일을 지정하고, `:hover`, `:focus`, `:invalid` 같은 가상 클래스로 상태별 스타일을 줄 수 있습니다. `width: 100%` + `box-sizing: border-box`로 입력칸 너비를 맞춥니다.

## 2. Form Elements

| 요소 | 용도 | 사용 예 |
|---|---|---|
| `input type="text"` | 한 줄 텍스트 입력 | 이름, 주소, Username |
| `input type="email"` | 이메일 입력 (형식 자동 검사) | 이메일 |
| `input type="password"` | 입력 내용이 가려지는 텍스트 | 비밀번호 |
| `input type="radio"` | 여러 개 중 **하나만** 선택 (같은 `name`으로 묶음) | 성별, 결제 수단 |
| `input type="checkbox"` | 여러 개 **복수 선택** / 단일 동의 | 관심 분야, 개인정보 동의 |
| `input type="date"` | 달력에서 날짜 선택 | 생년월일 |
| `input type="number"` | 숫자 입력 (`min`, `max`) | 나이 |
| `input type="range"` | 슬라이더로 범위 안의 값 선택 | HTML 실력 |
| `input type="tel"` | 전화번호 입력 (`pattern`으로 형식 지정) | 전화번호 |
| `input type="url"` | URL 입력 (형식 자동 검사) | GitHub 주소 |
| `input type="file"` | 파일 첨부 (`accept`로 파일 종류 제한) | 프로필 사진 |
| `input type="color"` | 색상 선택기 | 좋아하는 색 |
| `input type="hidden"` | 화면에 보이지 않지만 함께 전송되는 값 | formType |
| `input type="submit"` / `reset` / `<button>` | 제출 / 초기화 버튼 | 제출, Redeem, Continue to checkout |
| `select` + `option` | 드롭다운 목록에서 선택 | 전공, Country, State |
| `optgroup` | select 안의 option을 그룹으로 묶음 | 전공(공학 / 인문·사회 / 디자인) |
| `datalist` | input에 자동완성 후보 제공 (직접 입력도 가능) | 프로그래밍 언어 |
| `textarea` | 여러 줄 텍스트 입력 | 자기소개 |
| `fieldset` + `legend` | 관련 입력 항목을 묶고 제목 달기 | 기본 정보 / 학교·관심사 / 기타 |
| `label` | 입력 요소의 이름표 (`for` ↔ `id`) | 모든 입력 항목 |

그 밖에 `required`, `placeholder`, `checked`, `min`/`max`, `minlength`, `maxlength`, `pattern`, `inputmode` 속성도 사용했습니다.

## 3. HTML vs CSS

| 구분 | form1.html | form1_css.html |
|---|---|---|
| 구조 | HTML 태그만 사용 | form1.html과 **같은 HTML 구조** + `<style>` 추가 |
| 레이아웃 | 브라우저 기본 스타일, `<br>`로 줄바꿈 | `display: block`, `margin`으로 간격 조절 (`<br>`은 CSS로 숨김) |
| Form 영역 | 구분 없음 | 흰색 카드(`background-color`, `border`, `border-radius`, `box-shadow`), 최대 너비 720px 가운데 정렬 |
| Input / Select / Textarea | 기본 크기, 얇은 테두리 | `width: 100%`, `padding`, 둥근 테두리, 연한 배경색 |
| Label | 일반 텍스트 | 굵은 글씨, 색상, 입력칸 위에 block으로 배치 |
| fieldset / legend | 기본 회색 테두리 | 둥근 테두리 + 파란 배지 형태의 legend |
| Button | 브라우저 기본 버튼 | 파란 배경 / 흰 글씨, 초기화 버튼은 회색, Checkout 버튼은 가로 전체 |
| 상태 표현 | 없음 | `:hover` 테두리 색 변경, `:focus` 파란 테두리 + 그림자, `:focus:invalid` 빨간 테두리, `:active` 버튼 눌림 효과 |

즉, **HTML은 "무엇을 입력받을지"(구조와 의미)**를 정하고, **CSS는 "어떻게 보일지"(모양과 상태)**를 정합니다. 같은 HTML이라도 CSS만 바꾸면 사용성이 크게 달라집니다.

## 4. Problem & Solution

**문제 1. label을 클릭해도 이메일 입력칸이 선택되지 않음**
- 원인: 처음 작성한 코드에서 `<label for="email">`인데 input은 `id="emaii"`로 오타가 있어 서로 연결되지 않았습니다.
- 해결: input의 `id`를 `email`로 고쳐 `for`와 `id`를 일치시켰습니다. 이후 모든 입력 항목의 `for`/`id`가 서로 맞는지 확인했습니다.

**문제 2. 배포 사이트에서 Form 제출 시 에러가 날 수 있음**
- 원인: Vercel 같은 정적 호스팅은 서버 프로그램 없이 HTML 파일만 제공하기 때문에, `method="post"`로 `.html` 파일에 제출하면 405 (Method Not Allowed) 에러가 날 수 있습니다.
- 해결: `method="get"`으로 바꿔서 값이 URL의 query string으로 전달되게 했고, `form_ok.html`에서 JavaScript `URLSearchParams`로 전달된 값을 화면에 표시하도록 했습니다.

**문제 3. CSS 적용 후 입력칸 사이 간격이 지나치게 넓어짐**
- 원인: form1.html에서 줄바꿈용으로 쓴 `<br><br>`이 `display: block`인 입력칸과 겹쳐 빈 줄이 생겼습니다.
- 해결: form1_css.html에서는 HTML 구조는 그대로 두고 `form br { display: none; }`으로 `<br>`을 숨긴 뒤, label과 input의 `margin`으로 간격을 조절했습니다.

## 5. Reflection

- 같은 `name`을 가진 radio는 하나만 선택되고, checkbox는 같은 `name`으로 여러 값이 전송된다는 점을 제출 결과(query string)를 보면서 확실히 알게 되었습니다.
- `type="email"`, `url`, `required`, `pattern`처럼 JavaScript 없이 HTML만으로도 기본적인 입력값 검사를 할 수 있다는 점이 새로웠습니다.
- `datalist`는 `select`와 비슷해 보이지만 목록에 없는 값도 직접 입력할 수 있다는 차이가 있었습니다.
- 궁금한 점: 실제 서비스에서는 HTML의 검사만으로는 충분하지 않을 것 같은데, 서버 쪽에서는 입력값 검증을 어떻게 하는지, 그리고 `post`로 받은 데이터를 서버(PHP 등)에서 어떻게 처리하는지 더 알아보고 싶습니다.
