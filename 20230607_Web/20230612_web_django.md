## Django
- Django : 보안/ 유지보수가 편리한 웹사이트를 신속하게 개발하는데 도움을 주는 파이썬 웹 프레임워크
---
|Server|vs|Django|
|--|--|--|
| URL | --> | URL |
| Controller | --> | View |
| View | --> | Template |
| Model | --> | Model |
| URL 형식 ( `/url` )| --> | ( `url/` ) 형식 |
- 모듈화 => `file`로 쪼개기
- 폴더 => `package` 생성
---
### Django 시작
- `pip install django` : django 설치
- `django-admin startproject [프로젝트 이름]` : 프로젝트 생성
- `urls.py` : 요청을 맞는 뷰에 전달, `urlpatterns` 맵퍼에 경로들과 맵핑 목록 정의
- `views.py` : 요청을 수신하고 처리, DB 에 접근, HTML 경로 함수 정의
- `models.py` : 파이썬 객체를 동해 데이터를 관리
- `manage.py` : 프로젝트 매니저 (앱 생성 할 때 명령어를 활용, 서버 구동)
- `setting.py` : 프로젝트 설정(편집 하는 파일)
  1. `INSTALLED_APPS` : 기능 추가하는 앱 등록
- `python manage.py startapp [APP 명]` : APP[기능] 추가
- 보통 화면으로 보이는 `HTML` 파일을 `templates` 폴더에 생성 후 매핑 해야함
---
### 불필요한 중복 제거
- `HTML` 파일의 내용 중 중복이 다수 발생할 수 있음.
- 중복된 내용을 하나의 `HTML` 파일로 꺼내서 작성
- `setting.py` 안에 `TEMPLATES []` dic 안에
- --> `DIRS` : `[project 폴더명 / 꺼내놓은 파일이 있는 폴더명]`
- --> 수동으로 `templates` 찾게 해야함
- 공통적으로 사용되는 `HTML` 부위 `{% extends [].html %} ` 불러오기
- 공통적이지 않은 부분을 `{% block %} {% endblock %}` 담아서 적용
---