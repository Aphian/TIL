## board_like
- N : M 관계 활용
- DB에 변화가 생기므로 `POST` 방식으로 전송해야함
- `python` 언어의 속도가 빠르다 해도 `DB`에 특화된 기능을 이용할 경우 `DB`에 기능을 직접적으로 활용해야 부하가 적음. ex) `filter().exists():` <-- 조건에 따라 `True / False` 로 값이 반환됨
- ex)
```
    if feed.like_users.filter(pk=user.pk).exists():
        # 취소
        feed.like_users.remove(user)
    else:
        # 추가
        feed.like_users.add(user)

```
- `if user in feed.like_users.all():` --> python 언어`(if _ in _ :)`를 이용한 방법
- DB에서 전체적으로 값을 가져오는 방법이라 부하가 생김
---
## board_profile
- 개체를 `views.py` 에서 가져올 경우 `user`를 인스턴스 명으로 하면 `HTML`에서 요청을 할 때 사용되는 `user` 변수와 중복되서 덮어쓰기가 됨
- `user` 변수 사용에 유의해야함.