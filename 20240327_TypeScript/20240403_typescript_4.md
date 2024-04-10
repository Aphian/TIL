### TypeScript 4

#### 리터럴 타입
- 문자열
- 숫자
- `const`로 변수를 선언하게 되면 `TypeScript`에게 이 객체는 절대 변경되자 않음을 알림
```
ex)
-> 문자열이 아닌 "Hello World" 로 타입을 정함
const helloWorld = "Hello World";
-> `let`은 변경될 수 있으므로 컴파일러는 문자열이라고 선언함
let hiWord = "Hi World";
```

#### 문자열 리터럴 타입
- 문자열 리터럴 타입은 유니언 타입, 타입 가드, 타입 별칭과 결함이 잘됨
- `enum`과 비슷한 형태로 갖출 수 있음.
```
type Easing = "ease-in" | "ease-out" | "ease-in-out";

class UIElement {
  animate(dx: number, dy: number, easing: Easing) {
    if (easing === "ease-in") {
    } else if (easing === "ease-out") {
    } else if (easing === "ease-in-out") {
    }
  }
}

let button = new UIElement();
button.animate(0, 0, "ease-in");
button.animate(0, 0, "uneasy"); --> 오류 발생함
```

#### 숫자형 리터럴 타입
```
ex)
function rollDice(): 1 | 2 | 3 | 4 | 5 | 6 {
    return (Math.floor(Math.randon() * 6) + 1 ) as 1 | 2 | 3 | 4 5 | 6;
}
const result = rollDice();
```
- 