### React_Spring_06

#### React (중찹 라우팅 분리 / Redirection)
- 하나의 라우팅 설정에서 `children` 속성으로 중첩 라우팅이 가능하다.
- 페이지가 많아지면 `root.js` 가 복잡해짐
- 복잡해질 가능성이 있는 라우팅 부분을 함수로 반환하는 설정하면 가독성 및 유지 보수가 편리해짐.
- `react` 에 `<Navigate>` 태그에 `replace` 속성으로 `redirection` 처리

#### React (useParams)
- `PathVariable` 같은 것.
- `URL` 에 추가를 하는 내용
- ` : (콜론)` 사용
- 특정 식별자의 경로 사용 시, 컴포넌트에서 주소창의 일부를 활요해야함
- `react-router` 의 `useParams()`로 지정된 변수 추출 가능