### React_Spring_12

### Spring (Paging)
- `Spring JPA` 가장 강력한 장점 기능
- `Pagable` 라이브러리를 이용하여 처리
- 반환 값은 `Page` 객체로 반환
```
// PageRequest.of(처음시작, 개수, 정렬).오름차순/ 내림차순
Pageable pageable = PageRequest.of(0, 10, Sort.by("tno").descending());
// 결과 값
Page<Todo> result = todoRepository.findAll(pageable);
```
- 데이터가 10개 이하면 `count query` 처리를 한다.
- 동적으로 처리할 경우 `example` 기능이 있음
- 보통 `QueryDSL`를 사용하여 동적 페이징 처리를 함.