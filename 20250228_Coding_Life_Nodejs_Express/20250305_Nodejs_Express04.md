### Node.js_Express_04

#### Node.js_Express(MiddleWare Create)
- `middleware` 생성
```
app.use(function(request, response, next){
    next();
});
--> 모든 요청에서 middleware를 불러와서 사용하지 않는 부분에서도 읽어들어오는 비효율이 발생함

app.get('*', function(request, response, next){
    next();
});
--> get 요청에서만 middleware를 호출함. 불필요한 읽어드림을 배제할 수 있음.
```
- `Express` 에서는 모든게 `middleware`라고 생각할 수 있음.