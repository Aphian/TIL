### 인공신경망
- 확률적 경사 하강법을 사용하는 로지스틱 회귀와 비슷함
- `z값`(결정값)을 계산하는 단위 `뉴런(유닛)`이라고 함
  - 이 값을 바탕으로 클래스를 예측하기 때문에 출력층`(XX.predict)` 이라고도함
- 각 픽셀을 입력층 이라고 부름
  - 픽셀 자체이고 특별한 계산을 수행하지 않는다.`(XX.fit)`
- `tensorflow`와 `keras`
  - `keras`는 `tensorflow`를 사용하기 편하게 해주는 고수준 API 이다
  - 딥러닝 라이브러리는 `GPU` 사용이 가능
- 딥러닝은 검증 데이터를 따로 덜어내어 사용
- 밀집층 : 출력층과 입력층과의 연결선이 빽빽한 층을 의미함

#### Keras 모델
- 밀집층 생성을 위한 모델`Dense()` 클래스 사용
- 밀집층 생성 : `Sequential 클래스` 이용 / 구성정보를 담고 있는 `dense 클래스` 객체를 파라미터로 전달

#### 분류
- 훈련전 설정 단계
  - `MODEL.compile(loss=손실함수,metrics=평가방법)`
  - `crossentropy` 다중분류에는 원-핫 인코딩 형태 변환 필요
  - `sparse_categorical_crossentropy` : 정수 타겟값을 원-핫 인코딩방법을 안하는 방법

**텐서플로와 같은 딥러닝 라이브러리는 인공신경망을 만들고 훈련할 때 랜덤하게 동작하는 특성이 있어 결과가 다 다를 수 있음**