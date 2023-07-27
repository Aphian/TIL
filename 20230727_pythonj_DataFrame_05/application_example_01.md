### Example_01
#### 서대문구 치킨집 분포도
- 한글 `encoding` 방식이 두 가지 `['utf-8','cp949' ]`가 있음
- `pandas` 패키지에 있는 기능으로 파일을 불어 올 경우 `encoding` 요소에 방식을 추가해줘야 `Error`가 안난다.
- `문자열.contanins(문자열1)` : 문자열 안에 문자열1의 포함 여부
- `nan` 데이터가 있을경우 에러가 발생하므로 `nan=False` 요소 추가하면서 작업
- `Series` 원소가 집합(list등)안의 데이터 1개와 일치하면 True를 반환해주는 함수 : `시리즈.isin([데이터1, 데이터2, ...])`


#### treemap 그래프
- `heatmap`과 비슷하게 `data`의 크기를 색상으로 규정
- `heatmap` : 동일한 크기조각에 색상으로 분류
- `treemap` : 사각형 내부 조각의 크기를 이용해 `data` 크기 규정
- `install squarify` 패키지 설치