### Node.js_Cookie_02

#### Node.js_Cookie (Session)
- `Seession cookie` : 휘발성 `cookie` / 웹 브라우저가 켜져 있을 때 유지.
- `Permanent cookie` : 웹 브라우저를 껏다 켜도 유지됨.
  1. 기존 `cookie` 생성에 `Expire=''` or `Max-Age` 추가.
  2. `Expire=` 절대적 시점으로 지정.
  3. `Max-Age=` 현재 시점으로 언제까지 `cookie`를 살릴지 지정.

#### Node.js_Cookie (Secure & HttpOnly)
- `Session`
  1. `Https` 프로토콜일 경우에만 `cookie`를 전송
  2. `cookie` 값에 `Secure`를 추가 입력 시 적용됨.
- `HttpOnly`
  1. `cookie` 생성 시 `HttpOnly` 속성 추가 입력 시 적용.
  2. 웹 브라우저 / 웹 서버를 통신 할 때만 `cookie`를 인식
  3. 웹 브라우저에 `console` 에서 `cookie` 값을 가져올 수 없음.

#### Node.js_Cookie (Path & Domain)
- `Path`
  1. 특정 경로에서만 `cookie`를 활성화 하도록 할 수 있음.
  2. `cookie` 생성 시 `Path=` 속성을 입력 시 적용.
- `Domain`
  1. `cookie` 생성 시 `Domain=` 속성을 입력 시 적용.
  2. `Domain` 속성에 값을 넣으면 어떤 도매인에서 작동을 하도록 함