### React_Spring_31

#### Spring (Upload Read & Delete)
- 조회는 실제 파일을 조회하는 것이 아니라 파일 데이터를 전달 해 주는 것.
- `Spring` 에선 `resource` 데이터를 전달한다고 생각.
- 전송해주는 타입을 정해야 함.
```
파일 데이터를 정의 하는 코드
public ResponseEntity<Resource> getFile(String fileName) {
    // spring에 내재되어 있는 Resource 라이브러리를 이용
    Resource resource = new FileSystemResource(uploadPath + File.separator + fileName);

    if (!resource.isReadable()) {

        resource = new FileSystemResource(uploadPath + File.separator + "default.jpg");

    }

    HttpHeaders headers = new HttpHeaders();
    // 외부에 관련된 것을 처리하기 위해선 예외 처리 필요
    try {
        headers.add("Content-Type", Files.probeContentType(resource.getFile().toPath()));
    } catch (IOException e) {
        throw new RuntimeException(e);
    }
    // 파일 데이터 리턴
    return ResponseEntity.ok().headers(headers).body(resource);

}
```
- `controller` 에서는 위에 코드를 반환으로 조회 처리.
- `file delete` 는 썸네일이 있다면 썸네일도 같이 삭제를 해줘야함.
- `Files` 내에 내재되어 있는 라이브러리 `deleteIfExists` 메서드 활용