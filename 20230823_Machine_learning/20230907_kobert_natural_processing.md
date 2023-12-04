### Kobert 이용한 자연어 처리
- `aws python3` 에서 진행

#### Bert의 특징
- 전이 학습 모델
  - 구글의 `Devlin(2018)`이 제안한 `BERT`는 사전 학습된 대용량의 레이블링 되지 않는 데이터를 이용하여 언어 모델을 학습하고 이를 토대로 특정 작업 (문서 분류, 질의응답, 번역 등)을 위한 신경망을 추가하는 전이 학습 방법
- `BERT` 모델은 기본적으로 대량의 단어 임베딩 등에 대해 사전 학습이 되어 있는 모델을 제공하기 때문에 상대적으로 적은 자원만으로도 충분히 자연어 처리의 여러 일을 수행

#### Bert 구조
- `Token Embedding` : `Word piece` 임베딩 방식
  - `Word piece` 임베딩 : 자주 등장하면서 가장 긴 길이의 `sub-word`을 하나의 단위로 만드는 것
  - 자주 등장하는 단어에만 포커스가 주어져서 자주 등장하지 않는 단어를 무시해 의미 전달이 많이 저하되었던 문제를 해결
  - 입력받은 모든 문장의 시작으로 [CLS] 토큰(special classification token)이 주어지며 이 [CLS] 토큰은 모델의 전체 계층을 다 거친 후 토큰 시퀀스의 결합된 의미
  - 문장의 구분을 위해 문장의 끝에 [SEP] 토큰을 사용
- `Segment Embedding` : 토큰으로 나누어진 단어들을 다시 하나의 문장으로 만들고 첫 번째 [SEP] 토큰까지는 0으로 그 이후 [SEP] 토큰까지는 1 값으로 마스크를 만들어 각 문장들을 구분
- `Position Embedding` : 토큰의 순서를 인코딩

#### BERT의 Pre-traing / Fine-Tuning
- `Pre-traing` : 거대 `Encoder`가 입력 문장들을 임베딩하여 언어를 모델링 과정
- `Fine-tuning` : 여러 잔여어 처리 업무를 수행하는 과정

#### Bert 사용 순서
1. `bert tokenizer` 설치
2. 필요 패키지 설치
3. `Data` 준비
   - 학습 `data`와 학습 `label`을 따로 분리해서 준비해야 함
4. `bert tokenizer` 이용 `bert dataset` 생성
5. `Pre-train`된 `bert` 모델 이용해서 모델 생성
6. 모델 컴파일
7. 모델 학습

#### GluonNLP Toolkit
- NLP(자연어처리) 작업을 위한 효율적인 데이터 파이프라인을 구축하기 위한 도구를 제공하는 패키지
- `gluonnlp.data.TSVDataset()` : 파일을 텍스트 필드를 읽는 공통 탭 구분 텍스트 데이터 세트로 생성해주는 함수
