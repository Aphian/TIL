### TypeScript 5

#### 유니언 타입 (Untion Types)
- 여러 타입 중 하나가 될 수 있는 값을 의미
- `|`로 각 타입을 구분하여 작성
```
ex)
function padLeft(value: string, padding: string | number) {

}
```
- 유니언 타입인 값이 있으면, 유니언에 있는 모든 타입에 공통인 멤버들에만 접근 가능
- 유니언을 사용하는데 사용하는 기술 `TypeScript`가 현재 가능한 타입 추론의 범위를 좁혀나가게 해줄 수 있는 리터럴 타입을 갖는 단일 필드를 사용하는 것.

#### 교차 타입 (Intersection Types)
- 여러 타입을 하나로 결합
- 기존 타입을 합쳐 필요한 기능을 모두 가진 단일 타입을 얻을 수 있음.
- `&`를 작성하므로써 생성