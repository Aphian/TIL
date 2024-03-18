### Springboot Server

#### 고정 IP 생성
- `AWS` 서버에 접속하려면 고정 `IP`가 필요
- 네트워킹 탭에 `고정 IP 생성 ` 클릭
- 로컬 서버의 `8080번 포트`를 사용
- 방화벽을 해제하여 `8080` 포트로 접속을 허용

#### 프라이빗 키 만들기
- `SSH` 또는 `SFTP` 프로그램으로 서버를 접속하기 위해 `SSH` 키가 필요
- `SSH` 는 네트워크 상의 다른 컴퓨터에 로그인하거나 원격 시스템의 명령을 수행하는 프로토콜 또는 프로그램
- `SFTP (SSH File Transfer Protocol)`는 `SSH` 프로토콜 위에서 파일은 안전하게 전공하고 관리하는 역할
- `SSH` 클라이언트 : `SSH` 프로토클을 사용하여 원격 시스템 또는 서버에 접속하여 명령을 실행할 수 있는 프로그램

#### Springboot Server Setting
- `AWS` 서버에 자버 설치
  1. `sudo apt update` : 우분투 패키지 최신 업데이트
  2. `sudo apt install openjdk-18 -jdk` 명령어 자바 설치
- 프로젝트 디렉토리 생성 : `mkdir sbb`
- 배포 받은 `.jar` 파일을 실행하면 서버에 접속한 터미널 프로그램을 종료할 경우 `SBB` 서비스가 중단됨
- -> 백그라운드로 서비스 실행해야함 -> 시작 스트립트 작성 -> 권한 부여 하 스트립트만 입력해도 실행 하도록 해야함
- 권한 부여 : `chmod +x start.sh` / `chmod +x stop.sh`
```
나노 편집기 사용 시
start.sh
#!/bin/bash

JAR=sbb-0.0.1-SNAPSHOT.jar
LOG=/home/ubuntu/sbb/sbb.log

nohup java -jar $JAR > $LOG 2>&1 &
```
- 중지 스트립트 작성
```
#!/bin/bash

SBB_PID=$(ps -ef | grep java | grep sbb | awk '{print $2}')

if [ -z "$SBB_PID" ];
then
    echo "SBB is not running"
else
    kill -9 $SBB_PID
    echo "SBB stopped."
fi

```