### React_Spring_29

#### Spring (File Upload Setting)
- `DTO`를 사용하여 구현을 하는게 좋음.
- `springboot` 프로젝트 설정
  1. `application.properties`
  2. 가져올 파일 크기 설정과 경로
```
// 파일 크기
spring.servlet.multipart.max-request-size= 30MB
spring.servlet.multipart.max-file-size= 10MB
// 경로
org.zerock.upload.path=upload
```
- `DB`에 파일 자체를 저장을 할 경우 저장크기가 큼
- 파일의 이름을 저장을 해야함.
- 프로젝트 시작 시 저장될 폴더 등등 컨트롤러에서 파일 처리를 위한 `util` 패키지 구성