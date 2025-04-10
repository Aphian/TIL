### React_Spring_14

#### Spring (DTO Setting & Service Layer)
- 동적 쿼리 데이터는 `DTO`로 받아 처리를 함.
- `JPA Entity`는 `JPA` 에서 관리는 하는 객체
- 그래서 `DTO`로 변환을 해서 처리를 해야함.
- 쓰고 버리고 하는 간단한 객체였음. -> 관리는 안했음.
- `DTO`는 테이블과는 관련이 없음 -> 상황에 따라 여러개 만들 수 있음
- `service` 계층을 만들어서 `DTO`를 변환해줌.
- `return` 타입이 `DTO`가 됨