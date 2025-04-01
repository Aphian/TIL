### React_Spring_07

#### React (useSearchParams)
- 경로를 처리하도록 사용하는 `Hook`
- `url` 뒤에 `query string` 처리하는 경우가 많음 --> `url` 에 `?` 뒤에 붙는 문자열 -> 가변적 경로 처리
- 대표적인 처리 : `paging` 처리
- `react-router` 에서는 `useSearchParams` 를 이용하여 처리를 함.
```
ex.
경로 값 추출
const [queryParams] = useSearchParams()
const page = queryParams.get('page') --> 값 추출 후 저장

```