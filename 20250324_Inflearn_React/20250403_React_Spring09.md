### React_Spring_09

#### Spring (setting)
- `vsCode`의 `STS (Spring Tool Suites)` 확장으로 설치
- `Spring boot` 프로젝트 생성
- `src/main/resources/application.properties` 파일에 `DB` 관련 설정
```
연결 DB Driver
spring.datasource.driver-class-name=org.mariadb.jdbc.Driver

연결 DB URL
spring.datasource.url=jdbc:mariadb://localhost:3306/apidb

연결 DB 계정
spring.datasource.username=username
spring.datasource.password=username

DB 설정
DB의 DDL(테이블 생성이나 객체 생성 등등) 가능
spring.jpa.hibernate.ddl-auto=update

SQL 포맷팅 설정
spring.jpa.properties.hibernate.format-sql=true

실행시 SQL 출력 여부
spring.jpa.show-sql=true
```