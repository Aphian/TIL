### React_Spring_40

#### React (React Router loader)
- `useEffect()` 말고 `loader()`
- `Component`가 데이터를 뿌리기 전에 데이터를 미리 준비하는 것.
- 하지만, 아직 불완전함.
- `react-router`는 프레임워크 모드와 `data` 모드가 분리되어 있음.
- 프레임워크 모드의 `react-router`는 서버 쪽 렌더링, 리믹스 등등 서버 사이드 렌더링 방법을 지원하기 위해 두 가지 형태로 지원을 하기 때문임.
- 사용하고자 하는 `data` 모드 `react-router`에는 이런게 없음.
- `data` 모드를 사용하는 이유는 마음대로 추가로 변화를 주면서 사용이 가능 하기 떄문.
- 보통 페이지를 만들었을 때는 `router`를 받는 역할만 함.
- `loader`를 사용하게 되면 `routing` 할 때 데이터를 받을 수 있도록 설계가 됨.
```
ex. loader 정의.
export async function loadProducts({request} : LoaderFunctionArgs) {

    const url = new URL(request.url);
    const page = url.searchParams.get('page') || "1";
    const size = url.searchParams.get('size') || "10";

    const queryStr = createSearchParams({page, size}).toString();
    const res = await axios.get(`http://localhost:8080/api/products/list?${queryStr}`);

    return res.data;

}
```
- `router`안에 `loader`를 정의한 내용을 추가해줘야함.
```
{
    path: "list",
    element: <Suspense fallback={<Loading></Loading>}><ProductsList></ProductsList></Suspense>,
    // loader 지정.
    loader: loadProducts
},
```
- 화면에서 `uesLoaderData()` 훅 추가하여 사용.
```
ex. useState() 를 사용하여 값을 받아서 변화 주는 행위를 안해도 됨.
const pageResponse = useLoaderData()
```