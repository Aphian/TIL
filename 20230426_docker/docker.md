# Docker
- Docker는 개발환경을 만드는데 있어 문제가 발생하는 경우를 대부분 줄여주기 위해 의존성 관리
- Docker 설치
- Docker hub 로그인
---
1. PowerShell -> wsl --install ->재시작 됨 -> 터미널 창 user id/ pwd 설정
2. -> https://ueh0.notion.site/Docker-d7fe545d44c340ecab6ae7218f2da502 참조
3. -> Ubuntu -> mkdir learn-docker 폴더 생성 -> code learn-docker 명령어
4. -> Vcode 에서 Docker 설치 -> 터미널 확인해서 가상의 환경 이해
---
Image (객체 지향에서의 Class) : 이미지 하나로 여러개의 Container 만들 수 있음
Container(객체 지향에서의 Instance)

터미널에서 docker 명령어 쓰는것은 Docker CLI 환경이다

## 명령어
`docker run <img-name>` : 이미지에 있는 프로세스를 실행 및 컨테이너 생성
`docker run <img-name> <command>` : 컨테이너 생성 + 실행 + 시작 커맨드 override
`docker create` : 컨테이너 생성 -> 컨테이너 ID를 보여줌
`docker start <컨테이너 ID>` : 프로세스 실행
`docker creat <img-name>` : 이미지
`docker start -a <container id>` : STDOUT / STDERR 출력하며 컨테이너 실행
`docker system prune` : 모든 종료된 컨테이너 및 기타 삭제
`docker logs <container-ID>` : 해당 컨테이너의 출력기록(로그) 확인
`docker kill <container-ID>` : 컨테이너 종료 강제적임
`docker stop <container-ID>` : 컨테이너 10초간 시간을 주고 정상종료 시킴
`docker exec <container-ID> <command>` : 실행중인 컨테이너에 새로운 명령어 실행
`docker exec -it <container-ID> <command>` : 실행중인 컨테이너에 새로운 명령어 실행 + 입출력
`docker exec -it <container-ID> <command>` sh : 실행중인 컨테이너 내부의 sh 실행 + 입출력
`docker exec -it <container-ID>` sh : 실행중인 컨테니어 내부의 sh 실행 + 입출력
`docker run redis` : redis 는 DB와 비슷함 접근을 위해선 컨테이너안에 redis-cli

- Alpine Linux => adk add
- Ubuntu Linux => apt install

## Doker Image 생성
`FROM` []
- COPY ./ ./ : 로컬 pwd의 모든 파일을 컨테이너의 디렉토리로 복사 명령
- 첫 번째 ( ./ ): 현재 위치 디렉토리
- 두 번째 ( ./ ): 복사할 위치 디렉토리
- RUN [] [apk add -> install]
- RUN [] [apk add gcc]
- CMD
---
먼저 했던일이 있다면 캐싱되어 있는것을 활용함
순서가 바꼇다면 경과가 같아도 처음부터 실행함.

`$ docker build .`
`$ docker build -t usename/projectname:latest .`
`$ docker run  -p 8080:8080 docker.io/rsw7876/simple_web ` 컨테이너와 로컬의 네트워크 포트 연결