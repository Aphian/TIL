### Node.js & MySQL_03

#### Node.js & MySQL (Create)
- `node.js` 에서 `mysql` 서버에 값을 넣을 때 자동으로 증가하는 `key` 값은 사용자가 넣지 않고 자동으로 저장이 되는데 `mysql` 입장에서는 값을 받아야함
- `callback` 함수의 두번 째 인자의 `insertId` 라는 `node.js` 의 속성으로 값을 넘기면 `mysql` 서버에서 값을 받음.

#### Node.js & MySQL (Update)
- `update` 기능을 사용시 기존의 상세페이지와 방식이 같음.
- `update` 후 `submit` 기능을 실행하여 `mysql` 서버에 `update SQL` 문을 적용시켜야함