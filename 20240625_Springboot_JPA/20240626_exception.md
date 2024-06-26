### 전역 예외 처리

- `@RestControllerAdvice` : 컨트롤러 전역에서 발생할 수 있는 예외를 잡아 `Throw` 해줌.
- `@ExceptionHandler` : 특정 클래스에서 발생할 수 있는 예외를 `Throw` 해줌
- `@Slf4j` : 선언된 클래스에 자동으로 로그 객체를 생성, `log.error()`, `log.debug()` 로깅 관련 메서드 사용

#### JPA Service Layer
- `@Transactional` : `JPA`를 사용한다면, 서비스 클래스에 필수적으로 사용되는 어노테이션, 실행, 종료, 예외를 자동으로 처리 해준다.