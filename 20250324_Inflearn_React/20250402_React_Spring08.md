### React_Spring_08

#### React (동적 페이지 처리)
- 수정/ 삭제 작업은 매번 다른 번호(식별자)를 사용함
- `useParams()`로 찾는 번호를 이용하여 동적 처리
- `url`에 `page` 같은 요소를 유지하려고 한다면 `url` 에서 유지하고자 하는 `querystring`을 가져와야함 -> `useSearchParams()` 사용 --> `createSearchParams({가져가고자 하는 값})` 메서드를 이용하여 보냄
- 동적처리를 하기 때문에 `navigate()` 메서드를 이용하여 처리
  1. `pathname: 경로`
  2. `search: 가져가고자 하는 값`