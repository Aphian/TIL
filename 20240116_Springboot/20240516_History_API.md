### Spring boot 19
- `Ajax`는 페이지 번호에 해댱되는 데이터를 조회하되 주소는 변경되지 않기 때문에 브라우저를 새로고침해도 페이지 번호가 유지되지 않는 문제가 있음 
- `History API`를 이용해서 `URL`를 강제로 변경해 비동기 페이징 처리 문제를 해결해야함

#### History API
- 사용자가 페이지에 접근하면 브라우저 세션에 기록이 쌓임
- 세션 기록에 접근 할 수 있게 해주는 객체가 `History` 객체라고함

|메서드|기능|
|--|--|
|history.back()|현재 페이지 기준 뒤로 이동|
|history.forward()|현재 페이지 기준 앞으로 이동|
|history.go(-1)|현재 페이지 기준 뒤로 이동|
|history.go(1)|현재 페이지 기준 앞으로 이동|
|history.go() / history.go(0)|페이지 새로고침|

- `history.replaceState()` 메서드로 강제로 `URL`를 변경해 `Ajax` 페이징의 새로고침 문제 해결
