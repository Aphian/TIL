### 이상치 탐색 및 제거
- `IQR Rule`
- `IQR rule`을 위배하지 않는 `bool list` 계산 `(True: 이상치 X, False: 이상치 O)`
- 이상치의 조건 : `Q3 + 1.5 * IQR` 초과하거나 `Q1 - 1.5 * IQR` 미만이거나
- `Q3 + 1.5 * IQR > val_list` 는 val_list가 상위 이상치 이하면 True
- `Q1 - 1.5 * IQR < val_list` 는 vla_list가 하위 이상치 이상이면 True

**전체 컬럼에서 이상치가 있는 컬럼이 1개라도 있는 관측치(행) 모두 제거**
- 전체데이터중 한개 컬럼이라도 이상치가 있으면 제거하므로 데이터의 수가 많이 감소될 수 있음