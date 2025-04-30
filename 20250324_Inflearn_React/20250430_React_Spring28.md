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
- `modal` 창 처리
  1. 수정을 했는지 삭제를 했는지를 확인하는데 필요함
- `api`에 추가한 함수를 가진 함수 정의 / 이벤트 처리 버튼
```
const modify = () => {
    putOne(todo).then(data => {
        // 처리결과를 모달창에 보여줌
        setResult('Modified')
    })
}

const delete = () => {
    deleteOne(tno).then(data => {
        setResult('Deleted')
    })
}
```
- `modal` 창 종료 이벤트 처리.
```
{result ? <ResultModal title={"처리 결과"} content={result} callbackFn={closeModal}></ResultModal> :<></>}
```