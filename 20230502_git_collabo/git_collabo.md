# Git 협업


## 개인 git 활용
- 개인이 혼자 할 경우 로컬에 repo를 생성하고 remote repo를 연동한다.
- root commit를 해야 push 가능하다.

## 협업 git 활용
- 서로 협업을 해야 하기 때문에 개인 로컬 `repo` 에서 `push`를 하게 되면 통보식으로 `remote repo`에 올라가게 된다.
- 위의 상황을 방지 하기 위해 로컬 `repo`가 아닌 `remote repo`에서 `push`를 진행해야 한다.
- git remote repo 생성시, initialize repo 하위항목에 체크시(README, .gitignore) -> remote 에서 root commit 실행
- `git push origin master` => origin 이라는 이름의 원격저장소에, 내 로컬저장소 master branch push
- `git push origin a` => origin 이라는 이름의 원격저장소에, 내 로컬저장소 a branch push
- `git pull origin master` => origin 의 master 브랜치를 현재 local HEAD branch pull

## 협업 github에서 Merge
- `origin/master` branch에서 작업을 하게되면 여러명이 동시에 작업을 할 수가 없다.-> 여려 개의 branch로 쪼개야 함
- `origin/master` [remote repo] 에서 여러명이 각각의 branch 에서 `git add .`, `git commit -m '[메시지]'` 하고 그 branch 에서 `git push origin master` 실행한다.
- 성공적으로 `push`가 된다면 `github.com`에 접속하여 `pull request`를 확인하면서 `comment` 등을 활용하여 조율을 끝으로 `push`를 진행하여 `merge`를 한다.
    - `merge` 시 `conflict` 발생 할 경우
    - 해당 `branch`에서 `comflict`이 발생한 지점을 조율하고 `pull request` 
    - `merge`가 된다는 `commit`이 한번 더 찍힘
    - 그리고 그 `branch`와 `origin/master`와 merge를 한번 더 해야 최종적으로 Merge가 진행된다