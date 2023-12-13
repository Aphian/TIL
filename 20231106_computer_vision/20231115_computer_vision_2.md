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
- `Stable Diffusion` : 
- `idjourney` : 
- `DALL.E2` : 
- `Discriminative Model` : p(y|x)
- `Generative Model`: p(x)
- `Representation Learnig` : `Latent Space`
- `Evaludation` 
  1. `Inception Score`
  2. `FID Score` 평균 과 공분산 활용
  3. `Fidelity`
  4. `Alignment`
- `Autoencoder`
- `Variationasl Autoencoder` : `distribution`
- `GAN(Generative Adverarial Network)`
- `Energe based model`
- `DDM` : `U-Net`
- `DDPM` : 