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

### Springboot 5
- 메서드를 이용해 데이터를 `CRUD`를 할 경우 `JpaRepository`를 상속 받은 `Interface`를 정의하고 그 안에 사용하고자하는 메서드를 정의해야함
```
ex)
public interface QuestionRepository extends JpaRepository<Question, Integer>{
	Question findBySubject(String subject);
	Question findBySubjectAndContent(String subject, String content);
	List<Question> findBySubjectLike(String subject);

}
```
- `Springboot` 안에서 `Test` 코드를 이용할 경우 `DB` 세션이 끊김으로 인한 오류가 발생할 수 있음
- 실질적인 서버에서는 발생하지 않는 오류임
- 오류를 해결하기 위해 `Transactional` 애너테이션 사용
- `Java` 파일이 기능별로 정리가 필요함
- 템플릿 : 자바 코드를 삽입할 수 있는 `HTML` 형식의 파일
- 템플릿 엔진 `thymeleaf`

### Springboot 6
- `@Configuration` : 스프링의 환경 설정 파일 애너테이션
- `@EnableWebSecurity` : 모든 요청 `URL`이 스프링 시큐리티의 제어를 받도록 하는 애너테이션, 스프링 시큐리티 활성화 역할
- 비밀번호 보안을 위한 암호화 작업 : `BCryptPasswordEncoder` 클래스 사용, 비크립트 해시 함수