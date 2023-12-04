# 반복문 (Loop Statement)

- `while` 수동 / `for .. in` 자동

### while 
- 조건 초기화(설정)과 관리가 매우 중요함
- `while <조건식>: <코드블럭>`
- `:`이 반드시 필요, 종료 조건을 반드시 설정!!
---
### for ... in
- `for 임시변수 in 리스트, 문자열 등등`: -> 임시변수가 코드블럭 안에서 안쓰인다면 `_`를 사용함.
- `for <임시변수> in <순회가능데이터>: <코드블럭>`
- 리스트, 문자열 -> iterable 특성을 가진 자료형들이 올 수 있음 (숫자 참/거짓은 iterable 하지 않음.)
- 종료 까지도 알아서 해줌.
- `for n in range(5):` -> for 문에서 range()를 자주 사용함
- 문자열을 `for`로 반복하면 한글자씩 임시변수에 들어감.
  1. `range()`와 순회할 String의 길이를 활용하여 `index` 접근과 변경이 가능함.
  2. 딕셔너리 순회 가능 : `key` 값으로 `value`에 접근하여 변경가능
---
### enumerate()
 - `list`를 `enumerate(list)` -> 하면 튜플로 값을 가져와짐
---
### List Comprehension (리스트 내포)
- `[expression for 임시변수 in iterable]`
- ex) `cubic_list = [num**3 for num in range(1, 4)]`
---
### Dictionary Comprehension (딕셔너리 내포)
- `{key: value for 임시변수 in inerable}`
- `dic[key] = value` => 지금부터 dic의 key의 값은 value -->> 기존 키면 갱신 / 신규 키면 추가
---

### 반복 제어(break, contitnue, for-else)
- `break` : 반복문을 종료, `for`, 나 `while`문에서 빠져나갑니다.
- `continue` : `continue` 이후의 코드는 수행하지 않고 다음 요소부터 실행
- `pass` : 들여쓰기 이후 문장이 필요하지만, 프로그램이 특별히 할 일이 없을 때 채우는 용도로 사용
- `else` : 끝까지 반복문을 실행한 이후에 실행, `break`를 통해 중간에 종료되지 않는 경우에 실행
  1. break 없는 else 구문은 의미가 없다.