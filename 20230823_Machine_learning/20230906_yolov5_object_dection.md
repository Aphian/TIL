### yolov5 를 활용한 객체 검출
- 필요 패키지
  - `pytorch` 기반 구성된 알고리즘
  - `python 3.8` 이상 버전이 최적화
  - `GPU` 를 사용 가능해야함

#### GPU
- CPU보다 더 작고 전문화된 코어로 구성된 프로세서
- 여러개의 코어가 함께 작동하므로 여러 코어로 나누어 처리할 수 있는 작업의 경우 성능의 이점을 제공
- 시스템에서 그래픽연산을 빠르게 처리하여 결과값을 모니터에 출력하는 연산장치

#### yolov5를 활용한 이미지 객체 검출 재 학습
1. 재학습 이미지 준비
    - 이미지 관련 데이터 생성
2. `yolov5` 다운로드(기 학습된 모델활용 재학습)
    - 필수 패키지 `install`
3. `yolo 설정파일(yaml)`의 내용을 재학습 이미지에 맞게 수정
    - 재학습 : `yolo` 파일의 `train.py` 파일을 이용
    - 예측 : `yolo` 파일의 `detect.py` 파일을 이용

#### 학습 이미지 경로 설정 파일 구성
- `data.yaml` 파일 생성
- `roboflow`에서 다운 받은 `yolo5 dataset`에는 해당 파일이 생성되어 있음.
    - 직접 수집한 이미지를 재학습 시키려면 해당 파일은 메모장으로 생성하면 된다.
- `yaml` 파일의 필수 요소
    - 학습데이터 경로
        - `train: train/images`
        - `val: valid/images`
        - `test: test/images`
- 클래스 수
    - `nc`: 2
- 클래스 이름
    - `names`: ['name1','name2',...]

#### 재학습 방법
1. `dataset/label` 포함 준비
2. 학습시킬 이미지의 파일명과 라벨 정보를 모델에게 전달해야 하므로
    1. 사용할 이미지의 저장 경로 및 파일명을 리스트로 생성
    2. 1번에서 생성한 리스트를 이용해서 학습 / 검증 데이터 분리
    3. 2번에서 분리된 내용을 이용해서 각 이미지파일명을 `txt` 파일로 생성
        - 파일저장 경로는 어디든 상관 없음 보통 `dataset`이 있는 곳에 같이 저장하는 것이 효율적
    4. `data.yaml` 파일을 수정
        - 3번에서 생성한 `txt` 파일을 `train, val` 정보로 전달
        - 프로그램내에서 `load` 해서 파일 수정
3. 현재 디렉터리 확인 후 train.py 파일 사용해서 재학습진행
4. 관련 파라미터 (python 프로그램 파일 실행 옵션)
```
ex. 
# !python ./yolov5/train.py --img 416 --batch 4 --epochs 50 --data ./Pistols-1/data.yaml --cfg ./yolov5/models/yolov5s.yaml --weights yolov5s.pt --name results
```

### 재학습 후 객체 검출
- `detect.py` 파일 사용
```
ex. !python ./yolov5/detect.py --weights ./yolov5/runs/train/results2/weights/best.pt --img 416 --conf 0.5 --source gun.jpg
```