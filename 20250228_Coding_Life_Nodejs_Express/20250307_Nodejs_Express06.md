### Node.js_Express_06

#### Node.js_Express (Security [보안])
- `Express` 최신 버전 유지
- `https` 사용 : `TLS`
- `Helmet` : `npm install --save helmet`, `require('helmet)`, 후 `app.use(helmet())` 사용
- `cookies securely` : 방문자 식별하기 위해 사용함
- 개발에 사용된 모듈들 취약점 파악 : `npm install nsp -g` 명령어로 보안체크 모듈 설치
- `nsp check` : 명령어로 `nsp` 가 모듈들의 문제점을 파악