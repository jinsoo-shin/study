### 왜 쓰는가?

> 제네릭 타입을 이용함으로써 잘못된 타입이 사용될 수 있는 문제를 컴파일 과정에서 제거할 수 있다.
>
> 제네릭은 클래스와 인터페이스, 그리고 메소드를 정의할 때 타입을 파라미터로 사용할 수 있도록 한다.

### 장점

> #### 1. 컴파일 시 강한 타입 체크를 할 수 있다.
>
> 자바 컴파일러는 코드에서 잘못 사용된 타입 때문에 발생하는 문제점을 제거하기 위해 제네릭 코드에 대해 강한 타입 체크를 한다.
>
> 실행 시 타입 에러가 나는 것보다 컴파일 시에 미리 타입을 강하게 체크해서 에러를 사전에 방지하는 것이 좋다.
>
> #### 2. 타입 변환(casting)을 제거한다
>
> 비제네릭 코드는 불필요한 타입 변환을 하기 때문에 프로그램 성능에 악영향을 미친다.
>
> ```java
> List list = new ArrayList();
> list.add("hello")
> String str = (String) list.get(0); //타입 변환을 해야 한다.
> ```
>
> 제네릭 코드로 작성시 List에 저장되는 요소를 String 타입으로 국한하기 때문에 요소를 찾아올 때 타입 변환을 할 필요가 없어 프로그램 성능이 향상된다.
>
> ```java
> List<String> list = new ArraysList();
> list.add("hello");
> String str = list.get(0);
> ```

## 제네릭 타입

> 제네릭 타입이란 타입을 파라미터로 가지는 클래스와 인터페이스를 말한다.
>
> Object 타입을 사용하면 모든 종류의 자바 객체를 저장할 수 있다는 장점이 있지만, 저장할 때 타입 변환이 발생하고, 읽어올 때에도 타입 변환이 발생한다. 이러한 타입 변환이 빈번해지만 전체 프로그램 성능에 좋지 못한 결과를 가져올 수 있다.
>
> ```java
> public class Node{
> 	private Object object;
> 	public void set(Object object){
> 		this.object =object;
> 	}
> 	public Object get() {
> 		return object;
> 	}
> }
> ```
>
> ```java
> Node node = new Node();
> node.set("hello");
> String str = (String) node.get(); // Object 타입을 강제로 String 타입으로 변환
> ```
>
> 제네릭을 사용하여 Node 클래스 수정
>
> ```java
> public class Node<T>{
> 	private T object;
> 	public void set(T object){
> 		this.object =object;
> 	}
> 	public T get() {
> 		return object;
> 	}
> }
> ```
>
> ```java
> Node<String> node = new Node<>();
> ```
>
> 자동으로 타입 파라미터 T가 String 타입으로 변경되어 Node 클래스의 내부는
>
> ```java
> public class Node<String>{
> 	private String object;
> 	public void set(String object){
> 		this.object =object;
> 	}
> 	public String get() {
> 		return object;
> 	}
> }
> ```
>
> ```java
> Node node = new Node();
> node.set("hello");
> String str = node.get(); // 타입 변환이 발생하지 않는다.
> ```
>
> 
>
> 이와 같이 제네릭은 클래스를 설계할 때 구체적인 타입을 명시하지 않고, 타입 파라미터로 대체했다가 실제 클래스가 사용될 때 구체적인 타입을 지정함으로써 타입 변환을 최소화시킨다.

## 멀티 타입 파라미터

> 두 개 이상의 멀티 타입 파라미터를 사용
>
> ```java
> public class Node<T, M>{
> private T x;
> private M y;
> 
> public T getX(){
> 	return this.x;
> }
> public M getY(){
> 	return this.y;
> }
> 
> public void setX(T x){
> 	this.x = x;
> }
> public void setY(M y){
> 	this.y = y;
> }
> }
> ```

## 제네릭 메소드

> 매개 타입과 리턴 타입으로 타입 파라미터를 갖는 메소드
>
> ```java
> public class Sample{
> 	public <T> Node <T> func(T t){
>      Node<T> node = new Node<T>;
>      node.set(t);
>      return node;
>  }
> }
> ```
>
> 
>
> ```java
> Node<Integer> node = Sample.<Integer>func(100);
> int value = node.get();
> 
> Node<String> node = Sample.func("abc");
> String value = node.get();
> ```



## 제한된 타입 파라미터

> T extends 최상위타입
>
> 타입 파라미터에 지정되는 구체적인 타입을 제한할 필요가 종종 있다.
>
> 예를 들어 숫자를 연산하는 제네릭 메소드는 매개값으로 Number 타입 또는 하위 클래스 타입(Byte, Short, Long...)의 인스턴스를 가져야 한다.
>
> ```java
> public <T extends 상위타입> 리턴타입 메소드(매개변수,....) {.....}
> ```
>
> ```
> public <T extends Number> int compare(T t1, T t2){
> 	double v1 = t1.doubleValue(); //Number의 doubleValue() 메소드 사용
> 	double v2 = t2.doubleValue();
> 	return Double.comapre(v1,v2);
> }
> ```
>
> 
