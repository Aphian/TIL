### Springboot 6

#### 페이징 
- 페이징 기능에 필요한 패키지
  1. `org.springframework.data.domain.Page` : 패이지을 위한 클래스
  2. `org.springframework.data.domain.Pagerequest` : 현재 페이지와 한 페이지에 보여 줄 게시물 개수 등을 설정을 위한 클래스
  3. `org.springframework.data.domain.Pageable` : 페이징 처리 클래스

#### 스프링 시큐리티
- 스프링 기반 웹 애플리케이션의 인증과 권한을 담당하는 스프링의 하위 프레임 워크
- 인증`(authenticate)` : 로그인과 같은 사용자의 신원을 확인하는 프로세스
- 권한`(authorize)` : 인증된 사용자가 어떤 일을 할 수 있는지 관리 하는 것
- `build.gradle` 파일 수정 -> `org.springframework.boot:spring-boot-starter-security`
- 빈`(bean)` : 스프링에 의해 생성 또는 관리되는 객체 / 컨트롤러, 서비스, 리포지터리 모두 빈에 해당한다.
- `@Bean` 애너테이션을 통해 자바 코드 내에서 별도로 빈을 정의하고 등록이 가능함
