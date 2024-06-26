### 전역 예외 처리

- `@RestControllerAdvice` : 컨트롤러 전역에서 발생할 수 있는 예외를 잡아 `Throw` 해줌.
- `@ExceptionHandler` : 특정 클래스에서 발생할 수 있는 예외를 `Throw` 해줌
- `@Slf4j` : 선언된 클래스에 자동으로 로그 객체를 생성, `log.error()`, `log.debug()` 로깅 관련 메서드 사용

#### JPA Service Layer
- `@Transactional` : `JPA`를 사용한다면, 서비스 클래스에 필수적으로 사용되는 어노테이션, 실행, 종료, 예외를 자동으로 처리 해준다.
- `JPA`에는 영속성 컨텍스트 라는 개념이 존재함
  1. `Entity`를 영구히 저장하는 환경
  2. 애플리케이션과 데이터베시으 사이에서 객체를 보관하는 가상의 영역
  3. `Entity`를 조회하면 해당 `Entity`는 영속성 컨텍스트에 보관되며 값이 변경되면 트랜젝션이 종료되는 시점에 `update` 쿼리를 실행한다.
  4. 자동으로 쿼리가 실행되는 개념을 더티 채팅`(Dirty Checking)` 이라고 한다.
- `JPA Repository`의 `findById()`는 `Optional` 클래스를 리턴함 -> 반복적인 `Null` 처리를 피하기 위해 사용되는 클래스
- `orElseThrow()`는 `Optional` 클래스에 포함된 메서드 예외처리를 코드 한 줄로 처리가 가능하게 해준다.