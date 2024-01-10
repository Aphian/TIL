### JavaScript_2
- `JavaScript` 변수 선언 : 키워드 `var` 변수명
- 예약어로 변수 선언 불가 `(var, function, let, for)` 등.. 

#### JavaScript Object
- 객체 프로토타입 : `JavaScript` 객체가 또다른 객체로 특성을 상속시키기 위한 메커니즘
- `JSON` 데이터 : `JavaScript` 객체 문법상의 구조화된 데이터를 표현하기 위한 표준 텍스트기반 포맷
- 객체 : 서로 관련된 데이터와 함수의 집합
- 키워드 `this` : 지금 동작하고 있는 코드를 가지고 있는 객체

#### 프로토타입 기반 언어 JavaScript
- 모든 객체들이 메소드와 속성들을 상속 받기 위한 템플릿으로써 프로토타입 객체를 가진다.
- 인스턴스 생성 : `Object.create()` 메서드
- 모든 생성자 함수는 `constructor` 속성을 지닌 객체를 프로토타입 객체로 가지고 있음 -> 원본 생성자 함수 자신을 가르키고 있음

#### JavaScript 생성자
- 