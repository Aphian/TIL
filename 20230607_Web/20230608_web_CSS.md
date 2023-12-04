## CSS
- CSS(Cascading Style Sheets) : HTML의 각 요소의 style을 정의하여 화면에 어떻게 렌더링하면 되는지 브라우저에게 설명하기 위한 언어.
- `Selector(선택자)` : style을 적용하기 위한 HTML 요소를 선택
- `Property(속성)` : HTML의 요소를 선택하고 속성과 값을 지정하여 style을 정의
- HTML에 CSS를 연동하는 방법
  1. `Link Style` : CSS 파일을 외부에서 가져옴
  2. `Embedding Style` : HTML 파일 내부에 CSS 포함 시키는 방식
  3. `Inline Style` : Tag에 직접 style을 입력하는 방식
---
### Selector(선택자)
- 전체 selector(`*`)
- `Tag selector` : 태그명을 가져와서 사용
- `ID selector` : 태그에 부여된 ID와 일치하는 요소 선택
- `Class selector` : 태그에 부여된 class와 일치하는 요소를 선택
- `Pseudo-Class Selector)` : 요소의 특정 상태에 따라 스타일을 정의할 때 사용
---
### Unit
- display property의 값
- `inline` : 선으로 인식 계속 붙어서 입력됨, 가로폭 끝까지 이어짐
  1. content의 너비만큼 가로폭 차지
  2. width, height, margin, padding 지정 불가
  3. 공백은 정의하지 않으면 space(4px)가 자동 지정
- `block`
  1. 항상 새로운 라인에서 시작
  2. 화면 크기 전체의 가로폭 차지
  3. width, height, margin, padding 지정 가능
- `inline-block` : block와 Inline 속성을 모두 갖춤
- `flexbox`
---
### Box model
- HTML 모든 요소는 box 형태의 영역을 가지고 있다.
- Content, Padding, Border, Margin 으로 구성