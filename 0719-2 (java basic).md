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

- 외부 클래스명.내부 클래스명 변수명 = out.new 내부클래스명()
- InstanceClass.Inner inner = out.new Inner();
```
```java
public class InstanceClass {
	
	int a = 100;
	private int b = 10;
	static int c = 300;
	int sum = 0;
	
	void sum() { //로컬 
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
```java
- 외부 클래스명.내부 클래스명 변수명 = new 외부클래스명.내부 클래스명()
- StaticClass.Inner inner = new StaticClass.Inner();
```
```java
int a = 100;
	private int b = 10;
	static int c = 300;
	
	static int sum = 0;
	static int sNum1 = 20;
	static int sNum2 = 30;
	
	static void sum() { // 로컬 클래스 
		sum = Inner.d + sNum2; //static 변수만 사용 가능
	}
	
	// 내부 스테틱 클래스 (inner class중 static class)
	static class Inner{
		static int d = 1000;
		int e = 2000;
		void printData() {
//			System.out.println("int a : " + a); //non-static 변수 사용 불가
//			System.out.println("int b : " + b); //non-static 변수 사용 불가
			System.out.println("static int c : " + c); //static 변수 사용 가능
			
			System.out.println("내부 선언된 static int d : " + d); 
			System.out.println("내부 선언된 int e : " + e); 
			
```
```java
public static void main(String[] args) {
	int num = StaticClass.c; //클래스명.static변수명 : static 변수 사용
	StaticClass.sum(); //클래스명.static메서드명 : static 메서드 사용

	// 클래스명.내부클래스명.static변수명 : 내부 클래스인 static 클래스의 Static 필드변수 사용
	int innerNum = StaticClass.Inner.d;

	// : static 내부 클래스 객체 생성 후! non-static 메서드 사용
	// 외부 클래스명.내부 클래스명 변수명 = new 외부클래스명.내부 클래스명()
	StaticClass.Inner inner = new StaticClass.Inner();
	inner.printData(); // 생성된 객체(인스턴스)로 non-static 메서드 실행
}
```

3. 지역 클래스(local class)
- 외부클래스의 메소드나 초기화 블럭 내에 선언
- 선언된 영역 내부에서만 사용
```java
public class LocalClassTest {
	
	int a = 100;
	
	void innerTest(int k) {
		System.out.println(">> innerTest() 메서드 시작");
		int b = 200; //지역 변수(local variable)
		int c = k;
		
		// 지역 클래스(local class) : 메서드 내에 선언된 클래스
		// 선언된 메서드 내부에서만 사용 가능
		class Inner{
			void printData() {
				System.out.println(">> 지역 클래스 printData() 실행 시작");
				System.out.println("외부 int a : " + a);
				System.out.println("외부 메서드 int b : " + b);
				System.out.println("외부 메서드 int c : " + c);
				System.out.println("외부 메서드 파라미터 k : " + k);
				System.out.println(">> 지역 클래스 printData() 실행 끝");
			}
		}
		Inner in = new Inner();
		in.printData();
		System.out.println(">> innerTest() 메서드 끝");
	}
	
	public static void main(String[] args) {
		
		LocalClassTest outer = new LocalClassTest();
		outer.innerTest(999);

	}

}
```
```java
>> innerTest() 메서드 시작
>> 지역 클래스 printData() 실행 시작
외부 int a : 100
외부 메서드 int b : 200
외부 메서드 int c : 999
외부 메서드 파라미터 k : 999
>> 지역 클래스 printData() 실행 끝
>> innerTest() 메서드 끝
```

4. 익명 클래스(anonymous class)
- 클래스의 선언과 객체의 생성을 동시에 하는 이름없는 클래스(일회용)
```java

interface TestInter {
	int DATA = 100; //public/static/final
	void printData(); //추상 메서드
	
}

class TestInterImpl implements TestInter{

	@Override
	public void printData() {
		System.out.println(">> 구현한 메서드");
	}
	
}

public class AnonymousClassTest {

	public static void main(String[] args) {
		TestInterImpl imp = new TestInterImpl();
		imp.printData();
		
		TestInter imp2 = new TestInterImpl();
		imp2.printData();
		
		
		System.out.println("---인터페이스 직접 구현 객체 사용---");
		
		//익명 클래스 : 클래스의 이름이 없는 클래스		
		TestInter test = new TestInter() {

			@Override
			public void printData() {
				System.out.println("DATA : " + DATA);
			}
		};
		test.printData();
	}

}
```
