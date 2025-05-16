### React_Spring_35

#### Spring (Product List & Register)
- 게시글 정보일 경우 `DB`를 하나만 사용하는 단순한 데이터였음.
- `Product Entity` 안에는 `collection`이 들어가 있어서 신경 써야함.
- 수동적으로 받아온 값을 변환해주는 작업이 필요함.
- 받아 오는 값이 `DTO` 인데 이걸 `Entity`로 변환 해주는 작업이 필요하다.
- 파라미터가 `DTO` 인 메서드 생성
```
ex.
// 파라미터가 DTO
private Product dtoToEntity(ProductDTO productDTO) {

    Product product = Product.builder().pno(productDTO.getPno()).pname(productDTO.getPname())
            .pdesc(productDTO.getPdesc()).price(productDTO.getPrice()).build();

    // collection 관련 코드 start
    List<String> uploadFileName = productDTO.getUploadFileNames();

    // 이름이 없을 경우 그대로 Entity 반환.
    if (uploadFileName == null || uploadFileName.size() == 0) {
        return product;
    }
    
    uploadFileName.forEach(fileName -> {
        product.addImageString(fileName);
    });
    // end

    // Entity 반환.
    return product;

}
```