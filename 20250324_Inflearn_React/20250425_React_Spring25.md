### React_Spring_25

#### React (동일 페이지 Click 처리)
- 동일한 페이지를 처리할 경우 문제가 발생할 수 있음.
- 컴포넌트 내부에 매번 변하는 상태 값을 이용
- 상태 값은 `useEffect()` 훅을 사용하는 메서드에 넣어서 사용하도록 설정
```
// customhook 추가
const [refresh, setRefresh] = useState(false)

// 호출하면 반대 값으로 상태 값 변화
setRefresh(!refresh)

return 값에 추가

// customhook 사용하는 컴포넌트에 추가.
const {page, size, refresh, moveToList} = useCustomMove()

useEffect(() => {

    getList({page, size}).then(data => {
        // console.log(data)
        setServerData(data)
    })
    // page 와 size 값은 동일해도 refresh 값이 변화하기 때문에 서버를 호출.
}, [page, size, refresh]);
```
- 동일 페이지를 클릭하면 매번 호출 할 때마다 값이 변화하는 `refresh` 값 때문에 서버에 호출이 가능하다.