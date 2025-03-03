### Node.js_Express_02

#### Express (Main)
- `Express` 를 사용하기 전에는 사용되는 부분을 확인하기가 어려움
- `Express` 가 제공하는 모듈을 사용하면 사용되는 부분이 각각 구현되기 때문에 필요한 부분끼리 모여있기 떄문에 가독성이 좋아짐.
- `URL`에 `query String`을 사용하지 않고 `Route Paramter`을 사용하여 웹 애플리케이션의 `URL`에 있는 값을 가져와서 `express` 상에서 읽는 방법으로 구현.
```
ex. app.get('/page/:pageId', function(request, response){
    return response.send(request.params);
--> pageId 값을 express 에서 읽어서 가져올수 있음.
})
```