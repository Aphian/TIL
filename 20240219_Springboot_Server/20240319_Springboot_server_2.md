### Springboot Server

#### `Nginx` 설치 및 설정
- `AWS` 서버에서의 `Nginx` 설치 : `sudo apt install nginx`
- -> `sites-available` 디렉토리안에 `default` 파일만 존재함
- `sbb 파일 생성`
```
server {
        listen 80;              // 포트
        server_name localhost;

        location / {
                proxy_pass http://localhost:8080;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                proxy_set_header Host $http_host;
        }
}
```
- `sbb` 파일을 `Nginx`가 `SBB` 서비스의 설정 파일로 읽을 수 있도록 디렉토리와 링크가 필요함
- `sites-enabled` 디렉토리는 `sites-available` 디렉토리에 있는 설정 파일 중에서 활성화하고 싶은 것을 링크로 관리하는 디렉토리
- `default` 링크는 80번 포트롤 사용하도록 설정되어 있어 삭제해야함
- `ubuntu@jumpto:/etc/nginx/sites-enabled$ sudo ln -s /etc/nginx/sites-available/sbb` 링크 명령어

#### `Nginx 실행 및 적용
- `ubuntu@jumpto:/etc/nginx/sites-enabled$ sudo systemctl stop nginx` : `Nginx` 중지 명령어
- `ubuntu@jumpto:/etc/nginx/sites-enabled$ sudo systemctl start nginx` : `Nginx` 시작 명령어
- 502 오류가 발생 했다면 스트립트 시작 명령어 : `ubuntu@jumpto:~/sbb$ ./start.sh` 실행

### Springboot DB PostgreSQL 전환
- `PostgreSQL` 사용 방법 : `AWS` 서버에 `PostgreSQL`을 직접 설치 / `AWS`가 제공하는 데이터베이스 인스턴스를 사용하는 방법
- `AWS` 서버에 설치 : `sudo apt install postgresql-client` 명령어로 클라이언트 설치
- `build.gradle` 파일 : `runtimeOnly 'org.postgresql:postgresql` 추가하여 적용