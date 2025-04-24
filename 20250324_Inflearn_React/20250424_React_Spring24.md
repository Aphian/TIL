### React_Spring_24

#### React
- `customhook` 에 수정 / 삭제 이동 기능
```
    const moveToModify = (num) => {
        // navigate 메서드로 경로와 queryString 부여
        navigate({
            pathname: `../modify/${num}`,
            search: queryDefault
        })
    }
```
- `ReadComponent` 에 `customhook` 사용을 위한 `button` 추가.
- `custombook` 에서 반환하는 값으로 `page`, `size`를 가져올 수 있어서 필요한 경우 꺼내서 사용할 수 있음.
```
function ListComponent(props) {
    // customhook 에서 가져옴
    const {page, size} = useCustomMove()
    // 화면에 출력할 데이터
    // 데이터가 없을 경우 initState 초기 설정값으로 출력
    const [serverData, setServerData] = useState(initState)

    useEffect(() => {
        getList({page, size}).then(data => {
            setServerData(data)
        })

    }, [page, size]);
}
```