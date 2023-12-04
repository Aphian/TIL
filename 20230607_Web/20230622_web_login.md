## django login
- HTTP : 무상태 프로토콜 --> 서버에 session 상태가 없다는 것을 의미
- 세션 정보를 server에 저장하지 않음 / 상태에 무관한 응답
- `cookie` : 브라우저에 저장하는 것, 사용자의 편의성, 모든 요청에는 `cookie`가 있음
- `session` : 쿠키로 노출되면 안되는 내용이 필요에 따라 DB에 저장
- 서버가 기억하는것이 아니라 `cookie/session`을 보고 `login` 한다 라고 표현함
- `logout` -> 필요에 따라 DB에 저장한 `session`의 `key` 값을 삭제하는 행위
---
### login
- `AuthenticationForm` import 하여 사용함 --> `django` 내부적으로 인증해주는 `form`
- `POST` 오면 AuthenticationForm 값을 받음
  1. `AuthenticationForm(request[기본], request.POST[받은 값])`
  2. or `AuthenticationForm(data=request.POST)`
- 유효성 검사([].is_valid())
  1. 객체명 = `AuthenticationForm`의 `인스턴스.get_user()`
  2. `login(request, user)` --> `cookie / session` 세팅
  3. `django` 내부에 있는 `login()`를 실행
  4. 함수명을 다르게 해줘도 되나 별칭을 이용하여 사용하는 것을 권장
     - ex) `import login as auth_login, logout as auth_logout`
---
### logout
- `auth_logout(request)`
- 어느 전송방식으로든 상관없음
---
### 1 대 N 에서 N 부분 모델링
- `User` 클래스를 사용할 경우.
- `from django.conf import settings` 필요함
  1. 모델간 관계설정시에는 `settings.AUTH_USER_MODEL` 사용
  2. 그 외 (form 생성등) 에는 `get_user_model()` 함수 사용
---
### login / logout 유무에 따라 views.py 구현
- settings.py -> TEMPLATES = []
- `views.py` 에서 `ContextList` 에 값을 안담고 보내도 `HTML` 에서 가져올수 있는 데이터 
- `request` 에 `user` 에 대한 정보를 바로 가져올수 있어 `user.is_authenticated`에 값에 따른 로그인을 확인 가능하다.
- 로그인에 유무에 따른 사용자에게 보여질 `html`이 다르게 구현 가능
- `from django.contrib.auth.decorators import login_required`
  1. 개발자가 로그인이 필요한 부분이라 생각되는 `views.py` 에 구현한 함수에 `decorators` 를 해서 보다 단단한 느낌의 서비스 구현 `@login_required`
  2. 로그인이 안되있는데 `@login_required`가 설정되어 있는 함수를 실행하게 되면 `django` 내부적으로 개발자가 구현한 `AUTH_USER_MODEL` 에 있는 `login form` 으로 `redirect` 시킴
  3. 위의 상황에 이동시 `url` 에 딕셔너리 안의 `next` key 값에 `value`값이 저장되어 있어 로그인 후 `decorators` 가 설정되어 있는 부분으로 이동이 가능하다.
  ```
  ex)
   return redirect(request.GET.get('next') or 'home')
  ```
- 사용자가 입력하지 않은 부분을 저장을 해줘야하기 떄문에 수동으로 넣는 작업 필요
  ``` 
  ex)
    article = form.save(commit=False)
    article.user = request.user
    article.save()
  ```
  ### login 유무에 따른 html 구현
  - `html` 내에서 바로 가져올수 있는 `user` 와 `views.py` 에서 `ContextList` 에서 받아온 데이터를 비교하면서 `DTL` 을 이용하여 로그인 유무 / 다른 계정 로그인 에 따른 `HTML`이 구현이 가능하다.