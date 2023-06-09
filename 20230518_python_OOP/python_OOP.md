# OOP
- 객체(Object)
- 객체지향프로그래밍(Object Oriented Programming)
- 클래스(Class)와 객체(Object)

## 객체
- 특징 : 타입(연산자/ 조작), 속성(상태 = 데이터), 조작법(함수 = method)
- 객체 지향 프로그래밍 : 코드의 직관성, 활용의 용이성, 변경의 유연성

## OOP
**클래스 정의**
```
class MyClass:
    pass

```
**인스턴스 생성**
```
인스턴스 명 = 클래스 명()
```
**메서드 호출**
```
인스턴스 명.메서드()
```
- 클래스 : 공통된 속성과 조작법을 가진 객체들의 분류
- 인스턴스 : 특정 클래스의 실제 데이터의 예씨(instance)
- 파이썬에서는 모든 것은 객체 -> 특정 클래스의 인스턴스다!
- 속성 : 객체의 상태/데이터 
  - ex) <객체>.<속성>
- 메서드 : 특정 객체가 할 수 있는 행위
  - ex) <객체>.<메서드>()
- 인스턴스 : 정의된 클래스에 속하는 객체를 해당 클래스의 인스턴스라고 부른다.
  - 인스턴스 변수 : 인스턴스의 속성, 고유 데이터, `__init__` 에서 self. 변수명으로 정의
  - 생성 후 `인스턴스.변수명`으로 접근 및 할당
  - 인스턴스 메서드 : 인스턴스가 사용할 메서드
    - 메서드 호출시, 첫번째 인자로 인스턴스 자기자신에 해당하는 `self`가 전달
  - **인스턴스 메서드는 호출시 첫번째 인자로 인스턴스 자신을 전달하게 설계되있음.**
  - 생성자 메서드 : `__init__(self)`
  - 소멸자 메서드 : `__del__(self)`, 같은 이름의 인스턴스에 다른걸 할당하면 소멸함(이름을 뻇으면)

## 클래스
- 클래스 내부에 데이터와 함수를 정의 할 수 있고 이 떄의 `데이터를 속성`, `정의된 함수를 메서드`
- 클래스 변수
  1. 클래스의 속성
  2. 모든 인스턴스가 공유
  3. 클래스 선언 내부에 정의
  4. `클래스.변수명`으로 접근/ 할당
- 클래스 메서드
  1. 클래스가 사용할 메서드
  2. `@classmethod`로 명시해줘야함
  3. 첫번째 인자로 `cls`가 전달됨
- 스태틱 메서드
  1. 클래스가 사용할 메서드
  2. 인스턴스와 클래스의 속성과 무관
  3. @statcimethod 명시해줘야함
  4. 어떠한 인자도 자동으로 전달되지 않음.
  5. 기능(행동)만을 하는 메서드를 정의할 때 사용
---
## 이름 공간
- 인스턴스에서 특정 속성에 접근하면, 인스턴스 -> 클래스 순으로 탐색
- 인스턴스는 3가지 메서드 모두 접근 가능 (클래스 메서드와 스태틱 메서드 사용하지 않음.)
- 클래스는 3가지 메서드 모두 접근 가능 (인스턴스 메서드를 사용하지 않음.)