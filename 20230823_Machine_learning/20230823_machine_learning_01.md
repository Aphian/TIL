### 머신러닝(Machine Learing / 기계학습)
- 컴퓨터 프로그램이 데이터와 처리 경험을 이용한 학습을 통해 정보처리 능력을 향상시키는 것
- 자율 주행 자동차, 필기체 문자 인식
---
#### 머신러닝 알고리즘
- 확률적 모델링
    - 통계학 이론을 분석
    - 로지스틱 회귀
- 신경망
- 커널 방법 : 분류 알고리즘의 한 종류
- 결정 트리 : 랜덤 포레스트, 그래디언트 부스팅

|특성|머신러닝|전통적 방식|
|---|---|---|
|조정|모델 코드 활용|많은 수동 조정과 규칙 필요|
|유지보수|쉬움|어려움
|복잡한 문제|해결 가능|어려움|
- 분류
    - 지도 학습
    - 비지도 학습
    - 준지도 학습
    - 강화 학습
    - 전이 학습
    - 온라인 학습 : 개별적 소그룹으롤 데이터를 순차적 공급하여 점진적 훈련
    - 배치 학습
        - 점진적 학습 X
        - 모든 데이터를 사용해 학습
        - 오프라인으로 수행
- 지도 학습 : 학습데이터에 입력값(특성)에 대한 출력값(레이블)이 함께 제시
    - 알고리즘 : k-최급접이웃, 선형회귀, 로지스틱 회귀, 서포트 벡터 머신, 의사결정트리, 랜덤 포레스트, 신경망
- 비지도 학습 : 학습 데이터에 레이블이 지정되거나 분류되지 않은 테스트 데이터 학습
    - 알고리즘 : 군집분석, 시각화와 차원축소, 이상치 탐지, 연관규칙

#### 머신러닝의 주요 이슈
- 주요 작업 : 학습 알고리즘을 선택해서 데이터에 훈련시키는것
- 나쁜 데이터
    1. 충분하지 않은 데이터
    2. 대표성 없는 데이터
    3. 낮은 품질의 데이터
    4. 연관성 적은 특성
- 나쁜 알고리즘
    1. 훈련 데이터 과대 적합
    2. 훈련 데이터 과소 적합
- 주요 패키지
    - 머신러닝 패키지
        1. 사이킷런(Scikit-Learn)
    - 배열/선형대수/통계 패키지
        1. NumPy
        2. SciPy
    - 데이터 핸들링
        1. Pandas
    - 시각화
        1. Matplotlib
        2. Seaborn
    - 딥러닝
        1. 텐서플로(Tensorflow)
        2. 케라스(Keras)
