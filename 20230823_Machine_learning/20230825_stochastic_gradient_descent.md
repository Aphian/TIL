### 확률적 경사 하강법
- 훈련데이터가 한번에 준비되지 않고 조금씩 준비되는 것의 문제
- 훈련한 모델을 버리지 않고 새로운 데이터에 대해서만 조금씩 더 훈련하는 방법 찾기
- 점진적 학습 / 온라인 학습
- 알고리즘 : 확률적 경사 하강 법
- 경사하강법 : 조금씩 내려오는 과정이 경사하강법모델을 훈련하는 것
- 훈련세트의 전체 세트를 사용하지 않고 딱 하나의 샘플을 훈련세트에서 랜덤하게 골라 가장 가파른 길 찾기
- 훈련세트에서 하나의 샘플을 고르는 것이 확률적경사하강법
- 모든 훈련세트를 다 사용할 때 까지 반복 최저점에 도달하지 못했다면 다시 처음부터 복구
- 이런 한번의 반복 **에보크** 라고함
- 손실함수 : 샘플 하나에 대한 손실을 정의
- 비용함수 : 모든 샘플에 대한 손실함수의 합

#### 손실함수
- 머신러닝 알고리즘이 얼마나 엉터리인지를 측정하는 값, 값이 작을수록 성능이 좋은 알고리즘

**확률적 경사하강법을 사용한 모델은 에포크횟수에 따라 과소적합이나 과대적합이 될 수 있음**