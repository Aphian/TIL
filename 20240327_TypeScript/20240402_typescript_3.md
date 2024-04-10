### TypeScript 3
  
#### 함수 타입
- 매개변수 타입
```
let myAdd: (x: number, y: number) => number =
    function(x: number, y: number): number { return x + y; };
-> 
let myAdd: (baseValue: number, increment: number) => number =
    function(x: number, y: number): number {return x + y; };
-> 가독성을 위함
```
- 변환 타입 : `=>` 표기슬 써서 반환 타입을 분명히 할 수 있음.
- 값을 반환하지 않는다면 `void` 써서 표시
- 타입의 추론
```
전체 함수 타입
let myAdd = function(x: number, y: number): number { return x + y; };

매개변수 x 와 y number 타입
let myAdd: (baseValue: number, increment: number) => number =
    function(x: number, y: number): number {return x + y; };
```
- 추론의 형태 : `contextual typing` 이라 부름

#### 선택적 매개변수 / 기본 매개변수
- 컴파일러는 각 매개변수에 대해 사용자가 값을 제공했는지 검사
- 함수에 주어진 인자의 수는 함수가 기대하는 매개변수의 수와 일치해야함
- `TypeScript`에서 선택적 매개변수를 이름 끝에 `?`를 붙임
- 유저가 값을 제공하지 않거나 `undefined`로 했을 때에 할당 될 매개변수 값을 정해놓을수 있는데 이것을 기본-초기화 매개변수라고 함