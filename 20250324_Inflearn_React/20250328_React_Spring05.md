### React_Spring_05

#### React (Outlet)
- 서브 메뉴를 생성할 때 `Outlet` 이라는 모듈 사용
- 서브 메뉴 고유의 `layout` 을 사용함.
- `React-Router`의 중첩 `Routing`
```
ex.
/todo/list 페이지 이동 시 요소 출력
{
    path: "todo",
    element:<Suspense> fallback Loading TodoIndex </Suspense>
    // 중첩 라우팅
    children: [
        {
        path: "list",
        element:<Suspense> fallback Loading TodoList </Suspense>
        }
    ]
}
```