### 자연어 처리(Natural Language Processing : NLP)
- 음성이나 텍스트를 컴퓨터가 인식하고 처리 하는것
- 텍스트 자료를 딥러닝에 그대로 입력할 수 없음.
  - 알고리즘은 수치로 된 데이터만 이해할 뿐 임
  - 텍스트를 정제하는 전처리 과정이 필요함

#### 피처 벡터화
- 텍스트를 특정 의미를 가지는 숫자형 값인 벡터 값으로 변환하는 것
- 텍스트를 단어 단위로 추출해 피처로 할당하고 각 단어의 발생 빈도와 같은 값을 피처에 부여해서 단어 피처의 발생 빈도 값으로 구성된 벡터로 만드는 기법
- 카운트 기반의 벡터화
  - 단어 피처에 단어의 빈수도를 부여하는 것
  - 카운트 값이 높을수록 중요 단어로 인식
  - 단, 언어의 특성상 자주 사용될 수 밖에 없는 단어 까지 높은 값으로 부여됨 보안`(TF-IDF)`
- `TF-IDF(Term Frequency-Inverse Document Frequency)` 기반의 벡터화
  - 개별 문서에서 자주 나타나는 단어에 높은 가중치
  - 모든 문서에서 전박적으로 자주 나타나는 단어에 대해서는 패널티를 주는 방식으로 값 부여
  - 단, 다른 문서에서도 자주 나타난다면 특성상 범용적으로 자주 사용되는 단어일 가능성이 높음.

#### 텍스트 전처리 작업
- 토큰화 : 단어 토큰화 / `from tensorflow.keras.preprocessing.text import Tokenizer()`
- 정제 : 노이즈 데이터 제거
- 정규화 : 표현 방법이 다른 단어들을 통합시켜서 같은 단어로 만듦
- 어간 추출 / 표제어 추출: 하나의 단어를 일반화시켜서 문서 내의 단어 수를 줄이는 작업
- 불용어 제거 : 실제 의미 분석을 하는데의 기여를 하지 못하는 단어 제거
- 정규 표현식 : 특정 규칙이 이쓴 텍스트 데이터를 빠르게 정제
- 정수 인코딩 : 각 단어를 고유한 정수로 맵핑
- 패딩 : 여러 문장의 길이를 임의로 동일하게 맞춰주는 작업
- 원-핫 인코딩 : 문자를 숫자로 변환

#### 단어 임베딩 
- 각 단어를 임의 숫자를 부여하고, 학습을 통해서 유사도를 계산함
  - 문장과 단어와의 관계를 파악해서 유사도를 계산(경사하강법)
- 임베딩층
  - `model.add(Embedding(word_size, 8, input_length=4))`
  - 입력 정수에 대해 밀집 벡터(dense vector)로 맵핑
  - 밀집 벡터는 인공 신경망의 학습 과정에서 가중치가 학습되는 것과 같은 방식으로 훈련
  - 밀집 벡터를 임베딩 벡터라고 함.