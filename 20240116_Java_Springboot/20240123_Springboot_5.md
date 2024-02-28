### Springboot 5

#### Root URL 매핑
- 서버의 `URL` 을 요청할 때 도메인명 뒤에 아무런 주소를 덧붙이지 않는 `URL`을 루트 `URL`이라고 함
- 루트 `URL`를 매핑하지 않고 서버에 접속 하면 404 오류 메시지가 나옴
- 루트 `URL` 설정
  1. 메서드 추가 `/` `URL` 매핑
  2. 리턴 문자열 `redirect:URL 주소`

#### 서비스 활용
- 서비스와 웹 서비스는 다른 개념
- 컨트롤러가 리포지터리를 직접 접근해 질문 목록 데이터를 조회 했음
- 대규모의 스프링 부트 프로젝트는 컨트롤러에서 리포지터리를 직접 호출하지 않고 중간에 서비스를 두어 데이터를 처리함
- 서비스를 사용하여 `SBB` 프로그램 개선
- 여기서 말하는 서비스란 스프링에서 데이터 처리를 위해 작성하는 클래스
- 사용하는 이유
  1. 복잡한 코드를 모듈화
  2. 직접적으로 접근을 할 경우 민감 데이터가 노출될 위험이 있음
- `DTO(Data Transfer Object)` 클래스 사용
- 앤티티 객체를 `DTO` 객체로 변환하는 작업이 필요함
- 변환할 시에도 서비스 필요
- 서비스는 컨트롤러와 리포지터리의 중간에서 엔티티 객체와 `DTO` 객체를 서로 변환하여 양방향에 전달하는 역할

#### 서비스 기능 생성
- `@Service` 애너테이션 작성 -> 서비스로 인식하게 해줌
- 컨트롤러에서 서비스 사용 : `Repository` 변수를 생성한 `DTO`이름 변경

#### 테그에 링크 연결
```
ex)
<a th:href="@{|/question/detail/${question.id}|}" th:text="${question.subject}"></a>
```
- `URL`은 `@{ 내용 }`사이에 입력
- 타임리프 에서는 문자열과 자바 객체의 값을 연결할 때 `| 내용 |` 감싸줘야함
- `URL`에 변화하는 값을 넣을 경우 컨트롤러에 메서드 변수에 `@PathVariable("변화 값")` 으로 정의
- 메서드위에 `@GetMappting(value="URL{변화 값}")` 올 애너테이션 붙이기

#### URL Prefix 
- 메서드 위에 `@RequestMapping("/앞쪽의 URL명")`

#### Post 매핑
- 메서드 위에 `@PostMapping("URL")` 작성
- 메서드 변수에 `@RequestParam(value="name 속성 명")`

#### 템플릿 스타일 적용
- `src/main/resources` 디렉토리에 `static` 폴더에 `style.css` 파일 생성
- 적용할 `html` 파일
```
<link rel="stylesheet" type="text/css" th:href="@{/style.css}">
링크 테그로 연결
```
#### 템플릿 상속
- `CSS` 파일 이름이 변경되거나 새로운 `CSS 파일을 추가할 때 마다 모든 템플릿 파일을 일일이 수정을 해야하는 문제점해결을 위한 기능
- 기본 틀이 되는 템플릿을 작성하고 다른 템플릿에서 그 템플릿을 상속해 사용하는 방법
```
ex)
상속 하기
<th:block html 파일 명:fragment="content"></th:block>
th:block 기능 활용

상속 받기
<html `html 파일 명`:decorate="~{html 파일 명}">
<div `html 파일 명 `:fragment="content" class="container my-3">
    <table class="table">
        (... 생략 ...)
    </table>
</div>
상속 하는 html 과 상속 받는 html 간의 fragment가 동일해야 함
```
#### 폼 활용
- 폼(`form`) 클래스 웹 프로그램을 개발하는 주요 구성 요소, 웹 프로그램에서 사용자가 입력한 데이터를 검증하는데 사용
- `Spring boot Validation` 라이브러리 설치 -> `build.gradle` 수정
- 패키지에 `~~~Form.java` 파일 생성, 내용 작성
- 폼 클래스는 입력값 검증 과 입력 항목을 바인딩할 때도 사용
- 컨트롤러에 전송
  1. 메서드 변수 `@Valid ~~~Form 메서드`
