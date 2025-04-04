### React_Spring_10

#### Springboot(Entity Class)
- `Entity` : `Entity Class` or `Entity Object`
- `Entity Class` `springboot` 에서 연동된 `DB`에 테이블을 만드는데 사용하는 코드
- `class` 에 `@Entity` 어노테이션을 설정하면 됨.
- `@Table(name = "tb 이름")` 테이블 이름 설정
- `Entity` 에서는 `PK[기본키]` 가 있어야함
- 기본키 역할을 하는 `private` 변수에 `@Id` 어노테이션 설정
- `Auto Increment` 처리를 위해 `@GeneratedValue` 타입 설정으로 키 생성 전략을 정할 수 있음 --> `auto increment` 는 `IDENTITY` 전략을 사용함. 가장 무난하고 가장 많이 사용함.
- `String` 자료형의 변수는 기본으로 `255` 로 크기로 설정이 되어 있음.
- `@Colum(length = 길이, nullable = false)` 로 길이와 `Not null` 설정이 가능함.

```
ex.
public class Todo {

    // PK
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long tno;

    @Column(length = 500, nullable = false)
    private String title;

    private String content;

    private boolean complete;

    private LocalDate dueDate;

}
```