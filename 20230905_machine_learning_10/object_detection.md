### CV를 활용한 객체 검출
---
#### OpenCV를 활용한 객체 검출
- `opencv`내에는 `yolov3`의 객체를 라이브러리로 제공
- `YOLO` : `You Only Look Once`
  - 한개의 네트워크에서 탐지를 원하는 물체의 영역`(bounding box)`과 이름을 표시

#### YOLO 기본 구조
- 총 3개의 `output layer`를 갖고 있음 (82, 94, 106 `layer`)
- 피처 정보들을 조합하여 찾고자 하는 객체 위치
- 입력된 이미지를 일정 분할로 그리드 한 다음 (그리드 기분 분할함)
- 단점 : 작은 물체에 대한 검출성능이 떨어짐(V3 경우)
- 처리 순서
  1. 이미지 주입
  2. S X S 로 이미지 나누기 (그리드)
  3. 각 그리드에서 예측을 한 후 이를 종합해서 `bounding box`를 구성

#### YOLO 사용법
- `Darknet` : `YOLO` 개발자가 만든 프레임워크. `YOLO`를 위해 특별히 제작
    - 코랩은 `Darknet`을 사용하면 됨
    - 장점 : 빠르다. GPU또는 CPU와 함께 사용가능
    - 단점 : 리눅스에서만 호환됨
- `Darkflow` : `Darknet`을 `tensorflow`에 적용한것
    - 장점 : 빠르고 GPU 또는 CPU와 함께 사용 가능하고 리눅스, 윈도우, 맥에서 호환
    - 단점 : 설치 복잡
- `OpenCV` : 최소 3.4.2버전 필요
    - 장점 : `openCV`외에 설치만필요
    - 단점 : CPU에서만 작동하기 때문에 비디오를 실시간으로 처리하는 데 속도가 빠르진 않다

#### OpenCV DNN YOLO 사용하기 (사용법 위주)
- YOLO 사이트에서 기 학습된 모델의 weight와 cfg 파일을 받아와야 함
- `http://pjreddie.com/darknet/yolo/`
- `weight file` : 훈련된 모델
- `cfg file` : 구성파일 (모델 구성파일)
- `name file` : 모델이 감지할 수 있는 객체 명
