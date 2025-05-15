### React_Spring_34

#### Spring (Product Service Layer)
- `service` 패키지에 `ProductService(imterface), ProductServiceImpl(class)` 생성
- `repository` 에서 반환을 `object` 배열로 나옴
- `object` 배열을 상품이랑 상품 이미지 하나가 해당함. --> 대표 이미지를 반한하게끔 되어 있음.
- 이렇게 반환 된 것들을 `ProductDTO`로 변환해서 처리해야함.
- `Object` 배열에서 첫번째[0]은 `Product`를 의미하고 두번째[1]는 `ProductImage`를 의미함.
- 여러개로 쌓여서 반환함 -> 반복문 처리
```
ex.
// 반복 처리 map() 활용
List<ProductDTO> dtoList = result.get().map(arr -> {

    ProductDTO productDTO = null;

    // Product
    Product product = (Product) arr[0];
    // ProductImage
    ProductImage productImage = (ProductImage) arr[1];

    // 가져온 DTO 와 IamgePath 변환해준다.
    productDTO = ProductDTO.builder().pno(product.getPno()).pname(product.getPname()).pdesc(product.getPdesc())
            .price(product.getPrice()).build();

    String imageStr = productImage.getFileName();
    productDTO.setUploadFileNames(List.of(imageStr));

    return productDTO;

}).collect(Collectors.toList());
```