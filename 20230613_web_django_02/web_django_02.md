## Django_02
- 프로젝트 생성
  1. 개인이면 상관 없음. --> 중앙집권적 패키지
  2. 여러명의 프로젝트에 참여 하게 되면 프로젝트에 필요한 pip 파일을 특정한 곳에 설치할 필요가 존재함 --> 의존성 관리 가상환경 (독립환경)
- 가상환경(독립환경)을 생성해줘야할 필요성이 생김.
  1. 폴더 생성
  2. `python -m venv[가상환경 생성 명령어] [가상환경 폴더 이름]` : 보통 폴더 이름을 프로젝트/ venv 사용
  3. `source venv/Scripts/activate` : 독립환경 사용 명렁어
  4. `pip install` : 해당 프로젝트에 사용된 버전 다운로드 해야함
  5. `pip freeze` or `pip list` : 해당 프로젝트에 사용된 버전 목록
  6. `pip freeze > requirements.txt` : 해당 프로젝트에 사용된 버전 목록 txt 문서 작성
     - 문서를 `requirements.txt` 로 하는게 관례 
  7. `pip install -r requirements.txt` : 문서에 있는 버전 다운로드 
  8. `django-admin startproject [프로젝트명] . ` : 그 자리에 `manage.py` / `master APP` 생성
---
### temaplates 폴더 정리
- `django` 에서 `html`을 찾을 때 중복이 있더라도 `INSTALLED_APPS` 리스트에 추가되어 있는 기능들 먼저 추가되어 있는 기능에서 `templates` 폴더 안에 `html` 을 불러옴 
- --> 원하는 `html`이 출력 안되는 경우가 발생함.
- `templates` 폴더 안에 [프로젝트명] 폴더 생성 후 `html` 파일 생성
- 해당 `APP` 안에 `views.py` `render`를 `[폴더]/[파일명].html` 수정
---
### 사용자 입력
- 사용자와 서버간의 데이터가 교환 할 때 2번의 `cycle` 을 가짐
  1. 사용자가 요청 `[request]`
  2. 서버가 `<form>` 또는 `<input>` 태그 포함과 전송방식(`GET, POST`) 가진 `html`을 사용자에게 보내줌 `[response]`
  3. 사용자가 `html` 파일에 작성 후 포함된 전송방식으로 전달 `[request]`
  4. 서버가 데이터를 가지고 알맞는 `html` 사용자에게 응답 `[reponse]`
- 데이터를 전송하면 `view.py`에 `request` 인자안에 내용이 들어있음.
- 전송 방식에 따라 데이터 추출
---
### GET / POST
- `GET` : 사용자가 보내는 데이터가 `URL` 에 그대로 담고 전송 / 주로 검색에만 사용됨
- `POST` : 시스템에 영향을 주는 전송 방식으로 인식을 하여 `URL`에 보여지지 않음, 좀 더 엄격한 처리 방식을 요함.
---