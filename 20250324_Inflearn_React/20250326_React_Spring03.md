### React_Spring_03

#### React - Router
- 규모가 커지면 한 화면에 모든 것을 보여줄 순 없음
- 분기하고 처리를 할 필요성이 생김 --> `router` 가 이러한 처리 구조를 해준다.
- 웹 히스토리를 이용해서 어떤 값이 변경됬는지 알아낼 수 있음
- 변경 됬을떄 어떤 컴포넌트를 실행하는 구조로 만들어짐.
- `Next.js` 기본으로 라우팅을 제공해줌.

#### React-Router Install
- `npm install react-router-dom` 명령어
- `RouterProvider` : 라우터 객체를 만들어서 쓰는 방법
  1. 라우팅을 관리하고 조작하는 더 직관적인 `API` 제공
  2. 라우팅 처리를 독립 시키는 방법
- 라우팅 객체 생성 : `createBrowserRouter` 로 객체 생성 --> 라우팅을 처리하는데 사용함.
  1. 객체에 경로와 요소 형태로 저장을 하여 보냄. --> `list`
- 데이터를 보여주기 위해서 컴포넌트들을 다 처리를 해야하는데 `list` 요소가 많아지면 요소들을 다 처리하기 떄문에 시간이 오래걸림
- 위의 문제를 방지하고자 `code spliting` 이라는것을 이용
- 필요할 때 까지 로딩을 하지 않도록 해줌.
- `react` 에서는 `Suspense, lazy` 모듈을 활용함.
```
ex. 
import { Suspense, lazy } from "react"; --> react 에서 제공하는 모듈
const {createBrowserRouter} = require('react-router-dom');

지연 로딩 (Lazy loading)
const Loading = <div>Loading...</div>

const Main = lazy(() => import('../pages/MainPage'))
const About = lazy(() => import('../pages/AboutPage'))

라우터 생성하여 경로를 지정하면서 라우팅 기능 작용
const root = createBrowserRouter([
    {
        path:'',
        element: <Suspense fallback={Loading}><Main/></Suspense>
    },
    {
        path:'About',
        element: <Suspense fallback={Loading}><About/></Suspense>
    },
])

```