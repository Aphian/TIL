# 최대공약수 / 최소공배수
---
- 최대 공약수 : big / small -> range(small, 0, -1) -> big 과 small 이 gcd로 나누면서 나머지가 0 인 값
- 최대 공배수 : (big * small) / gcd(최대 공약수)

# 문자열만 뒤집기
- 포함 여부를 부등호로 조건문 가능 ex) if 'a' <= char <= 'z' or 'A' <= char <= 'Z':

# 튜플 활용 
- `lambda x:x[1]` -> 튜플에 두번 째 요소 추출

# 삼각수 
```
while
    num * (num + 1) // 2 < num:
    num += 1
return num * (num + 1) // 2 == num

```