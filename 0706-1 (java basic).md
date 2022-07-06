# Java-study

boolean
- 초기값 설정 필수 X 
- 기본값 false

생성자 매개변수 추가
- 중첩 가능
```java
void run () {
	System.out.println(">>앞으로 이동");
	}
void run(int speed) {
	System.out.println(">>앞으로 " + speed + "km 속도로 이동");
	}
 
 car.run();
 car.run(70);
 ```
 
 **예제1. 클래스 작성**
 
 ```java
 package edu.class3.Phone;

public class Phone {
	
	
	String name = "아이폰";
	String type = "se2";
	int hsize = 7;
	int vsize = 8;
	boolean hasLCD;
	
	public Phone() {
		
	}
	
	
	Phone(String name, String type) {
		this.name = name; // this 현재 객체(인스턴스)
		this.type = type;
	}
	
	Phone(String name, String type, boolean hasLCD){
		this.name = name;
		this.type = type;
		this.hasLCD = hasLCD;
	}

	void call() {
		System.out.println("전화 걸기");
	}
	
	void receiveCall() {
		System.out.println("전화 받기");
	}
	
	void sendSms(String message) {
		System.out.println("[메세지 전송] " + message);
	}
	
	String receiveSms(String message) {
		System.out.println("[메세지 수신] " + message);
		return message;
	}
	
	void view() {
		System.out.println("---전화기 정보---");
		System.out.println("모델명 : " + name);
		System.out.println("타입 : " + type);
		System.out.println("가로 크기 : " + hsize);
		System.out.println("세로 크기 : " + vsize);
		System.out.println("LCD유무 : " + hasLCD);
		
	
		
		
	}


	@Override
	public String toString() {
		return "Phone [name=" + name + ", type=" + type + ", hsize=" + hsize + ", vsize=" + vsize + ", hasLCD=" + hasLCD
				+ "]";
	}
	
}
```

```java
package edu.class3.Phone;

public class PhoneMain {
	public static void main(String[] args) {
		
	Phone phone1 = new Phone();
	String phone1String = phone1.toString();
	System.out.println("phone1String : " + phone1String);
	System.out.println("phone1: " + phone1);
	phone1.view();
	
	System.out.println();
	System.out.println("---기능 테스트---");
	phone1.call();
	phone1.receiveCall();
	phone1.sendSms("7월");
	
	phone1.receiveSms("0706"); // 리턴값 받았으나 버려짐
	
	String receiveMsg = phone1.receiveSms("6일");
	System.out.println("받은 메세지: " + receiveMsg);
	
	phone1.hsize = 10;
	phone1.vsize = 20;
	phone1.view();
	
	System.out.println("---phone2---");
	Phone phone2 = new Phone("갤럭시22", "스마트폰");
	System.out.println("phone2 : " + phone2);
	phone2.hsize = 12;
	phone2.vsize = 22;
	phone2.hasLCD = true;
	
	phone2.view();
	
	System.out.println("---phone3---");
	Phone phone3 = new Phone("아이폰", "스마트폰", true);
	System.out.println("phone3 : " + phone3);
	phone3.hsize = 13;
	phone3.vsize = 23;
	
	phone3.view();
	
	
	}
	
}
```

**배열 array**

- num1 = 10
- num2 = 20
- num3 = 30
- num4 = 40
|num|10|20|30|40|
|index|0|1|2|3|4|

- num[0] = 15
|num|15|20|30|40|
|:---:|:---:|:---:|:---:|:---:|
|index|0|1|2|3|4|









