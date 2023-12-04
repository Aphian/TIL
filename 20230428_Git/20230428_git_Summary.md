## Git 

### Git : VCS(Version Control Service)

1. 버전 관리 : 나중에 특정 버전을 불러올 수 있도록 시간이 지남에 따라 파일 또는 파일 집합에 대한 변경사항을 기록하는 시스템
2. Git에 작업은 로컬 파일과 리소스만 필요하다 -> 네트워크가 필요치 않다.
3. 무결성이 있다 -> 체크섬(해시값)이라는 참조주소가 있어 각각이 구분을 할 수 있다.
4. 데이터만을 추가한다.-> git에서 작업을 수행하면 거의 모든 작업이 Git 데이터베이스에만 데이터를 추가한다.

- git (로컬 저장소 : Local Repository)
- github, bitbucket, gitlab (원격 저장소 : Remote Repository)

- github : 오픈소스에 성지, 오픈소스 공개를 위주 public 원격 저장소
- bitbucket : private 프로젝트 원격저장소 [아틀라시안]
- gitlab : 비공개 저장소를 참여 인원 수에 관계없이 무제한 생성 최대 용량 5GB -> 기업들이 많이함
---
### Git에 3 가지 상태(`modified`, `staged`, `Committed`)
- `README` : github에 프로젝트를 볼 시 설명서 및 개요 목록 등 작성
- `Modified` : 파일을 변경했지만 아직 데이터베이스에 커밋하지 않음.
- `Staged` : 수정된 파일을 다음 커밋 스냅샷으로 이동하도록 표시
- `Committed` : 데이터가 로컬 데이터베이스에 안정적으로 저장됨
---

### Git 초기 설정
- 최초 1회 설치시 git bash 터미널에서
    1. `git config --global user.name <'git hub name'>`
    2. `git config --global user.email <'git hub email'>`
- `git init` : 명령어 입력 위치 디렉토리에 .git/ 폴더를 생성 -> 터미널에 `(master)`라는 글귀가 보임
    1. 되돌리고 싶다면 `rm -rf .git/` 실행 -> init은 숨김폴더 .git을 생성하는 의미만 있어 삭제하면 되돌려짐.
---
### 기본 폴더와 git이 관리하는 폴더 간 구분
|기본 폴더|git 관리 폴더|
|---|---|
|폴더,디렉토리|repository(저장소 : repo)|
- **repo** 안에 **repo**를 만들지 말자!

### Git 명령어
- `git init` : git 초기화 (repo 생성)
- `git status` : repo 안에 내용물 상태 확인
- `git clone URL` : repo 복사
- `git push origin master` : commit 한 내용을 github에 올리는것
- `git pull origin master` : git hub에 있는 내용들을 가져오는 것