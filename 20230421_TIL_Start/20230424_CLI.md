## Linux

### Git 다운로드 -> Git bash : 파일 만들기 삭제 등.
### CLI | GUI
|CLI|GUI|
|---|---|
|Command|Graphic|
|Line|User|
|Interface|Interface|

CLI : 명령을 줄/글 접한다.

Interface : 접촉하는 부분. 서로 다른 두 존재의 접점

UI : User Interface 사용자와 다른 무언가와에 접점
UX : UI를 변경 시켜 UX의 향상 유저 경험, 경험의 총체
Unix 와 Windows 명령어가 다름 
--> git bash로 인해 윈도우 안에서 Unix 명령어를 번역해 사용
프로그램 : 터미널, CLI 환경
프롬프트 마크(sign) : $ 명령을 받을 준비 됨, 지금 명령 가능

### 명령어

- `touch` 파일 생성
- `mv` : 파일 이름 변경 및 이동
- `mkdir` : make directory 폴더 생성
- `cd` : change directory 폴더 이동
- `clear` : 화면 정리(단축키 crl + L)
- `rm` : 파일 삭제, *(뭐가 오든 상관 없음)
- `echo 'hello'` : 뒤의 문자열 표준 출력
- `Tab Tab` : 명령어 후 경우의수 보여주기
- 정상적이지 않은 명령에서 벗어나기 : `crl + C` ^ << crl 의미 
- `cat` : concatnate 파일 내용 표준 출력
- `tab` : 자동완성
- `>>[uphand]` : 내용 추가
- `ls` : 내용물 확인, 폴더 지정하면 그 폴더 안에 내용 확인
- `ls -l` : 내용 자세히/ ls -t : 수정된 시간 나열/ .파일명 : 숨김파일, 폴더
- `ls -a` : 전체 보기
- `rm -i` : 지우는거 물어보기/ 
- `| (파이프)` :  왼쪽 표준 출력을 오른쪽 명령어 뒤에 붙임
- `wc` : 파일/ 출력의 줄/ 단어/ 글자수를 보여줌
- `diff` : 두 파일간의 차이를 보여줌 
- `command` A | command B << command A 결과를 붙이기
- `less` : 문서에서 찾아보기 / 파일을 열어서 탐색 가능 (q로 나옴)
- `grep` : 특정 문자열 찾기 [Globally search a Regular Expression and Pring], 파일 내용 찾기
- `ps` : 현재 실행 중인 프로세서 상태 확인
- `head`  : 특정 파일의 앞 10줄을 보여줌
- `tail` : 특정 바일의 뒤 10줄을 보여줌
- `kill` : 실행중인 프로세스 pid로 종료
### 폴더
- 폴더 상징기호 : / -> root(뿌리 최상단), ~ -> Home, . -> 지금 있는 폴더, .. -> 부모폴더
- `mkdir -p` : 부모-자식폴더 생성
- `pwd` : Present Working Directory  : 현재 작업중인 폴더
- `rm -r` : 내부 파일 다 돌면서 삭제
- `cp -r` : 내부 파일 다 돌면서 복사
- `rm -rf` : 폴더 강제 삭제
- `mv` : 폴더명만 바꿈
- `rm dir` : 폴더 삭제(내용물이 없어야함, 잘 안쓰임)
- `find` . -name 'apple' : 파일 명 찾기/ 내 위치(.)에서 이름이 apple 인 파일을 다 찾아줘
- `grep -ri` '[파일내용]' : 내 위치(.)에서 파일 내용 중 [파일내용]이 들어간 파일 - 대문자 상관없이 찾기
- `;` --> 체이닝 할 때 에러가 나더라도 하려고 함
- `&&` --> 체이닝 할 때 에러가 나면 그 후에 명령어도 실행이 되지 않음.