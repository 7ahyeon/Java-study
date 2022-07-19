# Inner class

**inner class / nested class 내부 클래스**

1. 인스턴스 클래스 (instance class)

- 객체를 생성해야 사용 가능
- 외부 클래스의 필드변수 선언위치에 선언
- 외부 클래스의 인스턴스 변수처럼 취급
- 외부 클래스의 인스턴스 변수들과 관련된 작업에 사용할 목적으로 선언 사용

- 외부 클래스명.내부 클래스명 : 내부 클래스의 타입
- 객체 생성 : new 외부 클래스().new 내부 클래스()
```java
- 외부 클래스명.내부 클래스명 변수명 = new 외부클래스명().new 내부 클래스명()
- InstanceClass.Inner inner = new InstanceClass().new Inner();
```
```java
public class InstanceClass {
	
	int a = 100;
	private int b = 10;
	static int c = 300;
	int sum = 0;
	
	void sum() {
		sum = a + b;
	}
	
	//내부 클래스 Inner class : 인스턴스 클래스 (객체를 생성해야 사용 가능)
	class Inner{
		int in = 888;
		void printData() {
			System.out.println("int a : " + a);
			System.out.println("int b : " + b);
			System.out.println("int c : " + c);
			sum();
			System.out.println("sum : " + sum);
			System.out.println("내부 클래스 필드 in : " + in);
		}	
	}
}
```
```java
InstanceClass out = new InstanceClass();
	System.out.println("필드 변수 a : " + out.a);

	title("내부 인스턴스 클래스 사용");
	// 클래스 내부에 있는 Inner 클래스에 있는 printData() 메서드 실행
	// 외부 클래스명.내부 클래스명 : 내부 클래스의 타입
	// 객체 생성 : new 외부 클래스().new 내부 클래스()
	InstanceClass.Inner inner = new InstanceClass().new Inner();
	inner.printData();

	title("");
	System.out.println("Inner 클래스 필드변수 in : " + inner.in);
```
```java
필드 변수 a : 100
---내부 인스턴스 클래스 사용---
int a : 100
int b : 10
int c : 300
sum : 110
내부 클래스 필드 in : 888
------
Inner 클래스 필드변수 in : 888
```


2. 스태틱 클래스(static class)
- 클래스의 구성멤버의 일부가 static인 경우 클래스를 static 선언
- 외부 클래스의 필드변수 선언위치에 선언
- 외부 클래스의 static 멤버처럼 사용
- 외부 클래스의 static 멤버와 관련된 작업을 처리하기 위한 경우 사용
  
3. 지역 클래스(local class)
- 외부클래스의 메소드나 초기화 블럭 내에 선언
- 선언된 영역 내부에서만 사용

4. 익명 클래스(anonymous class)
- 클래스의 선언과 객체의 생성을 동시에 하는 이름없는 클래스(일회용)

```java
class 외부클래스 {
	//필드변수
	
	//생성자
	
	//메소드
	void method() {
		class 지역클래스 {
		
		}
	
	}

	class 인스턴스클래스 {
	
	}
	
	static class 스태틱클래스 {
	
	}
	
}
```
