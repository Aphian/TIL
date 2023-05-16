# 데이터 구조
- 데이터 구조(자료구조) 데이터의 효율적인 접근 및 수정을 가능하게 하는 데이터의 구조, 관리 및 저장 형식을 의미

## 문자열(String)
- 특징 : 변경할 수 없고(immutable), 순서가 있고(ordered), 순회가능하다(iterable)
- 조회/ 탐색 
  1. **`.find(x)`** -> x의 첫번째 위치를 반환, 없으면 `-1`
  2. **`.idex(x)`** -> x의 첫번째 위치를 반환, 없으면 오류 발생
  3. `.startswith(x)` -> 문자열 x로 시작하면 True 반환 아니면 False 반환
  4. `.endswith(x)` -> 문자열 x로 끝나면 True 반환 아니면 False 반환
  5. `.is__() : 문자열의 어떠한 조건을 검증하는 역할
- 문자열 변경  : 원본을 바꿀 순 없음.
  1. **`.replace(old, new [, count])`** -> 바꿀 대상의 글자를 새로운 글자로 반환, `count`를 지정하면 해당 갯수 만큼 시행
  2. `.strip([chars])` -> 특정한 문자들을 지정하면, 양쪽, 왼쪽, 오른쪽 제거
  3. **`.split([chars])`** -> 문자열을 특정한 단위로 나누어 리스트로 반환
  4. `separator'.join(iterable)` -> iterable의 문자열을 separator로 이어붙인 문자열을 반환
  5. `.capitalize()` -> 앞글자를 대문자로 반환
  6. `.title()` -> `'`나 공백 이후를 대문자로 반환
  7. `.upper()` -> 모두 대문자로 반환
  8. `.lower()` -> 모두 소문자로 반환
  9. `.swapcase()` -> 대 <-> 소 문자로 반환
---
## 리스트(List)
- 특징 : 변경 가능하고(mutable), 순서가 있고(ordered), 순회 가능하다(iterable)
- 추가 및 삭제 => 원본 변경
  1. `.append(x)` -> 리스트에 값 추가
  2. `.extend(iterable)` -> 리스트에 iterable 값을 붙일 수 있음
  3. `.insert(i, x)` -> 정해진 위치 i에 값을 추가
  4. `.remove(x)` -> 리스트에서 값이 x인 첫번째 항목을 삭제
  5. `.pop([i])` -> 정해진 위치 i에 있는 값을 삭제, 그 항목을 반환
  6. `.clear` -> 리스트의 모든 항목 삭제
- 탐색 및 정렬
  1. `.index(x)` -> x값을 찾아 해당 index 값을 반환
  2. `.count(x)` -> 원하는 값의 개수를 반환
  3. `.sort()` -> 원본 list를 변형 시키고 **None** 반환
  4. `.reverse()` -> 리스트의 요소를 뒤집어 배열 **None** 반환
---
## 튜플(tuple)
- 변경할 수 없는 불변의 자료형
  1. 탐색 : `.index(x[, start[, end]])` -> 항목중 x와 같은 첫번쨰 인덱스 반환
  2. `.count` -> 튜플에서 x가 등장하는 횟수
---
## 셋(set)
- 특징 : 변경 가능하고(mutable), 순서가 없고(undordered), 순회가 가능함(iterable)
- 추가 및 삭제
  1. `.add(elem)` : 요소를 `set`에 추가
  2. `.update(*other)` : 여러 값을 추가
  3. `.remove(elem)` : 요소를 삭제하고 셋 내에 없으면 keyerror 발생
  4. `.discard(elem)`: 요소 삭제 셋내에 없어도 에러가 발생하지 않음.
---
## 딕셔너리(Dictionary)
- 특징 : 변경 가능하고(mutable), 순서가 없고(unordered), 순회 가능하다(iterable)
- 조회
  1. key값 이용 조회
  2. `.get(key[, default])` : key를 통해 값을 반환, 없을경우 None -> error [X]
  3. `.setdefault(key[, default])` : `.get`과 비슷하지만 key 값이 없을 경우 key값을 삽입 후 default를 반환 -> default 가 없을 경우 None 반환
- 추가 및 삭제
  1. `.pop(key[, default])` : key가 딕셔너리에 있을 경우 제거하고 그 값을 반환, 없으면 default 반환
  2. `.update([other])` : other가 제공하는 key, value를 쌍으로 덮어씀.