### React_Spring_15

#### Spring (Service Layer CRUD)
- `create`에서는 `return`타입을 신경써줘야함
  1. 새로 생성한 데이터를 그 자체를 반환
  2. `PK`를 반환하는 경우
- `update` 기능은 반환을 `void` 로 하고 예외 처리
  1. `DB`에서 데이터를 가져와서 해야함
- `delete` 는 `deleteById` 메소드를 이용하여 기능 구현.

#### Spring (Page DTO)
- 공통으로 사용되기 때문에 따로 빼서 상속을 시켜줌으로써 사용 가능하도록 하면 유지보수에 좋음.