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

#### MiddleWare 실행 순서
- `Application-level middleware` : 인자를 연속적으로 줘서 `middleware`를 여러개를 붙일수 있음.
- 같은 `path`를 가진 `route`를 두 개 일 경우 `middleware`에 `next()` 가 없을 경우 여러개가 있어도 먼저 있는 `middleware`를 호출하고 끝난다.
```
ex.
app.get('/user/:id', (req, res, next) => {
  console.log('ID:', req.params.id)
  next()
}, (req, res, next) => {
  res.send('User Info')
  --> 여기에서 middleware 호출이 끝남
})

app.get('/user/:id', (req, res, next) => {
  res.send(req.params.id)
})
--> 호출되지 않음.
-------------------
app.get('/user/:id', (req, res, next) => {
    if (req.params.id === '0') {
        next('route') --> 그 다음 route로 전달됨
        --> 조건이 맞으면 아래의 middleware를 호출함
    } else {
        next()
        --> 아니면 regular 가 있는 middleware 호출
    } 
}, (req, res, next) => {
  res.send('regular')
});

app.get('/user/:id', (req, res, next) => {
  res.send('special')
})
```

#### Node.js_Express(Middleware StaticFile)
- `JS`, `Image` 등등
- `express.static('경로', [option])`
```
app.use(express.static('경로'))
```