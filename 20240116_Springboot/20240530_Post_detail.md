### Spring boot 26

#### Today Error
- `Springboot 3.X.X` 버전으로 오면서 `Mybatis` `SQL` 문에서 `ParameterType` 에서 `Type` 을 명시해주지 않으면 오류가 발생하게됨 -> `Springboot 2.X.X` 버전에서는 자동으로 찾아서 매핑을 해줌
  1. `build.gradle` 에서 `tasks.withType(JavaCompile) { options.compilerArgs += ['-parameters'] }`  이 코드로 컴파일러 설정 추가를 해주면 오류 해결 가능
  2. `Controller` 에서 `@RequestParam(name = "id") final Long id` 이런식으로 `name`을 명시해주면 매핑이 되면서 오류 해결 가능