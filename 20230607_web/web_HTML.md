## Web
- Web : 인터넷에 연결된 컴퓨터를 통해 사람들이 정보를 공유할 수 있는 정보 공간
- 인터넷 상의 동작하난 하나의 서비스
 1. Web 1.0 : 읽기/ 수용만 가능
 2. Web 2.0 : 읽기/ 쓰기 
 3. Web 3.0 : 읽기/ 쓰기 / 소유
- 하이퍼텍스트 : 웹이라는 것이 하이퍼 텍스트로 묶인 집합, 연결/ linked 된 text 들
- html validator
---
## HTML

- `<!DOCTYPE html>` : HTML 이라는 문서 시작을 알림.
- `<html lang="ko">` : 지정된 요소의 언어로 지정
```
<head> : 메타데이터 설정등의 위치 
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Heading</title>
</head>
```
- `<h1>This is Heading 1</h1>` : 헤더
- `<p>` : 문단 분할
- `<strong>` : 중요성의 의미 (굵게)
- `<em>` : 중요성의 의미 (기울임)
- `<br> ` : 빈 공간(개행)
- `<hr>` : 가로 줄 긋기
- `<pre>` : 블록 지정
- `<a herf="" tartget="">` : link 태그
- `<a href="#">` : 목적지를 알 수 없을 때 `#`을 link에 써줌
- `<ol>` : 순서가 있는 리스트 
```
<ol>
    <li>HTML 배우기</li>
    <li>마크다운으로 정리하기</li>
    <li>
        내일 내용 예습
            <ol>
                <li>CSS</li>
                <li>Bootstrap</li>
            </ol>
    </li>
</ol>
```
- `<ul></ul>` : 순서가 없는 리스트
- `<iframe>` : 브라우저 위에 다른 특정한 브라우저를 위에 얹어 놓는다는 느낌의 프레임
```
<iframe> 
    width="560" 
    height="315" 
    src="https://www.youtube.com/embed/YKAnA0Jim_g" 
    title="YouTube video player" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
    allowfullscreen>
</iframe>
```
- `<from>` : 사용자가 입력한 데이터를 수집하기 위해 사용하는 태그
```
<form action="URL(아래 데이터를 제출할 목적지)" method="GET/POST">            
    <div>
        <label for="username">username : </label>
        <input type="text" id="username" required minlength="4" maxlength="20">
    </div>
    <div>
        <label for="password">password : </label>
        <input type="password" id="password" name="password">
    </div>
    <div>
        <label for="my_email">email : </label>
        <input type="email" id="my_email" placeholder="email은 @을 포함합니다.">
    </div>
    <div>
        <label for="age">age : </label>
        <input type="number" id="age" value="20" min="14" max="100">
    </div>
    <div>
        <label for="bio">자기소개</label>
        <textarea name="" id="bio" cols="30" rows="10"></textarea>
    </div>
    <div>
        <input type="submit">
    </div>
</form>
```
