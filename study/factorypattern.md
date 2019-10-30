# 팩토리 패턴

> JDK 및 Spring 프레임워크에 사용되고 있다.
>
> super class와 여러 개의 sub class가 있는 상황에서 input이 발생하면 하나의 sub class를 반환해야 할 때 factory pattern이 사용된다.
>
> 객체 생성을 대신 수행해주는 공장
>
> ## 장단점
>
> - 생성 할 클래스를 미리 알지 못해도 팩토리 클래스가 객체 생성 담당
> - 객체의 자료형이 하위클래스에 의해서 결정 
> - 동일한 형태로 프로그래밍 가능
> - 객체가 늘어날 때 마다 하위클래스 재정의로 인한 불필요한 많은 클래스 생성 가능성

```
// A 팩토리 추상 클래스
public abstract class A_Factory{
    public abstract string get_A();
}
```

```
//A 추상 클래스를 상속받은 각각의 A 클래스들
// a1
public class A1 extends A{

    @Override
    public String get_A()(){
        return "a1";
    }
}

// a2
public class A2 extends A{

    @Override
    public String get_A()(){
        return "a2";
    }
}
```

```
//A팩토리 추상 클래스
public abstract class A_Factory{
	public abstract A createA(String type);
}
```

```
//A 팩토리 추상 클래스를 상속받은 A 팩토리 구현 클래스
public class TypeA_Factory extends A_Factory{

    @Override
    public createA(String type){
        A a = null;

        switch(type){
            case("a1"):
                a = new A1();
                break;
            case("a2"):
                a = new A2();
                break;
        }
        return a;
    }
}
```

> 실제로 테스트해본다면

```
public static void main(String[] args){
	TypeA_Factory taf= new TypeA_Factory();
	
	A a1 = taf.createA("a1")
    A a2 = taf.createA("a2")
    
    System.out.println(a1.get_A()); //a1
    System.out.println(a2.get_A()); //a2가 출력이 된다!
}
```



메인 프로그램에서는 어떤 객체가 생성되었는지 신경 쓸 필요 없이 반환된 객체만 사용하면 된다.
