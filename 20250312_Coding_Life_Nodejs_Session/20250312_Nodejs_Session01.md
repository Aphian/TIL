### Node.js_Session_01

#### Node.js Session
- `npm install express-session` 명령어로 `session` 을 사용할 수 있도록 모듈을 설치
```
`app.use(session({
    옵션 설정
    secret: 노출되면 안되는 data / session ID 쿠키를 서명하는데 사용할 문자열
    resave: false,
    saveUninitailzed: true,
}))
```