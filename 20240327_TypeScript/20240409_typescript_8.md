### TypeScript 8

- 재사용 가능한 컴포넌트를 구축 중요함
- 현재의 데이터와 미래의 데이터를 다룰수 있는 컴포넌트는 거대한 소프트웨어 시스템을 구성하는데 있어 유연한 능력을 제공한다.
- 재사용 가능한 컴포넌트를 생성하는 도구 상자 `제네릭`
- 단일 타입이 아닌 다양한 타입에서 작동하는 컴포넌트를 작성할 수 있음.

#### 제네릭
- `identity` 함수는 인수로 무엇이 오던 그대로 반환하는 함수
```
ex)
제네릭이 없다면 특정타입을 주어야함
function identity(arg: number): number {
    return arg
}
또는 any
function identity(arg: any): any {
    return arg;
}
--> 어떤 타입이든 받을수 있다는 점이 제네릭 이지만, 반환할 때 어떤 타입인지에 대한 정보를 잃게됨

function identity<T>(arg: T): T {
    return arg;
}
--> 타입을 불문하고 동작함
```
- 제네릭 함수를 작성하고 나면 제네릭 함수 호출
    1. 함수에 타입 인수를 포함하여 인수에 전달하는 방법
    ```
    ex)
    let output = identity<string>("Hello World");
    ```
    2. 타입 인수 추론 : 전달하는 인수에 따라 컴파일러가 `T`의 값을 자동으로 정하게 하는방법
    ```
    ex)
    let output = identity("Hello World");
    <> 에 명시적으로 전달하지 않음
    컴파일러가 값을 보고 타입을 정하게 됨
    ```
- 함수 선언과 유사하게 타입 매개변수가 먼저 나열되는 비-제네릭 함수의 타입과 비슷함
- 타입 변수의 수와 타입 변수가 방식에 따라 타입의 제네릭 타입 매개변수에 다른 이름을 사용할 수 있음.
- 객체 리터럴 타입의 함수 호출 시그니처로 작성 가능.
- 제네릭 제약 조건 : 제약조건을 명시하는 인터페이스를 생성하고 `extends` 키워드를 사용하여 함수에 명시해줌
```
ex)
제약조건 인터페이스
interface Lengthwise {
    length: number;
}

제약조건을 명시한 인터페이스가 위에 없다면 오류가 발생함
function logging<T extends Lengthwise>(arg: T): T {
    console.log(arg.length)
    return arg
}
```
