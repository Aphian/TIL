### Springboot 3

#### ORM 이해
- `ORM(Object Relational Mapping)` : 데이터베이스의 테이블을 자바 클래스로 관리가 가능하게 해준다.
- 데이터베이스는 자바를 이해하지 못함 -> `ORM` 도구를 이용하면 자바 문법으로도 데이터베이스를 다룰수 있도록 해준다.
- `MySQL`, `오라클 DB`, `MS SQL` 등 종류의 관계 없이 일관된 자바 코드를 사용할수 있도록 프로그램 유지 보수하기가 편리하다.
- `SQL` 쿼리문을 자동으로 생성해 주므로 안정적으로 다룰수 있음.
- `DBMS` : 데이터베이스를 관리하는 소프트웨어

#### JPA 이해
- 스프링 부트는 `JPA(Java Persistence API)`를 이용하여 `DB` 관리
  1. `JPA`에서 대표적으로 하이버네이트가 있음
  2. 하이버네이트는 자바의 `ORM` 프레임워크

#### DB 설치
- `build.gradle` 파일에 사용할 `DB` 설치
  1. `Gradle` -> `Refresh Gradle Project` 라이브러리 설치
- `src/main/resources` 디렉토리 -> `application.perperties` 파일에 설정 추가
- `JPA` 환경 설정 : `build.gradle` 파일에 추가

#### Entity 생성
- `src/main/java` 디렉토리 `com.mysite.프로젝트명` 패키지에 생성
- `@Entity` 애너테이션을 적용해야 인식함
- `@ManyToOne`, `@OneToMany` 애너테이션으로 관계를 인식