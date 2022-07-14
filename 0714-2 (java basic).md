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
