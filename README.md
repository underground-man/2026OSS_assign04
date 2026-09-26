# Assign04 - HTML Form

- 이름 / 학번: 박찬 / 22300330
- Vercel Deploy URL: (배포 후 추가 예정)

## 파일 구성

- `index.html` : 메인 페이지 (form1.html, form1_css.html 링크)
- `form1.html` : HTML Form 연습 + 주문하기 Form 클론 코딩
- `form1_css.html` : form1.html에 CSS 적용
- `form_ok.html` : Form 제출 후 이동하는 페이지

## Clone Coding 원본 URL

- https://getbootstrap.com/docs/5.2/examples/checkout/

---

# Weekly Review

## Key Learning

1. `form`의 `action`은 데이터를 보낼 주소, `method`는 보내는 방식(get / post)이다.
2. `label`의 `for`와 `input`의 `id`가 같아야 서로 연결된다.
3. CSS로 입력칸의 `width`, `padding`, `border` 등을 바꾸고 `:focus`, `:hover`로 상태별 스타일을 줄 수 있다.

## Form Elements

| 요소 | 용도 |
|---|---|
| `input type="text"` | 이름, 이메일, 주소 등 한 줄 입력 |
| `input type="radio"` | 하나만 선택 (성별, 결제 방법) |
| `input type="checkbox"` | 여러 개 선택 (관심 분야, 정보 저장) |
| `input type="date"` | 날짜 선택 (생년월일) |
| `input type="color"` | 색상 선택 |
| `select` / `optgroup` | 목록에서 선택 (전공, 지역) / 옵션 그룹 묶기 |
| `datalist` | 입력칸에 자동완성 목록 제공 (좋아하는 언어) |
| `textarea` | 여러 줄 입력 (자기소개) |
| `fieldset` / `legend` | 입력 항목 묶기 / 묶음 제목 |
| `input type="submit"` | 제출 버튼 |

## HTML vs CSS

- `form1.html` : HTML 태그만 사용해서 브라우저 기본 모양으로 보인다.
- `form1_css.html` : 같은 HTML에 CSS를 추가해서 입력칸 너비를 맞추고, 테두리를 둥글게 하고, Form 배경색을 넣고, 버튼 색과 focus / hover 효과를 적용했다.

## Problem & Solution

- 문제: 처음 코드에서 `<label for="email">`인데 input이 `id="emaii"`로 오타가 있어서 label을 눌러도 입력칸이 선택되지 않았다.
- 해결: input의 `id`를 `email`로 고쳐서 연결했다.

## Reflection

- radio는 같은 `name`끼리 묶여서 하나만 선택된다는 것을 알게 되었다.
- `datalist`는 `select`와 달리 목록에 없는 값도 직접 입력할 수 있다.
- 궁금한 점: post로 보낸 데이터를 서버에서 어떻게 받아서 처리하는지 궁금하다.
