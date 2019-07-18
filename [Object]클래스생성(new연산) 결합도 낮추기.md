### 책 : [Object]                                              
___
#### 오늘의 주제 : new 연산자는 결합도를 높인다. 클래스 생성시 결합도를 낮추는 법.
#### 날짜 : 2019-07-18(잔디2)
#### 학습시간 : 21:26 ~ 22:30
#### 진도 : p.271~p.274
___
## 오늘 꼭 알아야 하는 내용.
#### new 는 객체간의 결합도를 높인다. 
#### new 연산자는 클래스의 인스턴스를 생성하는데 사용한다.
#### 구체클래스에 직접 의존하면 결합도는 높아진다. 당연하다. 반대로 추상클래스에 의존하면 결합도는 낮아진다.
___

### 객체를 new로 생성하면 안된다.
> 그 이유.
> new 연산자를 사용하기 위해서는 구체 클래스의 이름을 직접 기술해야 한다. 따라서 new를 사용하는 클라이언트는 추상화가 아닌 구체 클래스에 의존할 수 밖에 없기 때문에 결합도가 높다.
> new 연산자는 생성하려는 구체 클래스뿐만 아니라 어떤 인자를 이용해 클래스의 생성자를 호출해야 하는지도 알아야 한다. 따라서 new를 사용하면 클라이언트가 알아야 하는 지식의 양이 늘어나기 때문에 결합도가 높아진다.

> 아래 예제는 AmountDiscountPolicy의 인스턴스를 **직접 생성**하는 Movie 클래스 코드이다.
```
public class Movie{
    private DiscountPolicy discountPolicy;
    public Movie(String title, Duration runningTime, Money fee, DiscountPolicy discountPolicy{
        this.discountPolicy= new AmountDiscountPolicy(Money.wons(800), new SequenceCondition(1), ...);
    }
}
```
위 코드의 부작용은 Movie 객체가 AmountDiscountPolicy를 생성하는데 필요한 메서드 인자의 정보를 알게된다는 것이다. 이로 인해 결합도가 증가하였다.

AmountDiscountPolicy 메서드 인자가 변경된다면, 당연히 Movie 클래스에도 변경의 영향이 미친다. 이처럼 new 연산자로 다른 클래스의 인스턴스를 생성하는 방법은 변화에 취약한 코드가 된다.

### 이를 해결하는 방법!!!!

> 인스턴스를 생성하는 로직과 생성된 인스턴스를 사용하는 로직을 분리하는 것이다.
> AmountDiscountPolicy를 사용하는 Movie는 인스턴스를 생성해서는 안 된다. 사용하기만 해야 한다. 
> Movie는 외부로부터 이미 생성된 AmountDiscountPolicy의 인스턴스를 전달받아야 한다.
> 외부에서 인스턴스를 전달받는 방법은 **의존성 해결**과 동일하다.
> 1. 생성자의 인자로 전달하거나
> 2. setter 메서드 사용
> 3. 실행 시에 메서드의 인자로 전달하면 된다.


> 올바르게 객체가 오로지 메시지만 전달하는 역할을 하게 작성해보면..
> 다음 코드는 생성자를 통해 외부의 인스턴스를 전달받아 의존성을 해결하는 Movie의 코드이다.
> ```
> public class Movie{
    private DiscountPolicy discountPolicy;
    //@생성자
    public Movie(String title, Duration runningTime, Money fee, DiscountPolicy discountPolicy){
        this.discountPolicy=discountPolicy;
    }
}
다음 코드에서 알아야 하는 것.
> 1. Movie는 AmountDiscountPolicy 인스턴스를 직접 생성하지 않는다. 사용만 할거다.
> 2. AmountDiscountPolicy 인스턴스는 누가 생성하는가? Movie의 클라이언트가 처리한다. 
> 3. Movie는 단지 메시지를 전송한다.

Movie 클라이언트
> ```
> Movie JohnWick = new Movie("존윅", Duration.ofMinutes(120), new AmountDiscountPolicy(Money.wons(800), new SequenceCondition...));
> ```

사용과 생성의 책임을 분리한 예이다. 결론적으로는 결합도가 낮아진다.

