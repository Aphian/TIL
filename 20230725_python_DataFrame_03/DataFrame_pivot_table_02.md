### DataFrame_pivot_table_02
- ex.
```
# 선실 등급별로 숙박객의 성별 평균 나이
df1 = pd.pivot_table(df,             # df 피버할 데이터
                     index='class',  # 행 인덱스
                     columns='sex',  # 컬럼
                     values='age',   # 계산열/요약열/분석열
                     aggfunc='mean'  # 데이터 집계 함수/요약함수
                    )
df1
```
- `count()`는 `NaN` 을 세지 않음.
- 각 요소에 `list`가 들어갈수 있음.
```
pdf1 = pd.pivot_table(df,# 피벗할 데이터 프레임
                      index = 'class', # 행 인덱스로 사용
                      columns = 'sex', # 컬럼으로 사용
                      values=['age', 'fare'],# 계산데이터로 사용할 열
                      aggfunc='mean'# 데이터 집계함수
                     )
pdf1
```
---
#### 그룹 분석
- 피봇데이블과 달리 키에 의해서 결정되는 데이터가 여러개가 있을 경우 미리 지정한 연산을 통해 그룹테이터의 대표값을 계산 하는것
- `pandas`의 `groupby()` 메소드 사용
- 데이트럴 그룹 별로 분류하는 역살
- 인수는 열 또는 열의 리스트 / 행 인덱스
- `GroupBy` 클래스 객체로 반환 / 연산 메서드
  1. `size`, `count` : 그룹 데이터의 개수
  2. `mean`, `median`, `min`, `max` : 그룹 데이터의 평균, 중앙값, 최소, 최대
  3. `sun`, `prod`, `std`, `var`, `quantile` : 합계, 곱 표준편차, 분산, 사분위수
  4. `first`, `last` : 첫번째 데이터 / 마지막 데이터
  5. `agg`, `aggregate` : 함수를 만들고 `agg` 로 전달 후 연산 / 그룹연산을 동시해 하고자 하는 경우 문자열 리스트로 전달
  6. `describe` : 하나의 그룹 대표값이 아니라 여러개의 값을 데이터 프레임으로 반환
  7. `apply` : 데이트프레임으로 반환하고 그룹 연산이 없는 경우에도 사용
- `apply` 가 좀더 유연하고 기능정으로 폭 넓어서 주로 사용함. / `agg / aggregate` 보다