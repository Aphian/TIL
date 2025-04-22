### React_Spring_22

#### React (Component)
- 페이지 디렉토리는 라이팅 처리랑 컴포넌트를 조합하기 위해 구현한 것
- 실제로 역할과 실무 일을 하는 것을 컴포넌트라고 부름.
- 처음에 화면이 나와야 하기 떄문에 그 부분을 처리해주고 그 다음 데이터가 왔을 경우에 화면 처리를 해줘야함.
- 위에 작업을 할 때 로딩 같은 화면을 보여줄 수 있음.
- 화면 구성에 모양을 보여주기 위해 빈 데이터 객체를 생성하여 보여줌.
- `useEffect` 로 데이터가 들어왔을 때 화면 처리
- `react component`는 상태가 변경되면 자동으로 렌더링을 함.
- `useState`는 함수형 컴포넌트 상태를 유지할 수 없지만 유지하기 위해 `useEffect` 를 사용한다.
```
const [todo, setTodo] = useState(initState)
--> initState 는 초기 화면을 보여주기 위한 빈 데이터 객체
useEffect(() => {

    getOne(tno).then(data => {
        console.log(data)
        setTodo(data)
    })

}, [tno]); --> tno 값이 변할 때 렌더링을 한다.
```