# object
#### object 책을 읽으며 직접 코드를 작성하고 공부한 것을 기록하는  repository 입니다.


### chapter 01 _ 객체 설계
#### 1. 티켓 판매 애플리케이션 구현하기(TicketSaleApp)
#### 2. 무엇이 문제인가

> **소프트웨어 모듈의 3가지 목적**
>  1. 제대로 실행되어야 한다.
>  2. 변경이 용이 해야한다.
>  3. 사람이 이해하기 쉬워야 한다.

현재 코드는 제대로 실행되기는 하지만 _**변경이 용이하지 않으며 사람이 이해하기 쉽지 않다**_.

* 변경이 쉽지 않다   
  * Audience와 TicketSeller를 변경할 경우 Theater도 함께 변경된다.
  * _**최소한의 의존성만 유지하고 불필요한 의존성은 제거하자!**_

* 이해하기 어렵다    
  * 관람객과 판매원이 모두 소극장이 통제한다. → 예상에서 크게 벗어나는 코드
  * 세부적인 내용을 한번에 기억하고 있어야한다. → Audience가 Bag을 가지고 있으며 Bag에는 현금과 티켓이 들어있을 수 ... 😮‍💨

**객체 설계의 목적은 결합도를 낮춰 변경이 용이한 설계를 만드는 것이다!**



#### + 추가적으로 알게 된것
* Arbitrary Number Of Arguments(... , 가변 매개 변수)
  - 일정한 형의 변수를 여러 개 전달해야 할 경우 사용한다.
  ```
  TicketOffice(amount, ticket1, ticket2);
  
  ...
  
  public TicketOffice(Long amount, Ticket ... tickets) {
     // ticket1 == tickets[0]
     // ticket2 == tickets[1]
  }
  ```

