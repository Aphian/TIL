## DataScience
---
### Pandas(판다스)
- `Series`, `DataFrame` 등의 자료구조를 활용한 데이터분석 기능을 제공하는 라이브러리
- `Series` - 1차원 배열
- `DataFrame` - 2차원 배열
- 서로 다른 유형의 데이터를 공통된 포맷으로 정리하는 것
- 행과 열로 이루어지 2차원 `DataFrame`을 처리 할 수 있는 함수 제공
- 실무 : `DataFrame`
---
### Series(시리즈)
- `Pandas`의 기본 객체 중 하나
- `numpy`의 `ndarray`를 기반으로 인덱싱 기능을 추가하여 1차원 배열로 나타냄
- `index` 미 지정 시 `0-based` 인덱스 생성, 명시적 설정 가능
- 데이터가 0개 일 수 있음
- `index` 와 `value` 1:1로 대응
- 딕셔너리와 비슷한 구조
- 생성 : `Pandas` 내장 함수 `Series()` 이용
---
#### Series 생성
- `data` 만드로 생성 가능
- `range()` , `numpy.arrange` 함수 사용 가능
- 결측값 : `NaN` -> `numpy` 모듈 이용 생성
- `Series([원소값], index=[index 값] )` : `index` 명시적 설정
- `index` : 문자열 인덱스 지정 가능
- 문자열 `index` 접근 : `Series` 객체 `.[문자열 index]`
- 인덱스를 범위로 생성하거나 인덱스를 생략하면 `RangeIndex` 객체로 생성
- `index` 접근이 가능할 뿐 할당(`assign`)은 불가능함.
- `index`의 `name` 속성으로 이름 부여 : `Series 객체.index.name = [이름]`
- `Series 객체.name` : `value`에 이름을 부여하여 의미 전달
---
#### Series 인덱싱
- 정수형 인덱스 : 숫자 -> `Series 객체[0]`
- 문자형 인덱스 : 문자 -> `Series 객채['문자열 인덱스']`
- 인덱스 값 여러개를 이용해 접근시 [] 안에 넣는다.
- `Series 객체[1]` : 원소값 반환
- `Series 객체[1:3]` : `Series` 로 반환 -> 연속적인 데이터
- `Series 객체[[1,3]]` : `Series` 로 반환 -> 인덱스가 `1`, `3`의 값을 반환
- 정수형 위치 인덱스를 사용한 슬라이싱
  1. 시리즈[start:stop+1]
- 문자(라벨)인덱스 이용 슬라이싱
  1. 시리즈['시작라벨':'끝라벨'] : 표시된 라벨 범위 모두 추출
- 인덱스를 통한 데이터 업데이트 가능
---
#### Series 연산
- `numpy` 배열처럼 `pandas`의 시리즈도 벡터화 연산 가능
- 벡터화 연산이란 집합적 자료형의 원소 각각을 독립적으로 계산을 진행하는 방법
  1. 단, 연산은 시리즈의 값에만 적용되며 인덱스 값은 변경 불가
- Boolean selection
  - boolean Series가 []와 함께 사용되면 True 값에 해당하는 값만 새로 반환되는 Series객체에 포함됨
  - 다중조건의 경우, &(and), |(or)를 사용하여 연결 가능
- 동일한 인덱스는 연산이 되지만 나머지는 연산처리가 되지 않음 -> `NaN` 반환되서 출력
- `values` 속성 이용 연산시 `Series` 형태가 사라지며 동일한 위치 원소들 끼리 연산출력
- 실질적으로는 라벨을 key로 가지는 딕셔너리 형과 같다고 볼 수 있음
- 딕셔너리 연산자 `in`, `item()`, `for`문 사용 가능
- 딕셔너리로 `Series` 생성 가능 `key`이 `index` , `value`가 원소값(`value`)
- 딕셔너리는 순서를 갖지 않음 / `index` 명시적으로 지정하는게 좋음.
- 인덱싱을 이용하여 갱신(업데이트), 추가, 삭제 가능.
---
#### Series 함수
- `size(속성)` : 개수 반환
- `shape(속성)` : 튜플형태로 `shape`반환
- `unique`: 유일한 값만 `ndarray`로 반환
- `count` : NaN을 제외한 개수를 반환
- `mean`: NaN을 제외한 평균
- `value_counts`: NaN을 제외하고 각 값들의 빈도를 반환
- `date_range` : 날짜 자동 생성
  1. `pd.date_range(start=None, end=None, periods=None, freq='D')`
  2. `start` : 시작날짜, 필수/ `end`= 끝날짜 / `periods` = 날짜 생성기간, 둘 중 하나(`end`, `periods`/ `freq` = 날짜 생성 주기 `dafault` day
---
### DataFrame(데이타프래임)
- 2차원 행렬 데이터에 인덱스를 붙인 것
- 행과 열로 만들어지는 2차원 배열 구조
- 데이프레임의 각 열은 시리즈로 구성되어 있음
- `DataFrame()`함수를 사용해서 생성