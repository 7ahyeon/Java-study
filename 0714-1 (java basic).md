# Java-study

**클래스 Class**
- 구현체 : 기능 (method) 구현 ({} : 구현부)
- 객체 생성 가능

**인터페이스 Interface**
- 추상체 abstract : 기능 (method) 선언만 됨 ({} X)
- 객체 생성 불가 (추상 method)

**확장 Extends**
- 좌우 동일 타입 (하위 extends 상위)
- 클래스는 1개만 상속확장 가능(단일 상속)
- class extends class / interface extends interface1, interface2, ... interfaceN

**구현 Implements**
- class implements interface1, interface2, ... interfaceN
- class extends class implements interface1, interface2, ... interfaceN 


**객체 생성**
- 하위 클래스에서 객체 생성시 모든 상위 클래스 객체 포함

# 클래스 상속 확장(extends) 생성 및 사용 실습
 - Phone 클래스 상속 확장해서 만들기
 생성자
 - 폰 번호(phoneNo)만 받아서 객체 생성
 - 타입 값은 "WebPhone"으로 입력
 기능
 - 전화 걸기, 받기, 정보 보기, 웹 검색 기능 추가
 - 웹 검색 기능 : webSearch() : ">> WebPhone - 웹 검색" 화면 출력
 
 ```java
 public class WebPhone extends Phone {
	
	public WebPhone(String phoneNo) {
		super("WebPhone", phoneNo);
	}
	
	public void webSearch() {
		System.out.println(">> WebPhone - 웹 검색");
	}
}
```
```java
WebPhone Webph = new WebPhone("010-4444-4444");
Webph.call();
Webph.receiveCall();
Webph.view();
Webph.webSearch();
```
- 음악 플레이 기능 추가
```java
public class WebPhone extends Mp3Phone { //Phone
	
	public WebPhone(String phoneNo) {
		super("WebPhone", phoneNo);
	}
	
	public void webSearch() {
		System.out.println(">> WebPhone - 웹 검색");
	}
	
//	public void playMusic() {
//		System.out.println(">> 음악 플레이 !!");
//	}
}
```

