### Computer Vision 2
- `CNN 아키텍처`
  1. `AlexNet` : `AlexNet`은 2012년에 개최된 `ILSVRC(ImageNet Large Scale Visual Recognition Challenge)` 대회의 우승을 차지한 컨볼루션 신경망(CNN) 구조
  2. `GoogleNet` : `skip connection`, `Res Dual`
  3. `VGGNet` : VGGNet은 옥스포드 대학의 연구팀 VGG에 의해 개발된 모델로써, 2014년 이미지넷 이미지 인식 대회에서 준우승을 한 모델, `VGG16` : 16 레이어 / `VGG19` : 19 레이어
  4. `ResNet-50` : `ResNet-50`은 50개 계층으로 구성된 컨벌루션 신경망
- `Vision Transformer (VIT)` :  `Image Patch` + `Posision Embedding`
  1. `DeiT` : `Facebook AI Research`에서 개발한 데이터 효율성이 높은 모델, ViT모델과 동일한 아키텍처`(MLP head 제외)`이며, `convolution` 연산 대신 `self-attention` 매커니즘을 사용하여 입력 이미지의 특징을 추출
  2. `DETF (Detection Transformer)` : `Prediction Heads`, 
  3. `Swin Transformer` : 2021년 3월 마이크로소프트`(Microsoft Research Asia)`에서 발표,  이미지의 해상도, 그러니까 픽셀이 늘어나면 늘어날수록 모든 `patch`의 조합에 대해 `self-attention`을 수행하는 것은 불가능해진다는 것
- `CLIP` 멀티 모델 `Text` 와 `Image`
- `ConvNext` : `CNN` 모델 최적화 / 효율성 / 성능
- `Image Bind` :  6가지 각 `modalities`를 하나의 `representation space`에서 표현하는 것이 목표, 서로 엮어`(Jointly)` 학습
- `Zero-shot model` : `semantic information`은 여러 종류가 될 수 있는데, 한 가지 예시를 들면 `data`의 `class`를 `word embedding`으로 사용하는 것

#### Generative Model
- `Stable Diffusion` : 텍스트 및 이미지 프롬프트에서 고유한 실사 이미지를 생성하는 생성형 인공 지능(생성형 AI) 모델
- `Midjourney` : 텍스트를 입력하면 AI가 이미지를 생성해주는`(Text-to-Image)` 모델
- `DALL.E2` : `OpenAI`에서 개발한 생성형 이미지 인공지능, 텍스트를 이미지로 구현할수 있는 모델
- `Discriminative Model` : p(y|x), 판별 모델 또는 분별 모델은 주어진 데이터를 가지고 분류하거나 분류에 쓰일 수 있는 점수를 매기는데 사용되는 통계 모델
- `Generative Model`: p(x), 생성 모델은 분포에 맞는 데이터를 생성해내는 통계 모델
- `Representation Learning` : `Latent Space`, 입력 데이터를 기반으로 `expectation`(기댓값, 기대출력)에 가깝게 만드는 유용한 표현`(representation)`을 학습`(learning)`하는 것
- `Evaludation` 
  1. `Inception Score` : 생성된 영상의 품질, 생성된 영상의 다양성`(diversity)` 성능평가
  2. `FID Score` 평균과 공분산 활용, GAN을 사용해 생성된 영상의 집합과 실제 생성하고자 하는 클래스 데이터의 분포의 거리를 계산한다. 거리가 가까울수록 좋은 영상으로 판단
  3. `Fidelity` : 두 이미지를 구별하는 능력 또는 이미지가 실제 소스 분포를 얼마나 잘 나타내는지 평가
- `Autoencoder` : `representation learning` 작업에 신경망을 활용하도록 하는 비지도 학습 방법
- `Variational Autoencoder` : `distribution`, `encoder`와 `decoder`를 활용해 `latent space`를 도출하고, 이 `latent space`로 부터 우리가 원하는 결과를 `decoding`함으로써 정보를 생성함
  - `latent space`는 데이터가 가지고 있는 잠재적인 변수
- `GAN(Generative Adverarial Network)` : 적대적 생성 신경망, 실제에 가까운 이미지나 사람이 쓴 것과 같은 글 등 여러 가짜 데이터들을 생성하는 모델
- `Energy based model` : 에너지 기반 모델은 통계 물리학에서 학습으로 직접 가져온 생성 모델
- `DDM` : `U-Net`,  저차원 뿐만 아니라 고차원 정보도 이용하여 이미지의 특징을 추출함과 동시에 정확한 위치 파악도 가능하게 하자는 것, 인코딩 단계의 각 레이어에서 얻은 특징을 디코딩 단계의 각 레이어에 합치는(concatenation) 방법을 사용
- `DDPM` : `Denosing Diffusion Probabilistic Models`