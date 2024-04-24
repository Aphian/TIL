#### 2024. 3. 27.
### TypeScript
- `JavaScript`의 슈퍼셋의 오픈소스 프로그래밍 언어.
- 정적 타입을 명시할 수 있다는 것
- 개발 도구에게 개발자가 의도한 변수나 함수 등의 목적을 더욱 명확하게 전달할 수 있음
- 전달된 정보를 기반으로 코드 자동 완성 / 잘못된 변수/함수 사용에 대한 에러 알림을 보다 풍부하게 피드백을 받을 수 있게 됨
- 파라미터의 타입이 다를 때뿐만 아니라, 지정된 개수의 파라미터를 전달하지 않았을 때도 에러가 발생하여 `JavaScript`에 비해서 에러 핸들링이 유리함

#### 주의사항
- `TypeScript`에서 지정된 타입의 지정된 인자를 전달 받아야 정상적으로 함수가 실행됨
- 선택적으로 인자를 설정하고 싶은 경우 파라미터 위에 `?` 작성
- 필수 파라미터는 선택적 파라미터보다 먼저 작성되어야함.

#### 2024. 3. 28.
### TypeScript 2

#### TypeScript 기본 타입
- `Boolean` : `let isDone: boolean = false;`
- `Number` : `let num: number = 1;`
- `String` : `let str: string = "red";`
- `Array` : `let list: number[] = [1, 2, 3];`
- `Tuple` : `let x: [string, number]; x = ["hello", 10]` -> 순서가 바뀌면 오류가 발생함
- `Enum`
```
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
```
- `Any` : 알지 못하는 타입을 표현, 동적인 컨텐츠에서 값을 온다.
  1. 타입의 일부만 알고 전체는 알지 못할 때 유용
- `void` : 어떤 타입도 존재할 수 없음을 나타낼 때 사용
- `Null, Undefined` : 다른 모든 타입의 하위 타입
```
let u: undefined = undefined;
let n: null = null;
```
- `Never` : 절대 발생할 수 없는 타입, 함수 표현식이나 화살표 함수 표현식에서 항상 오류를 발생시키거나 절대 반환하지 않는 반환 타입으로 사용됨
- `Object` : 원시 타입이 아닌 타입