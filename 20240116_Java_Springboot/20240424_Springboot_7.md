### Springboot 7
- `@EnableAutoConfiguration` : 필수적인 설정들의 처리, 다양한 설정들의 일부가 자동으로 완료됨
- `@ComponentScan` : 자동으로 컴포넌트 클래스를 검색하고, 스프링 애플리케이션 컨텍스트에 빈으로 등록, 의존성 주입이 간편해짐
- `@Configuration` : `Java` 기반의 설정파일로 인식
- `application.properties` : 톰캣의 포트번호, 컨텍스트 패스 설정, 데이터베이스 관련 정보 등 애플리케이션에서 사용하는 여러가지 설정을 해당 파일에 `Key - Value` 형식으로 선언해서 사용할 수 있도록 해줌