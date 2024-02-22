### Springboot 2
- `JDK` 파일경로를 지정
- `JRE System Libarary` 에서 `Alternate JRE` 항목을 설치한 `JDK` 로 변경해야 함 -> `LinkedError` 발생함 

### Springboot 3
- `H2` 데이터 베이스 활용
- 주로 개발 환경에서 사용하는 자바 기반의 경량 `DBMS`
- `H2` 로컬 연결 후 적용이 안될 경우 서버 재시작

### Springboot 4
- `@Autowired` 애너테이션 : 비어 있는 값으로 선언된 변수에 스프링부트가 객체를 자동으로 만들어 주입해준다
- `@Autowired` 애너테이션을 사용하는 것 외에 `Sette` 메서드를 이용하여 생성자를 사용하는 방식이 권장됨
- 테스트 코드에 경우 생성자를 통한 객체 주입이 안되서 `@Autowired` 애너테이션을 사용함
- `Run` -> `Run As` -> `JUnit Test` 순서로 테스트 코드 실행
- `The file is locked` 오류가 발생 시 로컬 서버를 중지해줘야함
- `@Test` 애너테이션은 `testJpa`메서드가 테스트 메서드란 의미