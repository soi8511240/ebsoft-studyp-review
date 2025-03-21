# 리뷰 내용
## 2025-02-28

*동적으로 매소드를 쓰게끔.. 정적x*
- 바인딩은 컴파일 시에도 수행되고, 런타임 시에도 수행됩니다.<br>
컴파일 과정에서 수행되는 바인딩 - 정적(static) 바인딩 ex- overloading, System.out.println( "log" );<br>
런타임 과정에서 수행되는 바인딩 - 동적(dynamic) 바인딩 ex- Override, System.out.println( exam.total() );

- 정적(static) 특징
파라미터로 컨트롤되기떄문에 컴파일시에 결정된다.<br>
인스턴스를 생성하더라도 static 키워드가 붙은 멤버들은 모든 인스턴스가 같은 메모리 영역을 공유함. 같은 멤버가 호출됨.<br>
[설명 블로그 링크](https://hyunsb.tistory.com/58) <br>
*확인이 필요하다.* <br>

*DI? 제어역전.*
- 로직이 들어가는 부분은 하드코딩지양. 
- 제어를 받는 함수만 구현하고, 제어를 하는 부분은 확장성있게 작성하고 가져옴.
- 의존성을 주입하는 부분을 지양.

의존성 주입 패턴.
- class 간에 관계를 결정해주는 디자인패턴
- 의존성이 높으면 안된다.
예를들어
````java
public class Shop{
  private Book book;
}
Book book = new Book();
Shop shop = new Shop(book);
````
위처럼 너무 강하게 결합되어있는경우(book이 없으면 에러)<br>
아래처럼 *외부에서 상품을 주입(Injection) 받아야* 한다.
````java
public class Shop {
  private Product product;
  public Shop(Product product) {
    this.product = product;
  }
}

Book book = new Book();
Shop shop = new Shop(book);
````
결론: 강하게 결합된 클래스들을 분리
- 객체 간의 관계를 결정 
- 두객체간의 관계라는 관심사 분리, 두 객체간의 결합도를 낮춤으로서 유연성을 확보
- 객체의 유연성을 높임
- 테스트 작성을 용이하게함.
- Spring은 의존성 주입을 도와주는 DI컨테이너이다.
  
api 문서 lib - swagger, rest doc

Null이 있을수 있는경우는 명시적으로 Optional<>로 처리해 주어야한다.

MapStruct 같은 서비스 매퍼는 모아서.
