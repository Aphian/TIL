### React_Spring_33

#### Spring (Entity CRUD)
- 연관 관계를 테스트 할 경우 `ToString` 어노테이션 사용한 부분에 주의를 해야함.
- 조회를 할 경우 연관관계가 되어 있을 경우 `ToString (exclude)` 를 안하면 테이블을 두 번 조회를 하게 되면서 지연 로딩이 된다.
- `Transactional` 어노테이션을 설정한 `test` 에 실행결과를 보면 쿼리를 두번 날려서 두 번 테이블을 조회하게 된다. 이 어너테이션일 없으면 에러가 발생함. `DB` 연결이 두번이 이루어짐. (세션이 하나 더 필요하다.) --> 이걸 한번에 처리하기 위한 것이 필요함.
- `EntityGraph` 어노테이션 또는 조인을 구현해서 테이블을 한번 조회(DB 한번 연걸)를 하게 끔 해줘야함.
- `Repository`에 구현을 해주면 됨.
```
ex.
// 자동으로 조인을 해준다 라고 생각하면 됨.
// EntityGraph 에 어떤 얘와 연결을 해주냐 명시
// ElementCollection 어너테이션 설정한 변수 명시
@EntityGraph(attributePaths = "imageList")
// :pno 변수 작성
@Query("select p from Product p where p.pno = :pno")
Optional<Product> seletOne(@Param("pno") Long pno);
```
- 쿼리가 한번만 날아가면서 에러가 발생하지 않음.
- `@Modifying` 어노테이션을 설정하면 `query`를 사용하여 수정을 할 수 있음.
- `JPA`의 연관관계 같은걸 처리할 때 연관되어 있는 `EntityCollcetion`을 계속 사용해야됨 다른 부분을 다루면 문제가 커지기 때문.