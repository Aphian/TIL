### Node.js_Passport_02

#### Node.js_Passport
- `app.use(passport.initialize())` : `middleware`를 `express `에 설치 --> `express` 호출 될 때 `passport`가 개입함.
- `passport` 가 개입하면서 프로젝트에 `session` 설정을 해야함
- `passport.serializeUser` 와 `passport.deserializeUser` 메서드를 설정
- 로그인 하면서 `serialzeUser` `callback` 함수에 첫 번째 인자에 사용자가 보낸 값들이 들어감.