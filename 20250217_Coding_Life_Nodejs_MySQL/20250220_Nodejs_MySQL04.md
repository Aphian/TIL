### Node.js & MySQL_05

#### Node.js & MySQL (Delete)
- `SQL` 문 `Delete` 명령어 실행 -> `Where` 조건문 반드시 필요

#### Node.js & MySQL (Join Read)
- 두 개의 테이블의 관계성으로 `JOIN` 명령어 실행
```
명령어 ex.
SELETE * FROM topic LEFT JOIN author ON topic.author_id = author.id
```
- `JOIN` 시 기본키를 분명히 해줘야함.