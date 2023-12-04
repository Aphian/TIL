## Django_03
- `models.py` 에 DB에 필요한 `column` 의 개수가 증가 할 수록 `html` 파일에 생성해야할 `input` 태그가 많아지고 `views.py`에 그 데이터를 받고 DB에 저장할 때 필요한 코드 수가 늘어남.
- --> `django`에서 지원하는 `form` 클래스를 활용하면 보다 효율적으로 작업이 가능.
- `form` 클래스를 이용하면 기본적인 유효성 검사 기능을 이용할 수 있음

### Django Form
ex)
```
class 클래스명(forms.ModelForm):
    name = forms.CharField(min_lengh=2, max_lengh=20)
    ...
    -->> 최소한의 유효성 검사를 위한 제한

    class Meta:
        model = [models.py에 정의한 class 명]
        fields = '__all__' --> `models.py` 에 정의한 필드를 모두 사용한다 라는 의미
```

### Django views.py
- `form` 클래스 활용은 C(create), U(update) 부분에서 사용함.
- 사용자가 데이터를 보낼 때 `GET / POST` 방식으로 전송이 됨
- 분기를 나눠서 하나의 함수에 2가지의 기능을 구현이 가능함.
- `method == GET` 
  1. URL => enter
  2. a 태그 => Click
  3. redirect
- `method == POST` : `form` 태그에서 `method = POST`
- C(create)
  1. `method = GET` : 입력이 필요한 칸이 빈 `form` 으로 사용자에게 보여줌
   - `form` 클래스로 정의된 부분을 인스턴스화 시키면 `input` 태그와 매핑되서 `html`에 많은 `column` 을 하나씩 구현할 필요가 없음 -> `{{ form.as_p}}`
  2. `method = POST` : `인스턴스명 : [Form 클래스명](request.POST)` 데이터를 가져옴
   - `인스턴스명.is_valid()` : `form` 클래스 이용하여 정의한 클래스에서 정의된 내용으로 유효성 검사 -> `True` 가 된다면 저장하고 HTML 이동
- 2가지의 분기를 하나로 구현이 되는 이유 : 함수 안에서 `return` 함수를 만나면 바로 종료되는 특성을 이용하여 구현함.
- U(update)
  1. 기존에 있는 데이터를 그대로 보여주고 싶을 때 `(instance=[인스턴스명])` 으로 구현 가능.
- create 구현 부분과 유사함

### form 태그
- `form` 태그에서 `action` 특성이 비어 있을 경우 자기자신에 요청
- --> URL로 이동이 되기 때문에 처음엔 `GET` 방식으로 이동
- --> `form` 에 `button` 이용하여 `POST` 방식으로 요청을 하면 분기 나눈 부분에 조건에 맞게 응답함.
