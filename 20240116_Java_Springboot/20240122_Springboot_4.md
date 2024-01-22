### Springboot 4

#### Repository 생성
- 리포지터리 : 데이터베이스 테이블의 데이터들을 저장, 조회, 수정, 삭제 등을 할 수 있도록 도와주는 인터페이스
- 테이블에 접근하고, 데이터를 관리하는 메서드 제공
- `com.mysite.프로젝트명` 패키지에서 -> `New` -> `Interface` -> 인터페이스 생성
```
package com.mysite.sbb;

import org.springframework.data.jpa.repository.JpaRepository;

public interface QuestionRepository extends JpaRepository<Question, Integer> {

}
```
- `JpaRepository` 인터페이스 상속함.-> `JPA`가 제공하는 인터페이스 중 하나 `CRUD` 작업을 처리하는 메서드들이 내장 되어 있음
- `Question` 이라는 리포지터리 생성 / `Integer` 엔티티(테이블)의 기본키

#### JUnit 설치
- `JUnit` : 테스트 코드 작성, 작성한 테스트 코드 실행 때 사용하는 자바의 테스트 프레임워크
- 리포지터리를 이용하여 데이터를 저장하려면 관련 정보를 저장하는 컨트롤러, 서비스 파일이 필요함
- `JUnit`을 사요하면 이러한 프로세스를 따르지 않아도 리버지터리 개별적으로 실행해 테스트 가능
- `build.gradle` 에 수정
- 테스트 할 경우 로컬 서버를 중지를 해놓고 실행

#### URL 매핑
- `URL` 매핑을 위해서 컨트롤러 필요
- `@GetMapping("연결할 URL")` -> 로컬 서버를 실행한 뒤 접속 하고 출력이 되면 연결 성공
- 브라우저에 보이기 위한 화면에서 일반적으로 사용하는 방식은 템플릿 방식임
- 템플릿은 자바 코드를 삽일할 수 있는 `HTML` 형식의 파일을 말함
- 스프링 부트에서 템플릿 엔진을 지원하는데 `Thymelear, Mustache, Groovy, Freemarker, Velocity` 등이 있음
- 위의 엔진을 사용하려면 `build.gradle` 파일내의 수정

#### 템플릿 사용
- `src/main/resources` 디렉토리에 `templates` 선택 -> `New -> File` -> `HTML` 생성 
- 컨트롤러에서 `return` 값에 `html` 확장자 파일 작성