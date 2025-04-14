### React_Spring_16

#### Spring (Paging DTO)
- 결과물은 데이터들을 반환함.
- `responseDTO` 에서는 `DTO` 목록 데이터, `total` 값, `RequestDTO`가 정보가 필요함
- 페이징 번호 계산
  1. `page size` 는 `10` 가정
  2. 만약 현재 `page`가 `3` 이면 `page num` 은 1 ~ 10
  3. 만약 현재 `page`가 `12` 이면 `page num` 은 11 ~ 20
  4. 만약 현재 `page`가 `10` 이면 `page num` 은 1 ~ 10
  5. 만약 현재 `page`가 `20` 이면 `page num` 은 11 ~ 20
  6. 끝 번호를 구하고 시작 번호를 구한다.
  7. 현재 페이지 /page size.0 -> 소수 점 올림 -> *page size -> -9 --> 시작번호가 됨
  8. 전체 목록 데이터가 페이지 끝보다 적을 경우 따로 계산을 해줘야 한다.
  9. 만약 전체 데이터`(total)` < `page * page size`
  10. `total` 이 `78` 이면 `8` 페이지까지만 있어야함.