## django_comment
- 1 대 N 의 관계로 표현
- FK(ForeignKey)를 갖는 테이블 보통 N 에 속함

### N 해당 구현
- DB에 테이블을 생성 -> `models.py` `column` 정의 / 외래키에 해당하는 부분 ->
  ex) models.ForeignKey(외래키를 주는 테이블 인스턴스명, 특성(on_delete=models.CASCADE)) 
- 해당 인스턴스의 기본키를 내부적으로 뽑아서 할당함.
- `forms.py` 제한 사항 정의 / `class Meta:` `model` 정의 / `fields` = (넣을 내용, ) --> 튜플로 생성 또는 exclude = (테이블에 제외할 컬럼, )
- `1 대 N` 관계 에서 `N` 에서 `1`에 대응되는 데이터 생성
- `views.py` `1 대 N` 에서 `1`에 해당하는 테이블 조회 / 그에 해당 하는 `N`에 해당하는 부분에 데이터를 생성해야함
- DB에 변화가 생기므로 `POST`로 전송
- `인스턴스명.save()` 여기서 외래키를 사용자가 아닌 `1`에 해당하는 기본키를 수동으로 넣어줘야함
  1. 생성 `인스턴스명 = 클래스명(request.POST)`, 기존 `create` 부분과 유사함
  2. 유효성 검사
  3. `N`에 해당하는 인스턴스명 = `N` 해당 `클래스.save(commit=False)` : DB에 넣기 전에 메모리에 임시저장 / save()는 리턴값이 있음
  4. `N`에 해당 인스턴스.넣을 `column` = `1` 해당 인스턴스
  5. `N` 해당 인스턴스.save()
- `delete` : `1`의 해당하는 데이터 조회 -> `N` 에 해당하는 데이터 조회 후 삭제 `순서 유의` / 키워드 인자로 설정시 상관 없음.
---
### django SignUp
---
#### models.py
- `django` 내부적으로 회원가입에 대한 부분이 구현되어 있음.
- `django` 에 구현되어 있는 `AbstractUser` 클래스 상속을 받아 생성 / 이외으 컬럼을 추가 하기에 용이함
- `settings.py` 안에 `AUTH_USER_MODEL = APP 명.클래스` 정의 -> 개발자가 생성한 `User` `model`을 `django` 가 인식
- `default : AUTH_USER_MODEL = 'auth.user'`
- 사용자에게 선택을 할 수 있도록 하는 `form`을 구현 가능 ex) `choices=[사용자정의 리스트]`
---
#### forms.py
- `django` 내에 있는 `UserCreationForm`을 상속 받아 `forms` 생성
- `get_user_model` 상속 받아 `get_user_model()` 함수를 이용하여 `settings.py` 에서의 `AUTH_USER_MODEL` 정의한 내용을 인식 

#### admin.py
- `django` 내에서 자동으로 생성되는 관리자 관련 파일
- `admin` 계정은 터미널에서만 생성 가능 : `python manage.py createsuperuser` 명령어

#### django 내부적으로 pw 저장 방식
- `django` 내부에 구현되어 있는 `user model`에서 비밀번호를 강하게 유효성을 검사함
- `sha256`이라는 해쉬암호화를 통해서 DB 에 저장