### React_Spring_13

#### Spring (QueyrDSL)
- `springboot JOOQ`가 세계적으로 사용되긴 함.
- `QueryDSL` 설정 -> `build.gradle` 에 추가적으로 해줘야함
  1. 만약 프로젝트를 공유할 경우 `toolchain` 을 설정함으로써 `JDK`버전이 다를경우의 문제를 완화해줄 수 있음.
  2. 사용하려는 `JDK` 버전이 잘 설치되어 있고 환경변수 `JAVA_HOME`이 제대로 설정이 되어 있다면 삭제하면 `gradle` 이 인식을 못하던걸 제대로 인식이 될 수 있음.
- `build.gradle` 의 `Task` 항목에서 `other -> compilJava` 실행
- `build` 폴더에서 `Q Domain` 이 생성됨
- `queryDSL` 의 페이징 처리는 `applyPagination` 으로 함