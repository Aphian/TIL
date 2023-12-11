### Computer_vision
- 컴퓨터가 디지털이미지나 비디오에서 정보를 추출하고 해석하여 특정 작업을 수행하는 컴퓨터 과학 분야
- 컴퓨터가 이미지와 비디오 데이터를 분석하고 해석하는 기술
- `Perception`(인식) : `Vision`, `Auditory`
- `Time`(시계열) : `NLP`(자연어 처리), `Time serise`
- `Generative`(생성) : `Variational inference`(변분추론),
  1. `Generator(생성)-discriminator(판별)` : 데이터를 생성하는 `gernerator`와 데이터를 구별하는 `discriminator`가 경쟁하는 과정을 통해서 데이터를 학습 -> `GAN`
- `Action-Value robot` : `Model-free`, `Representation`, `Value learning`

#### YOLO Model
- 과정 : `Anomaly Detection` -> `Image Classification` -> `Object Detection`
- `DPM(Deformable Part Model)` : `bounding box regression`
- `object detection` 역사 `AlexNet (google net)`
- `One-stage detector` : 입력 이미지 전체를 네트워크에 한번에 클래스와 box 찾음
- `Two-stage detector` : `stage1` : `ROI`, `RPN` 
                         `stage2` : `ROI`들에 대한 클래스 분류, bbox 회귀 성능이 좋음
- `Region Proposal` : `Faster R-CNN`에서 활용, `selective search` 없이 `RPN` 학습하는 구조로 모델을 만드는 것
  1. 다양한 사이즈의 이미지를 입력 값으로 `object score`과 `obeject proposal`을 출력
  2. `Fast r-cnn`과 합성공 신경망을 공유
  3. `feature map`의 마지막 `conv` 층을 작은 네트워크가 `sliding`하여 저차원으로 매핑
  4. `Regression과 classification`을 수행
- `Selective Search` : `object` 인식이나 검출을 위한 가능한 후보 영역을 알아낼 수 있는 방법을 제공
- `NMS IOU`
  1. `IOU` : 객체를 검출 하는데 검출된 객체가 겹쳐질 경우 / 교집합/합집합의 비율을 의미
  2. `NMS` : `YOLO` 검출된 `bounding box` 들이 여러개 존재 하게됨
              -> 여러 개의 박스들을 `Confidence`(정확도)가 높은 순서대록 정렬
              -> 제일 큰 `Confidence`값을 기준으로 하나씩 `IOU`를 비교 하여. YOLO에선 0.5(50%)로 디폴트 되어 있다. 즉, 50%겹칠시에 첫번째것만 남기고 버리게 된다.
              -> 최종 결과가 나옴