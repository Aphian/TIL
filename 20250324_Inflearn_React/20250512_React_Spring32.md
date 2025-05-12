### React_Spring_32

#### Spring (Entity)
- 보통 게시글과 댓글은 `Many To One` 관계를 사용함
- 게시글에 `LifeCycle` 과 댓글의 `LifeCycle` 이 다르기 때문에
- `Product`에서는 `Element Collection` 처리를 하는 것이 좋음.
- `Entity` 와는 다르다. `Id`가 없음
- 예를 들어, `Product` 수정을 한다고 생각을 하면 `Product` 에 이미지를 수정하는것이 포함되어 있다 --> `LifeCycle`이 동일하다.
- `Element Collection` 자체가 주인공이 되지 않음.
- `Entity` 와 관련된 처리가 `Element Collection` 과 같이 이뤄진다.
- `@ElementCollection` 어노테이션으로 설정가능.