### React_Spring_11

#### Spring (Entity_Test)
- `build.gradle` 파일 -> `testCompileOnly 'org.projectlombok:lombok'` / `testAnnotaionProcessor 'org.projectlombok:lombok` 추가 해줘야 `lombok` `log4j2`가 `test` 상에서 인식이 됨 
- `test` 폴더에 `repository` 폴더 생성후 `respository` 생성
- 테스트를 할 `repository`를 `@Autowired`로 의존성 주입
- `entity` 에 `@Bulider()`를 붙여줘서 자동으로 빌더 패턴을 생성해주는걸 이용하여 `test` 작업