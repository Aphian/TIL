# Git_Branch

- https://git-school.github.io/visualizing-git/ 브랜치 연습

- 프로젝트를 만들고 나서 init 초기화 보다 주의사항 / 설명서인 우선적으로 README.md 와 .gitignore을 만들어놓기

`git commit -am` : 기존의 트래킹 하고 있는 얘들을 스테이지에 올리면서 커밋함

`master branch` : 상징적인 branch, 제대로 동작하는 SW
`(master) -> branch` : (스티커/ 책갈피스티커 비슷한 의미)라 부른다. 특정 커밋을 의미함 ,`master`가 커밋을 한 부분에 붙는다, 앞선 커밋을 참조해야한다.
- branch는 쪼개기 위해 사용하는 명령어 -> 나중에 합치기 위해 사용(merge)
- branch에서 오류가 남 -> branch 삭제를 하면 그 branch로 커밋한것이 다 삭제됨

- `HEAD` < 어떤 커밋을 보고 있냐를 의미한다.
- `git commit -m ' test '` : commit은 HEAD가 하는 것이다.
- `git checkout` : sha 가 필요함 (과거로 돌아가는 명령어) HEAD를 움직이는 명령어
- `git log --oneline` -> sha 값 보기, head 위치, 로그 짧게 한줄로 표시
- `git log --oneline --graph` : 짧게 보여준 로그를 그래프 화
- `git branch` : branch 목록
- `git branch 'name'` : head위치에 'name'란 branch 생성
- `git branch -d 'name'` : branch 삭제
- `git switch` : branch를 이동
 `git switch -c` : 만들고 이동
- `checkout` : branch와 commit id 두개 모두를 사용가능함
- `switch` : branch 이름만 사용
- `git merge` : branch 와 branch를 합치는 명령어 / 움직여야 하는(합침을 당하는쪽에) branch에서 사용
## Merge 상황
1. FF (Fast Forward) : 한 branch 와 master가 합침 -> master가 합쳐짐
2. Auto Merge :   - 자동으로 잘 합쳐짐 (자동으로 Merge Commit 발생!)
3. Auto Merge FAIL => Merge Conflict
  - 자동으로 합치기 실패(conflict)
	1. both modifed 파일을 수정
	2. git add 
	3. git commit 수동 커밋
- -->> merge 이후 잘 되면, 그대로 진행. Conflict 나면 수동으로 해결 후 커밋

## Git reset
`git reset --soft HEAD~` : 마지막 커밋의 변경사항을 stage 상태로 되돌림 (staged)
`git reset --mixed HEAD~` / git reset HEAD~ : 마지막 커밋의 변경사항을 stage 하지 않음 (modified)
`git reset --hard HEAD~` : 변경사항이 날아감, 마지막 커밋의 변경사항 모두 삭제(unmodified) 

commit 메시지 수정
- 다만 필요한 경우 길게 쓸수 있는데, 이때는 `git commit -m `보다는 `git commit` 이후 vim으로 들어가 길게 쓰는게 좋다.
`git commit` : -m 옵션 없이 길게 메시지 작성 가능
`git commit --amend #` :  직전 커밋만 수정할 수 있다.

`git config --global alias.logog 'log --oneline --graph' `: git alias(별명 가능) 
- 위 설정 등록 후 git logog 실행시 git log log --oneline --graph 실행