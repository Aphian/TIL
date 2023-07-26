### Matplotlib_02
- `subplot()` : 하나의 `figure`안에 여러개의 `plot`을 배열 형태로 표시
- `plt.tight_layout(pad=)` : 플롯간 간격을 설정
- 범례 표시 : `plt.plot(x, y, label='a)` / `plt.legend(loc=, ncol=)`
  1. `label` : 범례 이름
  2. `loc` : 범례 위치
  3. `ncol` : 추가하면 가로로 입력
- `plt.bar(x, y, color[색상]=, alpha[막대 밝기]=)` : 세로 막대 그래프
- `plt.barh(x, y, color=, alpha=)` : 가로 막대 그래프
- 수치값을 갖고 있는 열이 2개 이상이면 묶음 막대 그래프를 그린다.
- `plt.scatter()` : 버블차트 / 그룹별 시각화 할 경우 사용
- `plt.hist()` : 특정구간의 범위로 나누고 범위 내의 데이터의 빈도를 세서 데이터의 빈도를 확인할 때 사용
- `plt.boxplot()` : 위/ 아래 가로선안에 데이터들은 사용가능 데이터(정상데이터) / 밖에 데이터 들은 이상데이터 라고 함
  1. 이상데이터의 유/무를 파악하는데 용이함.
- `plt.pie()` : 카테고리별 값의 상대적인 비교를 할 때 주로 사용하는 차트