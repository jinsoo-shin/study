# spring

**5\) Spring에서 DI란 무엇인지 아시나요?**

: DI는 Dependency Injection\(의존성 주입\)의 약자로, 객체들 간의 의존성을 줄이기 위해 사용되는 Spring의 IOC 컨테이너의 구체적인 구현 방식입니다.

  DI는 기존처럼 개발코드 부분에서 객체를 생성하는 것이 아니라, 팩토리 패턴처럼 객체의 생성과, 데이터를 주입만 담당하는 Factory에 해당 하는 

 별도의 공간에서 객체를 생성하고 데이터간의 의존성을 주입해 개발코드에서는 이를 가져다 씀으로서 의존성을 줄이는 방식입니다. 이때, 

 Factory 패턴의 Factory Class의 역할을 스프링의 환경설정 파일이 담당합니다.

**16\) Spring의 AOP란?**

: AOP는 Aspect Oriented Programming 관점 지향 프로그래밍의 약자로, 기존의 OOP\(객체 지향 프로그래밍\)에서 기능별로 class를 분리했음에도 불구하

 고, 여전히 로그, 트랜잭션, 자원해제, 성능테스트 메서드 처럼 공통적으로 반복되는 중복코드가 여전히 발생하는 단점을 해결하고자 나온 방식으로

 이러한 공통 코드를 "횡단 관심사"라 표현하며 개발코드에서는 비지니스 로직에 집중하고 실행시에 비지니스 로직 앞, 뒤 등 원하는 지점에

 해당 공통 관심사를 수행할 수 있게 함으로서 중복 코드를 줄일 수 있는 방식입니다.

**17\) Filter와 Interceptor 방식의 차이?**

: 

**18\) 디자인 패턴 아는 것?**

1\) 싱글톤\(SingleTone Pattern\) : 대표적으로 Calendar 객체나 dataSource 객체처럼 객체가 하나만 생성되어야 하는 경우

 전체 코드에서 하나의 객체만 존재할 수 있도록 이미 생성된 객체가 있으면 그 객체를 사용하도록 하는 방식입니다.

2\) 팩토리 패턴\(Factory pattern\) : 객체간 의존성을 줄이기 위해 객체의 생성과 데이터 주입만 담당하는 Factory Class를 정의하고 개발 코드 부분에서는

   생성된 객체를 가져다 사용함으로서 의존성을 줄이는 방식입니다.

3\) 옵저버 패턴\(Observer Pattern\) : 기후 정보처럼 RSS 수신시 하나의 객체가 변하면 다른 객체에 객체가 변했다는 사항을 알려주어야 할 경우에 주로

    사용됩니다.

**19\) MVC 패턴이란?**

- Model : data 처리와 접근을 담당

- View : Client에 보여지는 화면을 담당

- Controller : Model과 View를 제어

하는 3가지 부분으로 나눔으로서, 데이터와 화면간의 의존관계를 벗어날 수 있게하는 개발 기법입니다.  
  
**22\) Servlet vs JSP**

- Servlet : 자바 언어로 웹 개발을 위해 만들어진 것으로, Container가 이해할 수 있게 구성된 순수 자바코드로만 이루어진 것

- JSP : html 기반에 JAVA 코드를 블록화하여 삽입한 것으로 Servlet을 좀 더 쉽게 접근할 수 있도록 만들어 진 것  
  
출처: [https://js2prince.tistory.com/entry/java-경력-기술-면접-질문-리스트](https://js2prince.tistory.com/entry/java-%EA%B2%BD%EB%A0%A5-%EA%B8%B0%EC%88%A0-%EB%A9%B4%EC%A0%91-%EC%A7%88%EB%AC%B8-%EB%A6%AC%EC%8A%A4%ED%8A%B8) \[개발은 전투다\]





### DAO data access object 

DB를 사용해 데이터를 조회하거나 조작하는 기능을 담당하는 것  
싱글톤패턴

statement ㅇㅇ



### DTO

Data Transfer Object의 줄임말이다. VO\(Value Object\)라고도 표현하는데, 계층간 데이터 교환을 위한 자바빈즈\(Java Beans\)  
get setter가 여기있

DTO는 Database에서 Data를 얻어 Service나 Controller 등으로 보낼 때 사용하는 객체

### Service

Service에 대해서 살펴보자. Service는 비지니스 로직이 들어가는 부분이다. Controller가 Request를 받으면 적절한 Service에 전달하고, 전달 받은 Service는 비즈니스 로직을 처리한다. DAO로 데이터베이스를 접근하고, DTO로 데이터를 전달받은 다음, 적절한 처리를 해 반환한다.



**3. MVVM\(Model - View - ViewModel\)**

ViewModel 뷰모델 말그대로 View를 나타내주기 위한 Model이라고 생각하면 된다. View보다는 Model과 유사하게 디자인 되며, View의 바인딩 될 때 가장 강력하다. 

MVP와 같이 View에서 입력이 처리된다.

MVVM 패턴의 가장 큰 **장점**이라 함은 **Command**와 **Data Binding**으로 MVP 패턴과 달리 **View와의 의존성을 완벽히 분리** 할 수 있다는 장점이 있다.

Command를 통하여 Behavior를 View의 특정한 ViewAction\(Event\)와 연결할 수 있으며, ViewModel의 속성과 특정 View의 속성을 Binding 시켜 줌으로써 ViewModel 속성이 변경 될때마다 View를 업데이트 시켜줄 수 있다.  
  
출처: [https://hackersstudy.tistory.com/71](https://hackersstudy.tistory.com/71) \[공대인들이 직접쓰는 컴퓨터공부방\]





