### Node.js_Express_05

#### Node.js_Express(Error 처리)
- `express` 처리
- `app.get('경로', callback(req, res, next))` : `error`가 있는 경우 `next()` 인자를 넣어서 사용함
- `next()` 함수로 어떠한 내용을 전달하는 경우(`route`를 제외한) `Express`는 현재의 요청에 오류가 있는것으로 간주하며 오류 처ㄹ와 관련되지 않은 나머지 라우팅 및 미들웨어 함수를 건너뛴다.
- 오류 처리 함수는 4개의 인수를 갖는다
```
ex. error 처리
app.use(function(error, request, response, next) {
  response.status(404).send('Not Found Page!');
});
```
- `Express`는 내장된 오류 핸들러와 함께 제공됨
- 내장 오류 핸들러는 앱에서 발생할 수 있는 모든 오류를 처리함

#### Node.js_Express(Router)
- 소프트웨어가 커짐에 따라 복잡도의 정리정돈이 필요함
- `route(경로)`들이 많아짐 --> 정리 정돈할 필요가 있음.
- `express.router` : `router` 라는 것을 생성하는 것
```
ex. 같은 경로로 시작하는 route 를 묶어서 파일에 저장 후 내보내기
같은 경로로 시작하는 router 묶은 파일 생성 후
app.use('공통 경로(ex. /topic)',middleware 이름) 으로 불러들어오기

var express = require('express');
var router = express.Router();

// 파일 분리
var topicRouter = require('./routes/topic.js');

// 파일 불러오기
app.use('/topic',topicRouter)


```