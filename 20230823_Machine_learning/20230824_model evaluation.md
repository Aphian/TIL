### 분류모델 평가
- 머신러닝 프로세스
  - 데이터 가공/ 변환
  - 모델 학습/예측
  - 평가
- 유형
  - 이진 분류 : 결정 클래스 값 종류의 유형에 따라 긍정/부정과 같은 2개의 결과값 분류
  - 멀티 분류 : 여러 개의 결정 클래스 값을 가지는 분류
- 분류 모델 평가지표
  - 범주형
    - 정확도
    - 재현율
    - 정밀도
    - `F1 measure`
    - `G measure`
    - `ROC curve`
    - `AUC`
- 회귀 모델 평가지표
  - 예측 대상이 수치 데이터인 경우
    - `MSE(Mean Square Error)`
    - `RMSE(Root Mean Square Error)`
    - `MAE(Mean Absolute Error)`
    - `MAPE(Mean Absolute Persentage Error)`
    - $R^2$
#### Accuarcy(정확도)
- 실제 데이터와 예측 데이터가 얼마나 같으지를 판단하는 지표
- 직관적으로 모델 예측 성능을 나타내는 평가지표
- **주의 불균형한 레이블 값 분포에서 ML 모델의 성능을 판단할 경우,적합한 지표가 아님**
  - 아무것도 하지 않고 무조건 특정한 결과로 찍어도 데이터가 균일하지 않은 경우 높은 수치가 나타날 수 있음

#### Confusion Matrix (오차행렬 / 혼동행렬)
- 이진 분류의 예측 오류가 얼마인지와 더불어 어떠한 유형의 예측 오류가 발생하고 있는지를 함께 나타내는 지표
- 머신러닝 모델의 예측이 얼마나 잘한 예측인지를 판단하는 데 중요한 기준을 제공
- 오차행렬로부터 우리는 머신러닝 모델의 우수성을 평가하는 여러 지표를 도출할 수 있음
- `confusion_matrix()`

#### 정밀도(Precision)와 재현율(Recall)
- `Positive` 데이터 세트의 예측 성능에 좀 더 초점을 맞춘 평가 지표
- 정밀도 : `TP / (FP + TP)` / `Positive`로 예측한 데이터 중 정답의 비율, 양성 예측도라고도 불림
  - `precision_score()`
- 재현율 : `TP / (FN + TP)` / 정답이 `Positive`인 대상 중에 `Positive`로 정답을 맞춘 비율
  - `recall_score()`
- 가장 좋은 성능 평가는 재현율과 정밀도 모두 높은 수치를 얻는 것 -> 임계값 조절
- `Trade-off` : 어느 한쪽을 강제로 높이면 다른 하나의 수치는 떨어지는데 맞나는 지점
  - `predict_proba()` 메서드 활용
- `Binarizer` 클래스 활용
  - 사이킷런의 Binarizer 클래스 이용해서 분류 결정 임계값을 조절하여 정밀도와 재현율의 성능 수치를 상호 보완적으로 조정 가능
- 정밀도와 재현율이 엇비슷한 분류의 평가에 성능이 좋은 모델이다.
- 임계값에 따른 정밀도-재현률 값 추출
  - `precision_recall_curve()`
- 분류의 종합적인 성능 평가에 사용하기 위해서는 정밀도와 재현율의 수치를 적절하게 조합하는 것이 필요함

#### F1 Score
- 정밀도와 재현율의 조화평균
- 정밀도와 재현율이 어느 한쪽으로 치우치지 않는 수치를 나타낼때 상대적으로 높은 값을 가짐

```
분류 클래스가 이진이고, 불균형 데이터(분포가 정규분포가 아니고 치우쳐져 있는 경우) 일때는
    - 정밀도, 재현율, F1 score까지 같이 보고하고
    - 분석가가 어떤 임계점을 사용할 것인지 데이터에 따라 결정하고 이유가 보고서에 들어가 있어야 함
```