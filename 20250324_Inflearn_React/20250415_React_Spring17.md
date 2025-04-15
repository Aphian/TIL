### React_Spring_17

#### Spring (QueryDSL Search)
- `service` 부분에서 `pageResponseDTO` 에서 변수를 `pageRequestDTO`받는 메소드를 생성
- `search interface` 에서 메서드에 변수를 `requsetDTO`로 생성
- `searchimpl` 에서 `return` 이 `page<>(PageRequestDTO 변수)` 인 메서드 구현 --> `QueryDSL` 사용하는 메서드
- `PageRequestDTO` 가 검색과 관련된 모든 데이터를 가지도록 하는 `DTO` 임
- `requestDTO` 안에 `page` 정보가 다 들어있음.
- `searchImpl` 에서 `pageable` 부분에서 `requestDTO` 에서 정한 값을 변수로 받을 수 있음.
- 메서드 호출에 이름을 부여할 수 있음 : `@Builder(builderMethodName = "이름")`