### TypeScript 7

#### 열거형 (Enum)
```
ex)
enum Response {
    No = 0,
    Yes = 1, 
}

function respond(recipient: string, message: Response): void {

}

respond("Princess Caroline", Response.Yes)
```
- 숫자 열거형은 계산된 멤버와 상수 멤버를 섞어서 사용 가능
- 초기화되지 않은 열거형이 먼저 나오거나, 숫자 상수 혹은 다른 상수 열거형 멤버와 함께 초기화된 숫자 열거형 이후에 와야함.
- 문자 열거형은 `직렬화`를 잘한다는 이점
- 문자열 열거형을 이용하면 코드를 실행할 때, 열거형 멤버에 지정된 이름과는 무관하게 유의미하고 읽기 좋은 값을 이용하여 실행 가능.
- 열거형은 런타임에 존재하는 실제 객체