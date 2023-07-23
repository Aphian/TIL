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

#### 인덱서(loc / iloc)
- `loc` : 라벨값 기반의 2차원 인덱싱
- `iloc` : 순서를 나타내는 정수 기반의 2차원 인덱싱
- `pandas` 패키지는 [행번호, 열번호] 인덱싱이 불가능
  1. `iloc` 속성을 사용하면 가능하게됨 
- `loc` 인덱서 : 행 우선 인덱서 -> `df명.loc[행인덱싱 값]`
- `value_counts()` : 원소들을 분류하여 갯수를 세는 함수
- 인덱스 데이터(index name, column name)
- 인덱스 데이터 슬라이스
- 같은 행 인덱스를 갖는 `boolean Series` (행 인덱싱인 경우)
  - 조건으로 추출 가능
- 값을 반환하는 함수를 이용해서 인덱싱 가능
- 행 인덱스 값이 수치 인덱스여도 [초기인덱스 : 마지막인덱스]
- 인덱스 값으로 슬라이싱, 위차값으로 하지 않음 / 라발로 인덱싱함
```
# df의 a 행의 모든 열 추출
df.loc['a']     # a 행의 모든 열 추출, 시리즈
df.loc[['a']]   # a 행의 모든 열 추출,  DataFrame 반환
df.loc['a', :]  # a 행의 모든 열 추출, 시리즈
df.loc[['a'], :]   # a 행의 모든 열 추출,  DataFrame 반환

```
- `iloc` 
- 라벨(name)이 아닌 위치를 나타내는 정수 인덱스만 받는다.
- 위치 정수값은 0부터 시작
- 데이터프레임.iloc[행,열]
--- 
#### DataFrame 데이터 다루기
- 행 추가 : `pandas`의 `DataFrame` 인덱서(loc) 사용 --> 원본에 적용
- `pd.concat()` 사용 - 추가하고자 하는 행 data를 새로 생성 후 결합 --> 반환만 해줌
- `df명.drop()` : 행/열 삭제 --> 기본으로는 원본에 반여하지 않음. 
  1. 속성 `index=인덱스명` 행 삭제 / `columns=컬럼명` 열 삭제
  2. 함수 내의 `inplace` 속성을 `True` 해주면 원본에 적용
  3. `.drop()`에 `axis` 속성을 `0`으로 하면 행 / `1`로 하면 열 `default axis=0`
- `data` 개수 세기 : `count()` -> `NaN(결측값)` 세지 않는다.
- 시리즈.value_counts()메서드를 사용해 각각의 값이 나온 횟수를 셀 수 있음
- 파라미터 normalize=True 를 사용하면 각 값 및 범주형 데이터의 비율을 계산
- 범주형 데이터 : 관측 별과가 몇개의 범주 또는 항목의 형태로 나타나는 자료