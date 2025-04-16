### React_Spring_18

#### Spring (Controller)
- `@RestController` 어노테이션 설정 --> `Data`가 `JSON` 형태로 웹 브라우저에 보여줌.
- `@RequestMapping` 으로 경로를 정함.
- `@Pathvariable` 로 경로에 원하는 정보를 가져올 수 있음.
  1. `ex. /api/todo/33
  2. 항상성을 유지함 --> `queryString` 과 다른점.
- `queryString` 은 상황에 따른 정보가 다를 수 있기 때문에 사용함.

#### Spring (RestControllerAdvice)
- `@RestController` 에서 공통적인 예외가 발생했을 때 처리를 해준다.
- `@RestControllerAdvice` 어노테이션 설정.