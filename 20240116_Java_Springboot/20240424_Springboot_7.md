### Springboot 7
- `@EnableAutoConfiguration` : 필수적인 설정들의 처리, 다양한 설정들의 일부가 자동으로 완료됨
- `@ComponentScan` : 자동으로 컴포넌트 클래스를 검색하고, 스프링 애플리케이션 컨텍스트에 빈으로 등록, 의존성 주입이 간편해짐
- `@Configuration` : `Java` 기반의 설정파일로 인식
- `application.properties` : 톰캣의 포트번호, 컨텍스트 패스 설정, 데이터베이스 관련 정보 등 애플리케이션에서 사용하는 여러가지 설정을 해당 파일에 `Key - Value` 형식으로 선언해서 사용할 수 있도록 해줌
- `@Autowired` : 빈(`bean`)으로 등록된 인스턴스를 클래스에 주입하는데 사용
- `sqlSessionFactory` : 마이바티스와 스프링의 연동 모듈로 사용, `factoryBean` 객체는 데이터 소스를 참조하며, `XML Mapper(SQL 쿼리 작성 파일)`의 경로와 설정 파일 경로등의 정보를 갖는 객체

### Springboot 8
- `@Bean` 의 `name` 속성을 선언하면 메서드명으로 빈을 주입받을 수 없게 됨
- `name` 속성으로 지정된 상태에서 `getBean()` 메서드를 호출하면 예외가 발생함
- `@Mapper` : `XML Mapper` 에 선언된 `SQL` 중에서 메서드명과 동일한 `id`를 가진 `SQL` 쿼리를 찾아 실행함, `Mapper`에는 어노테이션이 필수적임
- `MyBatisX 플러그인` : `Mapper` 와 `MML Mapper` 간의 이동이 쉬워지고 오류를 쉽게 캐치 가능

### Springboot 9
- `factoryBean.setMapperLocation()` : 선언해야 `XML Mapper`를 인식함
- `mybatisConfig()` : `application.properties`에서 `mybatis.configuration` 으로 시작하는 설정을 읽어 스프링 컨테이너에 빈으로 등록
- `Springboot` 는 기본으로 내장되어 있는 `Jackson` 라이브러리를 이용해서 `JSON` 문자열로 결과를 반환

### Springboot 10
- `@Service` : 해당 클래스가 비지니스 로직을 담당하는 `Service Layer` 의 클래스 의미
- `@RequiredArgsConstructor` : `Lombok`에서 제공해주는 기능, 클래스 내에 `final`로 선언된 모든 멤버에 대한 생성자 생성
- `@Controller` : 사용자의 요청과 응답을 처리하는 컨트롤러 플래스 의미
  1. 컨트롤러 메서드는 리턴 타입을 선언할 수 있음.
  2. 리턴 문에 `HTML` 파일의 경로 선언
- `Model` : 메서드의 파라미터로 선언된 `Model` 인터페이스는 데이터를 화면으로 전달하는데 사용

### Springboot 11
- 

