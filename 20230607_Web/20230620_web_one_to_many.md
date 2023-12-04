## djanog_DB
- `django` 에서 DB 테이블을 생성 시 `models.py`를 통해 `column` 을 정의 하고 셋팅한다.
- 테이블에 `column`을 추가 하려면 `default`가 없으면 추가를 하지 못함.
  - --> DB에는 `NULL` 값이 있고 기본으로 `column` 정의 시 `NULL=False` 되어 있기 때문에 못함
  - 추가 방법
    1. `column` 정의시 필드타입(`null=True`) 설정 좋은 방법은 아님.
    2. `column` 정의시 필드타입(`default=[ ]`)로 정의
  - `makemigration APP 명` 실행 `column` 추가가 됨.
---
### ModelForm 활용
- `ModelForm`을 활용하면 내부적으로 `HTML`에 `input` 태그를 자동으로 매핑 해줌
- 자동으로 구현이 되기 때문에 속성을 부여하기 위해 필드명(`widget = form.필드명(attr={ [속성명] })`) 으로 가능함.
---
### 선언형 / 명령형 프로그래밍
- 명령형 프로그래밍 : 프로그래밍의 상태와 상태를 변경시키는 구문의 관점(`어떻게[HOW]`의 관점)
- 선언형 프로그래밍 : 어떤 방법으로 해야하는지를 나타내기 보단 `무엇[WHAT]` 관점으로 구현하는 언어
---
### HTML[Templates] 분리
- 엄청 많은 코드 줄을 관리 하는것 보다 `html`을 나눠서 관리하는 것이 보다 효율적임.
- `django_extensions` 에 구현되어 있는 `include` 이용 ex) `{% include '[분리한. html]' %}` 
---
### 요청 방식에 따른 에러 처리
- `from django.views.decorators.http import require_safe, require_POST, require_http_methods` --> 요청 방식에 맞는 함수 호출
- `require_safe` : `GET`, `HEAD` 요청에만 응답
- `require_POST` : `POST` 요청에만 응답
---
### instance 명.objects.get()
- `from django.shortcuts import get_object_or_404` -> `import` 필요함
- `get` 대신 `get_object_or_404`을 사용하여 에러 처리
---
### 1 대 N 의 관계 데이터
- `FK(ForeignKey)` 를 정의 하면서 테이블을 생성
```
    컬럼명 = models.ForeignKey([외래키 받을 테이블명], on_delete=models.CASCADE[DB 특성으로 인한 설정])
    테이블 생성시 자동으로 컬럼명_id 생성되고 상속받은 테이블의 기본키(PK)가 들어옴
```
- 자식 인스턴스.부모 인스턴스 --> 객체를 가져올 수 있음
- 자식 인스턴스.부모 인스턴스.컬럼명 -> 객체의 값을 가져올 수 있음
- 부모 인스턴스.자식 테이블_set.all() -> 부모 객체에서 자식 객체를 가져오는 용어
- --> []_set.all() 명령어가 내부적으로 자동 생성됨.
- ex)
```
    [부모]
    a1 = Article.objects.create(title='저녁메뉴', content='추천')

    [자식]
    c2 = Comment.objects.create(article=a1, content='샐러드')
    c3 = Comment.objects.create(article=a1, content='떡볶이')
    
    c2.article
    c2.article.title
    a1.comment_set.all()
```
