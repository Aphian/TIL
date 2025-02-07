### MySQL

#### Mysql Install
- `MySQL Community Downloads` `Click`
- `MySQL Community Server` `Click`
- `ZIP Archive` 로 다운로드를 했을 경우
  1. 암축풀기
  2. 환경 변수 -> 시스템 변수 -> `path` 압축푼 `bin` 폴더 경로 입력
  3. `cmd` 창에서 설치 확인
- 초기 다운로드할 경우 초기 비밀번호가 자동 생성됨 --> 초기 비밀번호 확인
- 관리자 권한 `cmd` 실행
  1. `mysqld --initialze --console` 명령어로 초기화
  2. `A temporary password is generated for root@localhost` 와 함께 뒤에 비밀번호가 있음 --> 초기화 후 비밀번호를 기억 못할 시 압축 푼 폴더 위에 `data` 폴더를 삭제 후 `initialze --console` 명령어 다시 실핼하면 확인 가능
  3. `mysqld --console` 명령어로 `Mysql` 실행
  4. 새로운 `cmd` 창에서 `mysql -u root -p` 명령어 실행
  5. 위에 저장한 비밀번호로 연결
- 비밀번호 변경
  1. `mysql` 연결
  2. `ALTER USER 'root'@'localhost' IDENTIFIED BY '새로운_비밀번호';` 명령어 실행
  3. 바뀐 비밀번호로 `mysql` 접속 --> 비밀번호 변경 확인.

#### Mysql < -- > VScode 
- `VScode` 확장 --> `SQL Tools` / `SQL Tools MySQL/MariaDB Driver` 설치
- `SQL Tools` -> `Add New Connection` 선택 --> 사용 `DB` 선택
- `MySQL` 연결시 입력한 비밀번호 입력으로 연결
- `mysql` 이 실행되고 있어야 연결이 됨.

