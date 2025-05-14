### React_Spring_33

#### Spring (Product (Image) List Read)
- 목록이 출력될 때 이미지도 같이 나와야함.
- 상품 하나 당 목록이 10개 로 설정을 해놓음.
- 즉, 쿼리가 10번이 전송되어야 함. --> 과부하가 걸린다.
- `elementcollection` 조인 가능함.
```
ex. p 와 pi (elementcollection 어노테이션을 설정한 entity)
@Query("select p, pi from Product p left join p.imageList pi where pi.ord = 0 and p.delFlag = false")
Page<Object[]> selectList(Pageable pageable);
```
- `elementcollection` 을 조인하여 사용할 경우 정렬에 값을 잘 정해야함 에러 발생하면 찾기 어려울 수 있음.

#### Spring (QueyrDSL & ElementCollection)
- `Q Domain`을 그대로 `import` 해서 사용하면 된다.
```
// Entity
QProduct product = QProduct.product;
QProductImage productImage = QProductImage.productImage;

JPQLQuery<Product> query = from(product);
// product entity 에 있는 imagelist 를 productImage로 간주한다
// elementcollection 사용
query.leftJoin(product.imageList, productImage);

query.where(productImage.ord.eq(0));
```