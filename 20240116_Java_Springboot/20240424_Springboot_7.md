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