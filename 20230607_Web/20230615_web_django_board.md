## Django Board
- `APP[기능]` 폴더 생성
- `master` 에 `settitngs.py` ->  `INSTALLED_APPS =[]` 에 추가
- `master` 에 `urls.py` -> `urlpatterns = []`에 경로 추가
- `APP` 폴더에 `models.py` 기능에 필요한 DB 생성 -> `column` 과 자료형
- `APP` 폴더 `urls.py`에 경로 및 함수 호출
- `APP` 폴더 `views.py` 기능에 맞는 함수 구현

### Django CRUD
- `C(create)` : DB에 사용자가 작성한 데이터를 저장하는 행위, 사용자 작성 `HTML` 호출하는 `views`에서 함수 정의 -> 작성한 `HTML` 을 DB 에 저장하는 함수 호출 해주는 2개의 `cycle` 필요
- `R(Read)` : 전체 조회 - DB 내용을 전부 조회 / 단일 조회 - `pk`를 `URL`에 추가해서 DB에 내용 조회
- `U(Update)` : `pk`를 가지고 단일 조회한 내용을 보여주는 `HTML` 필요/ `HTML` 에서 클릭 행위를 할 때 DB에 저장하는 행위가 필요 -> 2개의 `cycle` 필요
- `D(Delete)` : `pk`를 URL에 가지고 단일 조회 후 `삭제` 버튼을 클릭시 `delete` 함수 호출