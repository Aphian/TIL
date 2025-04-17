### React_Spring_19

#### Spring (LocalDate 위한 Formatter)
- 날짜와 관련된 처리
- `Springboot` 내에 `Formatter` 패키지를 사용
- 문자열을 받아서 `yyyy-MM-dd` 형태로 변환 메서드
- `yyyy-MM-dd` 값을 받아서 문자열 형태로 반환 메서드 `Override`
- 프로젝트내에서 `Formatter` 등록 해줘야 사용할 수 있음.
- `config` 클래스를 생성하여 `WebMvcConfigurer` `implements` 설정
- `addFormatters` 메서드를 `Override` 하여 프로젝트에 등록
```
ex.
@Configuration
@Log4j2
public class CustomServletConfig implements WebMvcConfigurer {

    @Override
    public void addFormatters(FormatterRegistry registry) {

        registry.addFormatter(new LocalDataFormatter());

    }

}

```
#### Spring (Post Mapping)
- `return` 타입이 `long` 타입임 --> `JSON` 타입으로 바꿔서 해야하함 -> `Map` 타입으로 `return` 을 해줘야함.
- `JSON` 데이터 타입으로 받으려면 `@RequestBody`로 받아야함
- `service` 내에서 반환 값이 `Long` 값으로 구성을 함.
- `return Map.of("TNO", tno)` 로 메서드 반환 값을 설정