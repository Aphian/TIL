### React_Spring_26

#### React (Read)
- `customshook` 에 `hook` 생성 --> `moveToRead` 변수로 `tno` 값을 받아서 페이지 이동
- `ListComponent`에 제목을 클릭하면 이동하도록 구현.
```
// moveToRead 추가
const {page, size, refresh, moveToList, moveToRead} = useCustomMove()

// Click event 추가
<div key={todo.tno} className='w-full min-w-[400px] p-2 m-2     rounded shadow-md'
    onClick={() => moveToRead(todo.tno)}
>
```

#### React (Create)
- `api`를 구성 `create`는 `post` 방식으로 데이터를 전송해야함.
```
export const postAdd = async (todoObj) => {
    // post 방식 설정
    const res = await axios.post(`${prefix}/`, todoObj)

    return res.data

}
```
- `AddComponent` 구성
```
    // 값이 없을 경우 빈 내용 설정
  const [todo, setTodo] = useState({...initState})

  const handleChangeTodo = (e) => {

    console.log(todo[e.target.name] = e.target.value)

    // 값 초기화
    todo[e.target.name] = e.target.value
    setTodo({...todo})

  }
```