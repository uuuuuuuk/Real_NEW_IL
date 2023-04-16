# **@ColumnDefault**

스프링으로 이메일 인증을 만들던 도중 다른 코드를 참고 하는데 이메일 엔티티에서 <br><br>
```java
@ColumnDefault("1")
private Integer attemptCount;
```

와 같은 컬럼이 만들어져있는 것을 보았다. attemptCount 라는 것은 해석해보니 시도횟수 정도와 비슷한 말인데 위 컬럼에 달려있는 `@ColumnDefault("1")` 은 무엇일까??

<br>

궁금해서 찾아보니 `@ColumnDefault("1")` 는 테이블을 처음 생성할 때 컬럼의 기본 값 제약 조건을 정의해주는 어노테이션이었다. 

한마디로 위의 코드는 처음 시도횟수의 기본 값을 단순히 1부터 시작하게 하는 코드였던것..

앞으로도 모르는게 있다면 바로바로 찾아보면서 궁금증을 남겨두지 않는 개발자가 되어야겠다고 생각했다.

`+`

추가로 아래에서 다음과 같은 코드도 발견할 수 있었다.

```java
    public void increaseAttemptCount() {
        this.attemptCount += 1;
    }
```