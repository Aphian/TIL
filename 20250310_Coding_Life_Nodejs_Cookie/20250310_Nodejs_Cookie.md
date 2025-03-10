### Node.js_Cookie

#### Cookie
- 개인화 : 사람 취향 / 선택에 따라웹 페이지를 다르게 보여주는 것, 로그인 인증 등등.
- `cookie`를 도입하면서 이전에 접속한 사용자에 정보를 웹 서버에 전송하고 웹 서버는 이 정보를 바탕으로 현재 접속한 사용자를 인식함
- `http` 프로토콜에 포함된 기술
- `cookie` 설정 : `Set-Cookie: <cookie-name>=<cookie-value>`

#### Cookie (Read)
- `request.headers.cookie` : `cookie`를 웹 브라우저로 읽어오기
- `npm install cookie` : `node.js` 에서 `cookie`를 다루는 모듈 설치
- `cookie.parse()` 메서드를 이용하여 객체로 반환하여 사용하기 편하게 변수에 담아짐