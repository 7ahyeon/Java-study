# 인터페이스 확장 실습


//인터페이스(interface) 구현(implements) 방식으로 클래스 만들기
```java
class Phone implements I_Phone{
	
	private String type;
	private String phoneNo;
	
	public Phone() {}
	
	public Phone(String phoneNo) {
		super();
		this.type = "타입";
		this.phoneNo = phoneNo;
	}
	
	public Phone(String type, String phoneNo) {
		super();
		this.type = type;
		this.phoneNo = phoneNo;
	}

	@Override
	public void view() {
		System.out.println("-타입 : " + type + ", " + "전화 번호 : " + phoneNo);
		System.out.println(">> view() 실행 !");
	}

	@Override
	public void call() {
		System.out.println(">> call() 실행 !");
	}

	@Override
	public void receiveCall() {
		System.out.println(">> receiveCall() 실행 !");
	}

	@Override
	public void sendMsg() {
		System.out.println(">> sendMsg() 실행 !");
	}

	@Override
	public void receiveMsg() {
		System.out.println(">> receiveMsg() 실행 !");
	}
```
```java
  // I_Phone 인터페이스를 구현한 Phone을 상속 확장(extends)하고
// I_Mp3Phone 인터페이스를 구현(implements)해서 클래스 만들기
class Mp3Phone extends Phone implements I_Mp3Phone {
	

	public Mp3Phone(String phoneNo) {
		super("Mp3Phone타입", phoneNo);
	}
	public Mp3Phone(String type, String phoneNo) {
		super("Mp3Phone타입", phoneNo);
	}
	
	@Override
	public void playMusic() {
		System.out.println(">>> playMusic() 실행 - 음악 플레이- ");
		
	}
```
```java

/* 인터페이스 구성 요소
 - static 상수 : public static final 선언된 변수
 - 추상 메서드 : public abstract 정의된 메서드
  :: 자바8(JDK8)에서 추가된 요소 : 구현부가 있는 메서드
  - public default 메서드 : public default method() {}
  - public static 메서드 : 공통으로 사용할 수 있는 메서드(기능구현 완료)
  재정의 없이 인터페이스명으로 참조 사용
*/

interface I_Phone { // public 있거나 없거나
	// 상수화된 변수 : public static final
	public static final boolean SUCCESS_CALL = true;
	boolean FAIL_CALL = true;
	
	// 인터페이스에 정의된 메서드 : 기본으로 public abstract method
	public abstract void view(); //public abstract method
	public void call(); 
	void receiveCall(); 
	
	void sendMsg();
	void receiveMsg();
	
	//public default 메서드
	//구현 클래스에서 구현을 안해도 되는 메서드
	//재정의해서 사용할 때만 구현하면 ok 
	public default void defaultMethod() {
		//구현해도 되고 안해도 되는 메서드
		//공통으로 사용하는 기본 기능이 있으면 구현해도 됨	
	} 
	//public static 메서드 
	//재정의 없이 인터페이스명으로 참조 사용
	public static void staticMethod() {
		System.out.println("I_Phone 인터페이스의 static 메서드");
	}

}
```
