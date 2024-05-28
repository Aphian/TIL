### Spring boot 25

- `@RequiredArgsConstructor` : 클래스 내에 `final`로 선언된 모든 멤버에 대한 생성자를 만들어줌.
- `@Transactional` : 트랜잭션 처리 방법 중 하나, 선언적 트랜잭션으로 불리는 기능, 메서드의 실행과 동시에 트랜잭션이 시작되고, 메서드의 정상 종료 여부에 따라 Commit 또는 Rollback 을 해준다.

- `JSP` 의 `${}` 표현식와 마찬가지로 타임리프에서도 `${}` 표현식을 이용해 컨트롤러에서 전달받은 데이터에 접근
- `th:fragement` : 다른 `HTML` 에서 `include` 또는 `replace` 와 같은 역할
- `th:block` : 실제적으로 컨텐츠 페이지의 내용을 채우는 기능