## Django Model
- SQL(Structured Query Language) : DB 시스템에서 자료를 처리하는 용도로 쓰이는 언어
- RDBMS(Relational DataBase Management System) : 데이터를 행(Row)와 열(Column)의 형태러 저장한다. 대부분 활용함.
- ORM(Object Relational Mapping) : 객체 관계적 매핑, 객체와 데이터베시으의 데이터를 자동으로 매핑(연결) 해주는 것
---
### Django Model 시작
- `pip install django-extensions` : `lib` 설치가 필요함
- `INSTALLED_APPS []` 에 `django_extensions` 추가
---
### Model.py 
- 데이터를 저장할 `table` 생성 해줘야함
- `class [객체명]` : 객체 클래스 생성
  1. 객체에 필요한 스키마(Column) 변수 방식과 자료형 정의
  ```
  ex)
        class Student(models.Model):
                name = models.CharField(max_length=10)
                age = models.IntegerField()
                ...
                ...

  ```
- python 에서 정의 해준 후 DB에 생성을 해줘야함.
  1. `terminal` -> `python manage.py shell_plus` -> `python manage.py makemigrations`
- 클래스로 부터 실제 DB 테이블 접근한다는 명령 실행
  1. `python manage.py migrate orm_test`
- `terminal` 에서 DB에 접근 CRUD 작업 현황을 보기 위한 명렁어
  1. `python manage.py shell_plus --print-sql`