### Spring boot 21

#### 다중 File Upload
- `OS`에 따라 파일이 저장되지 않거나 이름이 자동으로 바뀐 채 업러드되는 이슈가 있음 -> 이런 상황에는 디스크에 업로드된 파일을 찾을 수 없음 -> 테이블에 원본 파일명과 저장 파일명은 `UUID`라고 부르는 고유 식별자를 저장함으로써 해결해야함
- 게시글과 파일은 `1 : N` 관계를 위해 외래키`(FK)` 제약조건 설정
- `@Builder` : 빌더 패턴으로 객체를 생성할 수 있게 해줌, 생성자가 파라미터가 많은 경우 가독성을 높여주기도하고, 원하는 변수에만 값을 넣어 객체를 생성할 수 있음.
- `@Component` : 개발자가 직접 정의한 클래스를 빈으로 등록할 때 사용
- `form` 태그에 `enctype`을 선언해줘야함 -> `multipart/form-data`
- 파일 업로드/다운로드 모든 영역에서 공통으로 사용할 수 있어야함