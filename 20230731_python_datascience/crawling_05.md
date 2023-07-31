### 포털사이트 크롤링(ex. 쇼핑몰)
- `SSL CertiVerification Error`
  - 보안연결 시도
  - `import ssl` 패키지를 사용
  - `ssl 연결 context()`를 생성해서 인수로 전달해야 함
  - `context = ssl._create_unverified_context()`

#### 쇼핑몰
- 제품명 / 가격 / 세일가격 
- 페이징 기능을 가지는 페이지 다르게 접근해서 모든 제품 크롤링
- 기능별 함수 세분화
  - 요청 및 파싱
  - 전체 정보 추출
  - 각 제품의 정보 추출

#### DB 저장
- `DBMS` 각각에 맞는 패키지 설치
- `Maria DB` -> `!pip install pymysql`
- `pymysql` 사용법
  1. `DBMS` 연결
  2. 1번에서 연결한 정보(객체)를 이용해서 `cursor` 객체
  3. `sql 문` 작성
  4. `cursor` 객체를 이용해서 작성한 `sql` 문 실행
  5. 검색 관련 `sql` 문 일 경우
     1. `cursor.fetchXXX()` 를 이용해서 데이터 반환
     2. `cursor.fetchall()` : 반환된 모든 데이터 한번에 전달
     3. `cursor.fetchone()` : 반환된 데이터 하나씩 받기