# 명령어

- `vim` : 편집기  `command mode` 저장, 종료, 탐색 [shift + ;], insert mode 편집 모드 [`i`]
- `:w` => command + write (저장)
- `:q` => command + quit (종료)
- `:q!` => command + quit! (강제종료)
- `:wq` => command write + quit (저장 후 종료)
- `vimtutor` : vim 명령어 튜토

- Visual Studio Code 다운 -> 기타에 체크박스 클릭 -> crl + Shift + P -> Terminal:Select ~~~ -> git bash 클릭

- markup => 역할 표시 (문법이 좀 복잡함)

- markdown => 역할 표시 (문법이 더 간결함) 글의 구조 글의 역할을 어떻게 지정하냐  작성시 고려사항 
- 문서에서의 요소 역할을 제대로 지정한다.

Ex)
# 구글 효과 (Google Effect)

## 구글 효과란 무엇인가.
구글 효과는 우리의 뇌가 정보를 기억하기보다 정보를 검색하는 방법을 기억하기로 변화하는 현상

---

# Markdown 기초

## 제목(Heading)
문서의 제목들을 레벨별로 표시할 수 있다.

가장 큰 제목은 h1으로, 그보다 작은 제목들은 각각 숫자들을 늘려가며 표시. 

h6 까지 존재
```md
# h1 가장 큰 제목 
## h2: h1 의 하위 제목
### h3: h2 의 하위 제목
#### h4: h3 의 하위 제목
##### h5: h4 의 하위 제목
###### h6:  h5의 하위 제목
```
주의 사항) 제목의 글씨 크기로 판단하지 않는다. 제목의 역할로 구분한다.

---

## 목록(list)

### 순서가 있는 목록 (Ordered List)
1. 주문을 한다.
2. 손을 씻는다.
   1. 물로 손을 적신다.
      1. 미온수를 튼다.
      2. ㅇ.ㅇ
   2. 비누를 충분히 묻힌다.
   3. 헹군다.
3. 수저를 놓는다.
4. 밥을 먹는다.
5. 계산을 한다.

### 순서가 없는 목록 (UnOrdered List)
- 된장찌개
- 짜장면
  - 간짜장
  - 쟁반짜장
  - 고추짜장
- 칼국수
- 라면
  1. 물을 받는다.
  2. 물을 끓인다
  3. 스프를 넣는다.
  4. 면을 넣는다.
  5. 5분간 주시한다.

---

## 인라인 강조 (inline)
중요한 것은 **굵게 표시**하고, 주의할 것은 *기울이* 고, `코드` 혹은 `명령어`등은 따로 표시한다.

- **Bold** => * 두 개 로 감싼다. 
- *Italic* => * 한 개 로 감싼다.
- `Code` => backtick 한개로 감싼다.

---

## 블럭 강조(Block)
### 표(Table)

|명령어|설명|예시|
|-|-|-|
|`$`|프롬프트 마크||
|`ls`|폴더 내부의 목록|`ls -a`|
|`touch`|파일 생성|`touch a.txt`|
|`mkdir`|폴더 생성|`mkdir text_files`|
|`rm`|파일 삭제|`rm a.txt`|
|`rm -r`|폴더 삭제|`rm -r text_files`|
|`cd`|폴더 이동|`cd ~`|

### 코드 블럭 (Code Block)
``` sh
$ cd ~
$ mkdir CLI
$ cd CLI
$ touch a.txt b.txt c.txt
$ grep -ri '김치'.
```

``` py
a = 1
def f():
    return 2

print ('hello world')
```

### 인용문 (Block Quote)
> 일단 유명해 져라. 그러면 아무튼 박수를 쳐줄 것이다.
>
> by Person

---

## 기타

### 수식
- 인라인 수식 $x + y$
- 블럭 수식
$$
\mathbb{N} = \{ a \in \mathbb{Z} : a > 0\}
$$

### 하이퍼링크 / 이미지
```
link
[표시 텍스트](링크 URL)

image
![대체 텍스트](이미지 URL)
```