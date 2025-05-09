### React_Spring_30

#### Spring (File Upload Controller)
- `File` 관련 `controller` 생성하여 구현.
- `Thumbnailator` 라이브러리 활용 썸네일 환경설정.
- `customFIleUtil class` 에 업로드된 파일 타입을 가져와서 이미지인지 아닌지 판별하도록 코드 작성.
- 이미지 파일일 경우에만 썸네일 작업
```
// 파일 타입 가져오기
String contentType = file.getContentType();

// 이미지일 경우 thumbnail 이미지로 업로드 경로에 저장.
if (contentType != null && contentType.startsWith("image")) {

    Path thumbnailPath = Paths.get(uploadPath, "s_" + savedName);

    Thumbnails.of(savePath.toFile()).size(200, 200).toFile(thumbnailPath.toFile());
}
```