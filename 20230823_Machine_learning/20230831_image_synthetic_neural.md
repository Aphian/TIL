### 이미지 합성곱 신경망 활용 예제
- `keras ImageDataGenerator` 클래스
- `image 디렉터리`를 지정하면 자동으로 라벨을 생성해주는 클래스
- 이미지 증식 및 이미지 변환 작업도 진행
- 구성 : 보통 입력층 - 합성곱층(원하는만큼) - Flatten - 밀집층 - 규제 - 밀집출력층
- `tf.keras.utils.preprocessing.image_dataset_from_directory()`
  - 디렉토리의 이미지 파일에서 `Dataset` 생성
  - 이미지에 대한 라벨링
- `ImageDataGenerator.flow_from_directory()`
  - 디렉토리에 대한 경로를 가져오고 증강 데이터 배치를 생성
  - 이미지 증식이 가능