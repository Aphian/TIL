### Node.js_Express_05

#### Node.js_Express(Error 처리)
- `express 404` 처리
```
ex. 보통의 404 error 처리
app.use(function(request, response, next) {
  response.status(404).send('Not Found Page!');
});
```
- `app.get('경로', callback(req, res, next))` : `error`가 있는 경우 `next()` 인자를 넣어서 사용함
```
ex. 그 외의 처리
app.use(function(err, request, response, next){
  response.status(500).send('Something broke!!');
});
--> next를 가지고 있는 middleware 가 호출되면서 error 상황을 사용자에게 보여준다
```