## board_follow
- N : M 관계로 표현
- 본인과 본인과 참조 할 경우
- `self` 변수 사용 == `settings.AUTH_USER_MODEL`
- `symmetrical` 기본값 `True` --> 서로 자동으로 관계가 표현됨
- 서로 관계가 수락되게 설정을 위해 `False` 
```
stars = models.ManyToManyField('self', symmetrical=False, related_name='fans')

```