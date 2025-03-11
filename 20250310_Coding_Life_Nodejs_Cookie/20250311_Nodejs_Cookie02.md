### Node.js_Cookie_02

#### Node.js_Cookie (Session)
- `Seession cookie` : 휘발성 `cookie` / 웹 브라우저가 켜져 있을 때 유지.
- `Permanent cookie` : 웹 브라우저를 껏다 켜도 유지됨.
  1. 기존 `cookie` 생성에 `Expire=''` or `Max-Age` 추가.
  2. `Expire=` 절대적 시점으로 지정.
  3. `Max-Age=` 현재 시점으로 언제까지 `cookie`를 살릴지 지정.