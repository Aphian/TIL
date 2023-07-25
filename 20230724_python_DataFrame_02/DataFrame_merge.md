### DataFrame Merge [데이터프레임 병합]
- `pandas`는 2개 이상의 `dataframe`을 하나로 합치는 `merge()`, `concate()` 지원
---
#### Merge 명령어
- `merge` 명령 사용 병합
  1. 공통 열이나 인덱스 기준으로 병합
  2. 기준되는 열 데이터를 `key`라고 부름
  3. `df.merge(df명, df명2)` : 두 `df` 병합
  4. 기본은 `inner join` : 양쪽에 동일하게 존재하는 키만 표시
- 병합 방식
  1. `inner join` : 양쪽 `df`에서 모두 키가 존재하는 `data`만 표시
  2. `outer join` : 키가 존재하기만 하면 `data`로 표시
  3. `how=inner / outer`
  4. `how=left` : 왼쪽 df에 있는 모든 키의 데이터는 표시
  5. `how=right` : 오른쪽 df 에 있는 모든 키의 데이터는 표시
- key 두 데이터 프레임에서 이름이 같은 열은 모두 키가 될 수 있다.
- 이름이 같아도 키가되면 안되는 열이 있으면 `on=기준열 이름` 인수로 기준열을 명시해야 한다.
- 일반 데이터 열이 아닌 인덱스를 기준으로 `merge` 할수 있음
  - `left_index`/ `right_index` `= True` 설정을 하게 됨
--- 
#### concat 명령어
- 기준열 없이 데이터를 연결
- 기본은 위 아래로 데이터 행 결합(row bind) axis 속성을 1로 설정하면 열 결합(column bind)을 수행한다 
- 단순히 두 시리즈나 데이터프레임을 연결하기 때문에 인덱스 값이 중복될 수 있다.
- 내용은 상관 없이 인덱스가 같냐 다르냐만 다룬다
- `axis` `0 / 1` : `default` `0` 위+아래 합치기(행 병합) , `1` : 왼쪽 + 오른쪽 합치기(열 병합), `join='outer`
- `keys=` 인덱스 생성
- `ignore_index = True` : 기존 인덱스 제거 후 제로베이스 인덱스 설정