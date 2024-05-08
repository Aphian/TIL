### Springboot 2

#### Spring boot 구조
- `com.mysite.sbb` 패키지 : 자파 파일을 저장하는 공간
  1. 컨트롤러, 폼, `DTO`, `DB` 차리를 위한 엔티티, 서비스 등의 자바 파일 위치함
- `프로젝트명 + Application.java 파일`
  1. 프로그램 시작을 담당하는 파일
- `src/main/resources` 디렉토리
  1. 자파 파일을 제외한 `HTML`, `CSS`, `JavaScrpit`, 환경파일 저장공간 -> `static` 디렉토리 안에 저장함
  2. 하위 디렉토리 `templates` 템플릿 파일 저장
- `application.properties` 파일
  1. `sbb` 프로젝트의 환경 설정, 환경 변수 데이터베이스 등의 설정파일 저장
- `src/test/java` : `sbb` 프로젝트에서 작성한 파일을 테스트하는 코드 저장 공간
- `build.gradel` : `Gradle`이 사용하는 환경 파일