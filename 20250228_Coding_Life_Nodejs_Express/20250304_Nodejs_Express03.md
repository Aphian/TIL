### Node.js_Express_03

#### Node.js_Express
- `Express`에서의 `redirection` : `response.redirect()`를 이용하여 `redirection`을 할 수 있음.

#### Node.js_Express (Middleware)
- 다른사람(본인)이 만든 소프트웨어를 부품으로 해서 소프트웨어를 만든다.
- `Third-party`: 다른 사람이 만든 부분이다.
- `Express body-parser` : `npm install body-parser` 명령어 실행
- `app.use` 메서드를 이용하여 개발하는 웹 애플리케이션에 `express` 내에 있는 `middleware` 인 `body-parser` 를 장착시킬 수 있음.

#### Node.js_Express (Compression)
- 사용자가 필요로 하는 데이터 용량이 많아지면 많아질수록 비용이 많이 들어감
- 데이터 용량을 압축하고 받을 때 압축을 풀게 끔 알려주도록 하는것이 비용적으로 절약됨
- `Express Compression Middleware` 사용함