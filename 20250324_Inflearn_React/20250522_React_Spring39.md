### React_Spring_39

#### React (Product Add)
- 등록 페이지와 컴포넌트를 만들고 라우팅 처리
```
ex.
Router 파일에 작성.
등록 페이지.
const ProductsAdd = lazy(() => import("../pages/products/addPage"))

라우팅.
export default function productsRouter() {
    return (
        {
            path: "products",
            Component: ProductsIndex,
            children: [
                ...
                // 등록 페이지 라우팅
                {
                    path: "add",
                    element: <Suspense fallback={<Loading/>}><ProductsAdd/></Suspense>
                },
                ...
            ] 
        }
    )
}
```
- 상품 등록 `component`와 관련 `API` 호출
- `useActionState()` : `React` 18.3 버전 이상 사용
  1. 주로 <form> 태그를 처리하기 위해 사용 --> `onChange` 같은 함수 사용하지 않음.
  2. 기본적으로 `FormData`를 사용할 수 있음.
- 로딩 창 같은 처리 --> `Pending` 을 표시하는 `Modal` 창 구성.