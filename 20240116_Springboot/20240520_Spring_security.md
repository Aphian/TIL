### Spring boot 20

- 스프링 시큐리티 암화화 라이브러리 : `PasswordEncoder` 를 이용하여 비밀번호를 암호화 할 수 있음
- 비밀번호는 복호화`(Decodeing)`가 되면 안되기 때문에, `PsswordEncoder`는 복호화가 불가능한 단반향 `Hash` 알고리즘을 제공해주는 인터페이스 제공
  1. `build.gradle` 에서 `spring-security-crypto` 추가
- 로그인 체크 인터셉터
```
if (member == null || member.getDeleteYn() == true) {
            response.sendRedirect("/login.do");
            return false;
        }
--> member 객체가 null 이면 로그인이 되어 있는 않은 상태
--> 강제로 로그인 페이지로 이동
```
- 애플리케이션 인터셉터
```
@Override
    public void addInterceptors(InterceptorRegistry registry) {
        registry.addInterceptor(new LoggerInterceptor())
                .excludePathPatterns("/css/**", "/images/**", "/js/**");

        registry.addInterceptor(new LoginCheckInterceptor())
                .addPathPatterns("/**/*.do")
                .excludePathPatterns("/log*");
    }
--> addInterceptor() : 애플리케이션 내의 모든 페이지에 접근할 때 preHandle()이 작동함
--> excludePathPatterns() 를 이용해서 로그인/로그아웃 URL 인터셉터 실행 제외
```