### Pytorch
- `pytorch` : `Python`을 위한 오픈소스 머신 러닝 라이브러리
- 자연어 처리와 같은 애플리케이션을 위해 사용
- GPU사용이 가능하기 때문에 속도가 상당히 빠르다

#### pytorch 패키지 구성
- `torch` : 다양한 수학 함수가 포함되어져 있으며 `numpy`와 유사한 구조
- `torch.autograd` : 자동 미분을 위한 함수들이 포함
- `torch.nn` : 신경망을 구축하기 위한 다양항 데이터 구조나 레이어등으로 정의
  - `layer(RNN, CNN)`, `활성화함수(ReLU)`, `손실함수(MSELoss)`
- `torch.optim` : 경사하강법을 중심으로 한 파라미터 최적화 알고리즘이 구현
- `torch.utils.data` : `SGD`의 반복 연산을 실행할 때 사용하는 미니 배치용 유틸리티 함수
- `torch.onnx` : 서로 다른 딥 러닝 프레임워크 간에 모델을 공유할 때 사용하는 포맷
