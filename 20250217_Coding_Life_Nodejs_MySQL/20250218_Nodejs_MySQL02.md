### Node.js & MySQL

#### Node.js & MySQL Module
- `npm mysql module` 활용 -> `npm install mysql` 명령어
- `npm install --save mysql` --> 해당 프로젝트 내의 `package.json` 에 의존성이 설치와 통시에 주입이 됨.
- `node.js` 가 `mysql` 서버에 접속하려면 `id` 와 `pw`가 필요함
- 설정파일을 만들어줘야함 
```
ex. mysql.js
var mysql      = require('mysql');

var connection = mysql.createConnection({
    // mysql 서버가 같은 컴퓨터에 있다면.
    host     : 'localhost',
    user     : 'root',
    password : 'secret',
    database : 'DB'
});
  
connection.connect();
```

#### Node.js & MySQL (List Read)
- `DB` 속에서 데이터 가져오기
- `mysql module` 안에 있는 `query` 메서드를 이용하여 값을 가져옴
- `query` 메서드 안에 `SQL` 문을 작성하여 필요로 하는 데이터를 `DB` 안에서 가져올수 있음
- 데이터는 객체 형태로 가져옴
```
ex. db.query(`SELECT * FROM DB_name`, function(error, results){ 결과값 })

SQL 문에 `WHERE` 조건을 넣을 경우 두번째 인자에 조건을 넣으면 됨
ex. db.query(`SELECT * FROM DB_name WHERE id = ?`, [조건], function(error, results){ 결과값 })
```