### Spring boot 22 

- 익명 함수 : 자바스크립트에서 전역 변수의 문제점을 해결하는 방법
  1. 전역 변수 문제점
     1. 결합과 중복 선언 -> 모든 전역 변수는 결합되어 있어 쉽게 수정이 됨, 비슷한 이름으로 할당 될 수 있으며 같은 이름으로 재 할당이 되는 경우가 있음, 추적이 어려워 디버그가 어려움
     2. 네임스페이스 오염 : 자바 스크립트의 전역 스코프는 파일을 분리해서 작성하더라도 모두 같은 전역 스코프를 공유함 -> 다른 파일에서 선언한 전역 변수를 또 다른 파일에서 수정 되면서, 예상한 결과와 다른 결과가 나올 수 있음
     3. 생명 주기 : 프로젝트가 실행되는 동안 생명 주기가 계속 진행됨 -> 생명 주기가 길어지면 변수에 접근하고 재할당 할 수 있는 가능성 또한 커짐
     4. 스코프 체인 : 자바스크립트는 스콯프 안에서 참조한 변수 또는 함수가 없는 경우 상위 스코프를 검색하는 스코프 체인을 가지고 있음 -> 전역 변수의 경우 스코프 체인의 가장 상위에 존재하게 되며 코드를 실행 했을 때 변수를 검색이 될 경우가 있음
- 자바 스크립트 `join()` : 인자로 전달한 값을 기준으로 배열의 모든 값을 문자열로 연결해서 리턴해주는 함수