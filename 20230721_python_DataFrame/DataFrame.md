### DataFrame
- `List`이용 `DataFrame` 생성
  1. 각 `List`가 한 행으로 구성됨
  2. `List` 요소의 개수가 다를 경우 `None` 값이 할당됨
- `dict` 이용 `DataFrame` 생성
  1. `key`값이 `column`(열) 이름이 됨
- `Series`로 생성 시 `Series`의 `index`가 `column` 값이 됨
- `csv` 데이터 활용 : `pandas.read_csv('경로명/파일명')` 함수 사용
   - `pandas.read_csv` 함수 파라미터
     - `seq` : 구분자
     - `index_col` : `index`로 사용할 `column` 설정
     - `usecols` - 실제로 `dataframe`에 로딩할 `columns`만 설정
- `DataFrame`의 `data` 파악
  1. `shape` : 데이터 크기
  2. `describe` 함수 : 숫자형 데이터의 통계치
  3. `info` : 데이터 타입 / 각 아이템의 개수 
- 행과 열을 바꾸는 전치 기능 있음 (`df명`.T)
- `DataFrame` 내용 변경 : 열추가. 열삭제, 내용 갱신
- `DataFrame` 인덱싱 : df명['컬럼명']
  1. 열인덱싱을 우선적으로 함
  2. 라벨(`column`)을 `key`값으로 생각하고 인덱싱
  3. 라벨을 하나를 넣으면 `Series`로 반환
  4. 리스트로 넣으면 부분적 `DataFrame`으로 반환
  5. 컬럼명이 문자열일 경우 위치인덱스를 사용할수 없음.
  6. 행 단위 인덱싱을 하고자 한다면 인덱서라는 특수 기능 사용 or 슬라이싱으로 추출

#### Index(인덱스) / Column(컬럼)
- `index` : 각 아이템을 특정할 수 있는 고유의 값 저장
- 복잡할 경우 멀티 인덱스 표현 가능
- `column` : 각각의 특성 / 멀티 컬럼 가능





#### 