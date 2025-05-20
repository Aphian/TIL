### React_Spring_37

#### Spring(Product Update & Delete)
- 조회 -> 변경이 가능한 항목 수정 -> 저장
- 파일들이 있어서 좀 더 복잡해짐.
- 파일을 수정할 경우 변경이 됬는지 안됐는지 알 수가 없음.
- `ArrayList`를 다른 객체로 바꾸면 안됨 --> `List`를 비워야함.
```
// 목록 지우기
product.clearList();

ex. 이미지 처리.
if (uploadFileNames != null && !uploadFileNames.isEmpty()) {

    uploadFileNames.forEach(uploadName -> {

        product.addImageString(uploadName);

    });

}
DB 에 저장하면 끝.
```
- `update`의 `PUT` 방식 : 페이로드`(PayLoad)`를 사용해 새로운 리로스를 생성하거나, 대상 리소스를 나타내는 데이터를 대체함.
- `PUT` 방식 : 멱등성을 가진다. -> 같은 객체를 여러 번 보내도 한 번만 생성되거나 계속해서 같은 값을 보냄.
- `Controller`에서의 `Multipart`(이미지) 동작 원리
  1. 어떤 파일들이 지워졌는지 알기 위해 `DB`에 저장된 값 가져오기
  2. 수정된 파일들 등록 --> 추가하고자 하는 파일 이미지 처리
  3. 기존에 있던 파일 --> 유지하려는(그대로) 파일 이미지 처리
  4. 지우려는 파일 처리
```
ex.
@PutMapping("/{pno}")
public Map<String, String> modify(@PathVariable("pno") Long pno, ProductDTO productDTO) {

    productDTO.setPno(pno);

    1.
    ProductDTO oldProductDTO = productService.get(pno);

    2.
    List<MultipartFile> files = productDTO.getFiles();
    List<String> currentUploadFileNames = fileUtil.saveFiles(files);

    3.
    List<String> uploadedFileNames = productDTO.getUploadFileNames();

    if (currentUploadFileNames != null && !currentUploadFileNames.isEmpty()) {

        uploadedFileNames.addAll(currentUploadFileNames);

    }

    productService.modify(productDTO);

    4. 
    List<String> oldFileNames = oldProductDTO.getUploadFileNames();
    if (oldFileNames != null && oldFileNames.size() > 0) {
        List<String> removeFiles = oldFileNames.stream()
                .filter(fileName -> uploadedFileNames.indexOf(fileName) == -1).collect(Collectors.toList());

        fileUtil.deleteFiles(removeFiles);

    }

    return Map.of("RESULT", "SUCCESS");

}
```