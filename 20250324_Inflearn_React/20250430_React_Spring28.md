### React_Spring

#### React (Modify / Delete Component & Modal)
- `API` 에 `modify` 와 `delete` 함수 추가
- `modifyComponent` 에 초기값과 버튼 추가 `useEffect` `hook`을 사용하여 데이터를 가져와서 출력해야함.
- `modifyPage`에 `modifyComponent` 추가
- `modifyComponent` 에 받은 데이터를 출력 / 변경이 가능해야함.
```
const handleChangeTodo = (e) => {
    값 가져오기
    todo[e.target.name] = e.target.value

    값 변경
    setTodo({...todo})
}
```