### Spring boot 25

- `@RequiredArgsConstructor` : 클래스 내에 `final`로 선언된 모든 멤버에 대한 생성자를 만들어줌.
- `@Transactional` : 트랜잭션 처리 방법 중 하나, 선언적 트랜잭션으로 불리는 기능, 메서드의 실행과 동시에 트랜잭션이 시작되고, 메서드의 정상 종료 여부에 따라 Commit 또는 Rollback 을 해준다.

- `JSP` 의 `${}` 표현식와 마찬가지로 타임리프에서도 `${}` 표현식을 이용해 컨트롤러에서 전달받은 데이터에 접근
- `th:fragement` : 다른 `HTML` 에서 `include` 또는 `replace` 와 같은 역할
- `th:block` : 실제적으로 컨텐츠 페이지의 내용을 채우는 기능

#### Today Error

- `Thymeleaf Syntax Error` : 컨트롤러에서 `HTML` 내의 `Thymleaf` 탬플릿 내에서 `JavaScript` 코드를 사용하려고 할 경우 발생할 수 있음
  1. 컨트롤러에서 변수를 가져올 경우 /*[[${ 변 수 }]]*/ 로 `JavaScript` 에 할당 해야됨
  2. 간혹 주석으로 값이 들어가서 서버에서 가져온 변수를 가져오고 그 후 그 변수를 이용하면 코드 읽기가 더 쉬워짐
  3. `th:inline = "javascript"` 로 `JavaScript` 를 감싸줘야 기능 변수를 변환 가능
- `DB`에 `Boolean` 타입의 값을 `JavaScript` 내에서 저장을 하려고 할 경우 `true` / `false`를 명시 해줘서 저장을 해야 오류가 발생하지 않음.