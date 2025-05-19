### React_Spring_36

#### Spring (Product Controller & Service)
- `Product` 데이터를 `Create` 할 때 파일 업로드도 이루어져야함.
- `Multipart` 파일로 되어 있도록 구현. 이걸 먼저 `Create` 해줘야 의미가 있다.
- `CustomFileUtil.java` 안에 `fileUtil` 에 구현을 해놓음.
- `fileUtil` 에 문자열로 문자열 목록을 만드는 것.
- `Entity`를 `DTO` 로 변환해주는 메서드가 필요함.
```
ex.
private ProductDTO entityToDTO(Product product) {

    ProductDTO productDTO = ProductDTO.builder().pno(product.getPno()).pname(product.getPname())
            .pdesc(product.getPdesc()).price(product.getPrice()).delFalg(product.isDelFlag()).build();

    List<ProductImage> imageList = product.getImageList();

    if (imageList == null || imageList.isEmpty()) {
        return productDTO;
    }

    List<String> fileNameList = imageList.stream().map(productImage -> productImage.getFileName()).toList();

    productDTO.setUploadFileNames(fileNameList);

    return productDTO;
}
```