### Node.js_Passport_02

#### Node.js_Passport
- `app.use(passport.initialize())` : `middleware`를 `express `에 설치 --> `express` 호출 될 때 `passport`가 개입함.
- `passport` 가 개입하면서 프로젝트에 `session` 설정을 해야함
- `passport.serializeUser` 와 `passport.deserializeUser` 메서드를 설정
- 로그인 성공하면서 딱 한 번 `serialzeUser` `callback` 함수에 첫 번째 인자에 사용자가 보낸 값들이 들어감. --> `session store`에 사용자 식별자가 저장됨 
- `deserializeUser` 은 저장된 `data`를 기준으로 사용자가 필요한 정보를 조회할 때 사용함.