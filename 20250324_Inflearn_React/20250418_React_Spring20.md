### React_Spring_20

#### Spring (REST Update & Delete)
- `Update Mapping` : `@PutMapping("/{PK}")` 로 매핑 파라미터로 `PK`와 변경할 `data` 값을 받음
- `Delete Mapping` : `@DeleteMapping("/{PK}")` 로 매핑 파라미터로 `PK` 값을 받음.

#### Spring (CORS)
- `API` 서버는 외부에서 호출해서 사용하기 때문에 외부에서 `AJAX` 호출 했을 때 사용할 수 있도록 해주는 설정
- `CORS` 설정은 2가지
  1. `Controller` 에 직접적으로 설정
  2. 웹과 관련된 설정 전체에 셋팅을 하는 방법
- `addCorsMappings` 메서드를 이용하여 설정