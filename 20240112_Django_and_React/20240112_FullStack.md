### Django Backend 설정

1. 프로젝트 생성 : `django-adim startproject 프로젝트명`
2. `Model, View, URL`  구현 
   - `model` : 데이터베이스의 테이블
   - `view` : 요청을 처리하고 응답을 반환
   - `URL` : `Django`가 올바른 뷰를 찾기위한 패턴 집합
3. `Django REST Framework` 설정
   - 유연한 툴킷으로 웹 `API` 구축
   - 직렬화, 뷰셋, 라우터, 인증과 권한 기능
   - `pip install djangorestframework`
   - `setting.py` 설정
4. `RESTful API` 설계
   - 애플리케이션의 데이터와 리소스를 나태내는 엔드포인트를 생성
   - `GET`, `POST`, `PUT`, `DELETE` 등 `HTTP` 메서드에 응답하는 작업
   - 직관적이고 예측 가능하게 유지가 중요
5. `CRUD` 작업, 인증, 권한 설정
   - 인증과 권한을 처리하기 위해 인증 클래스와 권한 클래스 사용
   - `API`에 접근할 수 있는 사용자와 그들이 수행할수 있는 작업을 제어
   - 인증 방식, 세션 인증, 일반적인 권한 정책을 제공
6. `API` 테스트와 문서화
   - `rest_framework.test` 라는 테스트 모듈을 제공
   - 다른 개발자들이 `API`를 사용하는 방법을 이해할 수 있도록 문서화
7. 풀 스택 애플리케이션의 프론트엔드 개발환경 설정
   - `Next.js` 사용하여 프로젝트 생성 `npx create-next-app@latest 앱 이름`
8. 재사용 가능한 `React` 컴포넌트 구현
   - 재사용 가능한 `UI` 요소를 만들어 유지 및 업데이트를 쉽게 가능
   - `src` 안에 `components` 디렉토리를 생성하여 컴포넌트 저장
9. `React Hooks` 와 `Context`를 사용한 상태 관리와 사용자 상호 작용
   - 애플리케이션에서 상태 관리와 데이터 공유 쉽게 가능
   - `Context` 는 컴포넌트 트리를 통해 데이터를 전달하는 방법을 제공
     - 사용자 인증 정보나 테마 설정과 전역 데이터를 수동으로 전달하지 않아도 공유 가능